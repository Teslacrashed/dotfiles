Dotfiles
########

The purpose of this repo is to codify and unify various tooling as much as sanely possible.

Notations are made to explain what things are for, and document notes that help understand non-standard files.

I like over documenting what files are (their type of data or programming code) as well as what language or tool, because
I feel it's really beneficial for newcomers, I hated not knowing what a file was for when looking over code.

Some filetypes are grouped in ways to make it easy to cut out stuff you may not care about or need/want.

These files are very verbose and all-inclusive, but when working on a project I often cut out sections that I don't plan to use.


dircolors
=========

The dir_colors file is optimized for Solarized terminal colors, and the logic behind how it colors files is based on a scheme
that makes sense in that context.

git attributes
==============

once I saw a .gitattributes file that used these macros for spaces-2 (for files that use 2 spaces for tab/indent) then spaces-4,
this struck me as such a sensible standard to use, as spaces-2, spaces-4, spaces-8, and then tab versions, covers most standard files.


Tabs vs Spaces
==============

Tabs are preferred over spaces in many cases where a tool or language does not mandate one or the other.

Reasons I personally choose tabs:

* Tabs are more accessibility-friendly.
  People with visibility issues can more easily adjust tab spacing to their liking.
  This is the primary reason I choose to prefer them for code repos.
* With some filetypes that don't have strong standardizations, like .conf files, usually Linux prefers tabs in them.
  Usually it's very specific filetypes that prefer spaces, not vague ones like .conf
* Tabs are faster for interpreters to parse because they are a single character, so very minor speed / efficiency boost is achieved.
  Faster parsing due to less load means a very slightly more green computing.

filetypes treated as similarly as possible across tooling.
Typically broken into categories like Data, Markup, Prose, Programming.
Vaguely treat "flag files", like .gitkeep, where nothing exist in the file, as Data.
Their existence changes some programs configuration.
e.g.: .gitkeep, .gdignore

Attempts are made to accounting for common filenames conventions that add context but wouldn't normally be picked up
using standard extensions types. (dev.Containerfile, Containerfile.dev, or Containerfile-dev)
