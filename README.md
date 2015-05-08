Scripts useful for maintaining the Mac games collection
=======================================================

Note that some other scripts are useful for this but which aren't actually
specific to the game bits, which can be found in
https://github.com/kergoth/dotfiles:

- extractico, extracticns: wrap around wrestool extraction of icons from exe
  or dll files, also passed to makeicns for the latter
- new-app: create a mac .app to run a specified script, useful for creation of
  custom wrappers
- apath: resolve a Finder alias
- mkalias: create a Finder alias
- select-random: select a random input line from stdin, used by
  run-random-game
- tag-find: handy wrapper around mdfind for selection of files matching
  specified tags (or without specified tags). find-games requires this.
