# Orgmode.nvim

Orgmode clone written in Lua for Neovim 0.5.

## Installation

Use your favourite package manager:

* [vim-packager](https://github.com/kristijanhusak/vim-packager):
  ```lua
    packager.add('kristijanhusak/orgmode.nvim')
  ```
## Setup

```lua
require('orgmode').setup({
  org_agenda_file = {'~/Dropbox/org/*', '~/my-orgs/**/*'},
  org_default_notes_file = '~/Dropbox/org/refile.org',
})
```

* **Open agenda prompt**: `<Leader>oa`
* **Open capture prompt**: `<Leader>oc`

Features (TL;DR):
* Agenda view
* Search by tags/keyword
* Repeatable dates
* Capturing to default notes file/destination
* Archiving (archive file or ARCHIVE tag)
* Calendar popup for easier navigation and date updats
* Various org file mappings:
  * Promote/Demote
  * Change TODO state
  * Change dates
  * Insert/Move/Refile headlines
  * Change tags
  * Toggle checkbox state

Features (Detailed breakdown):
* Agenda prompt:
  * Agenda view (<kbd>a</kbd>):
    * Ability to show daily(<kbd>vd</kbd>)/weekly(<kbd>vw</kbd>)/monthly(<kbd>vm</kbd>)/yearly(<kbd>vy</kbd>) agenda
    * Support for various date settings:
      * DEADLINE:  Warning settings - example:  `<2021-06-11 Fri 11:00 -1d>`
      * SCHEDULED: Delay setting - example: `<2021-06-11 Fri 11:00 -2d>`
      * All dates - Repeater settings
        * Cumulate type: `<2021-06-11 Fri 11:00 +1w>`
        * Catch-up type: `<2021-06-11 Fri 11:00 ++1w>`
        * Restart type: `<2021-06-11 Fri 11:00 .+1w>`
    * Properly lists tasks according to defined dates (DEADLINE,SCHEDULED,Plain date)
    * Navigate forward (<kbd>f</kbd>)/backward(<kbd>b</kbd>) or jump to specific date (<kbd>J</kbd>)
    * Go to task under cursor in current window(<kbd><CR></kbd>) or other window(<kbd><TAB></kbd>)
  * List tasks that have "TODO" state (<kbd>t</kbd>):
  * Find headlines matching tag(s) (<kbd>m</kbd>):
  * Search for headlines (and it's content) for a query (<kbd>s</kbd>):
* Capture:
  * Define custom templates
  * Fast capturing to default notes file via <kbd><C-c></kbd>
  * Capturing to specific destination <kbd><Leader>or</kbd>
  * Abort capture with <kbd><Leader>ok</kbd>
* Org files
  * Refile to destination/headline: <kbd><Leader>or</kbd>
  * Increase/Decrease date under cursor: <kbd><C-a></kbd>/<kbd><C-x></kbd>
  * Change date under cursor via calendar popup: <kbd>cid</kbd>
  * Change headline TODO state: forward<kbd>cit</kbd> or backward<kbd>ciT</kbd>
  * Toggle checkbox: <kbd><C-space></kbd>
  * Toggle folding of current headline: <kbd><TAB></kbd>
  * Toggle folding in whole file: <kbd><TAB></kbd>
  * Archive headline: <kbd><Leader>o$</kbd>
  * Add archive tag: <kbd><Leader>oA</kbd>
  * Change tags: <kbd><Leader>ot</kbd>
  * Promote: <kbd><<</kbd>
  * Demote: <kbd>>></kbd>
  * Add headline/list item/checkbox: <kbd><Leader><CR></kbd>
  * Insert heading after current heading and it's content: <kbd><Leader>oih</kbd>
  * Insert TODO heading after current line: <kbd><Leader>oiT</kbd>
  * Insert TODO heading after current heading and it's content: <kbd><Leader>oit</kbd>
  * Move headline up: <kbd><Leader>oK</kb>
  * Move headline down: <kbd><Leader>oJ</kb>

Link to detailed documentation: [DOCS](DOCS.md)

## Thanks to
* [@dhruvasagar](https://github.com/dhruvasagar) and his [vim-dotoo](https://github.com/dhruvasagar/vim-dotoo) plugin
  that got me started using orgmode. Without him this plugin would not happen.
* [vim-orgmode](https://github.com/jceb/vim-orgmode) for some parts of the code (mostly syntax)
