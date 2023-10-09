Dotfiles
########

This is a wip and not all the logic that has gone into these files is fully explained yet.

The purpose of this repo is to codify and unify various tooling as much as sanely possible.

By codify I mean to notate files by type if they are a text file that can be modified with a text editor, or a binary file that
requires a special program to be used. Then further broken down into types like Data or Programming.

By unify I mean filetypes are treated as similarly as possibly between tooling files, if the `.editorconfig` file says a filetype
uses tabs, then the `.gitattributes` file will set it for tabs, etc.

Notations are made to explain what things are for, and document notes that help understand non-standard files.

I like over documenting what files are (their type of data or programming code) as well as what language or tool, because
I feel it's really beneficial for newcomers, I hated not knowing what a file was for when looking over code when I was learning.

Some sections are grouped in ways to make it easy to cut out stuff you may not care about or need/want.

These files are very verbose and attempt to be all-inclusive,
but when working on a project I often cut out sections that I don't plan to use.

filetypes treated as similarly as possible across tooling.
Typically broken into categories like Data, Markup, Prose, Programming and/or Text or Binary files.
Vaguely treat "flag files", like .gitkeep, where nothing exist in the file, as Data.
Their existence changes some programs configuration.
e.g.: .gitkeep, .gdignore

.db is a very tricky file extension as I've seen some vendors use it for text files, Sqlite3 uses it for database files, and
other other programs uses it for their own binary format of data storage. If you are writing a program I would avoid using it,
the safest assumption is treating it as a binary file, because if it is a vendor's text file, you likely aren't going to be editing
it much, and if you are, just change it in the appropriate tooling files.

Attempts are made to accounting for common filenames conventions that add context but wouldn't normally be picked up
using standard extensions types. (dev.Containerfile, Containerfile.dev, or Containerfile-dev)


dircolors
=========

The `dir_colors` file is optimized for a Solarized-based terminal color scheme,
and the logic behind how it colors files is based on a scheme that makes sense
in that context.

Directories are yellow, like manilla office folders. Then Sticky / Other Writeable and Sticky + Other Writeable all
include yellow + White for Other Writeable, Black for Sticky, and Gray if both.

Pipe's are blue text on a green background (think water in a Super Mario Pipe). Sockets are black on a green background.

Executables are blue, this is because using Solarized most functions are blue, so blue is associated with executing code.

Data files that are text are Purple / Violet. This is because in Solarized I often see violet used for parameters, so I associate
key-value and data mappings with it.


git attributes
==============

Once I saw a .gitattributes file that used these macros for spaces-2 (for files that use 2 spaces for tab/indent) then spaces-4,
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
