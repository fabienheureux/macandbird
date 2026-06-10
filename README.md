# MacAndBird

A macOS-native theme for Mozilla Thunderbird, adapted from
[FluentBird](https://github.com/Deathbyteacup/fluentbird) by Danny King.
Where FluentBird brings Windows 11 Fluent Design and Mica to Thunderbird,
MacAndBird does the same for the Mac — taking Apple Mail as its reference.

Released under the MIT License.

## Design language

- **Apple Mail message list** — selected messages become a solid accent-blue
  pill with white text when focused, and a quiet grey pill when the list
  loses focus. Unread messages get the familiar blue dot.
- **Source-list sidebar** — folder symbols are SF Symbols–style glyphs, all
  tinted with the system accent colour; account names read as small grey
  section headers; selection is a translucent rounded pill (Big Sur style).
  Unread counts are plain grey numbers, not badges.
- **Monochrome toolbar** — action buttons (reply, forward, archive, trash…)
  are borderless template images in a single secondary tint, with a soft
  rounded hover wash, exactly like Mail's toolbar.
- **System palette** — `#007AFF` / `#0A84FF` accent, Apple's secondary-label
  greys, hairline separators. Light and dark mode both follow the macOS
  system appearance automatically.
- **San Francisco** — the system font everywhere, with Mail's weight
  hierarchy (semibold senders, regular subjects, secondary previews).

All design tokens live as CSS custom properties at the top of
`userChrome.css` (`--mb-accent`, `--mb-sidebar-pill`, …) and can be
overridden from `custom.css` without touching the theme.

## Icons

The Fluent icon set has been replaced with hand-drawn, SF Symbols–style
stroke glyphs (24 pt grid, hairline weight). They are applied as CSS masks,
so they are monochrome and tinted entirely by the theme — accent blue in the
sidebar, secondary grey in toolbars.

## Setup

1. **Enable userChrome.css**
   - Open Thunderbird
   - Go to **Settings** → **General**
   - Click **Config Editor…** under **Advanced**
   - Search for `toolkit.legacyUserProfileCustomizations.stylesheets`
   - Set it to `true`

2. **Use the system theme**
   - Make sure no other theme is selected in Thunderbird's Add-ons Manager.
     *Do not* select Light, Dark, or a store theme — leave it on
     "System Theme" so the theme can follow macOS light/dark appearance.

3. **Install the files**
   - Click **Help** → **Troubleshooting Information**
   - Under "Application Basics", find **Profile Folder** and click
     **Show in Finder**
   - Inside the profile folder, create a folder named `chrome` if it does
     not already exist
   - Copy `userChrome.css`, `custom.css`, and the `Icons` folder into
     the `chrome` folder

4. **Restart Thunderbird.**

No Mica / transparency flags are needed on macOS — the theme uses the
standard window appearance.

## Known limitations

Inherited from how Thunderbird is built (same constraints as FluentBird):

- Some areas render inside a Shadow DOM out of `userChrome.css` reach:
  the Settings pages, the compose window, and pop-up dialogs cannot be
  fully themed.
- The mail 3-pane view is fully themed; Contacts, Calendar, Tasks and Chat
  have partial theming.

## Credits

- [FluentBird](https://github.com/Deathbyteacup/fluentbird) by Danny King
  (www.dannyking.co.uk) — the structure and Thunderbird selector work this
  theme is built on. MIT License.
- Icon glyphs are original SVGs drawn in the style of Apple's SF Symbols
  (no Apple assets are redistributed).
