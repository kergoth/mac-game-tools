- Consider setting LSApplicationCategoryType to public.app-category.games for
  all the games, rather than relying on the 'Game' tag.

    https://developer.apple.com/library/ios/documentation/General/Reference/InfoPlistKeyReference/Articles/LaunchServicesKeys.html#//apple_ref/doc/uid/TP40009250-SW8

    They can be found via:

    ```
    mdfind "kMDItemContentType == 'com.apple.application-bundle' && kMDItemAppStoreCategoryType == 'public.app-category.games'"
    ```

    Note that when doing so, we'd need to exclude game launchers (openemu,
    game center, etc), as well as the steam libraries, and any game tools.

## wrap-native

- Fix all the wrapper scripts to check supported correctly. That is, in some
  cases, just because we didn't find e.g. dosbox.exe doesn't mean the script
  should error out if it doesn't find it, so that check should only be done
  when running in check only mode.
- Add copymacicon to all the external scripts which use new-app, as the new
  app will otherwise have no icon at all when using a gamedir as a source.
- Consolidate common logic amongst the external scripts.
- Add temp dir usage to the external scripts, so the final app is renamed into
  place in a single operation.
- Add handling of GOG dosbox wrappers as input
- Add handling of Boxer standalone instances as input, not just wineskin
  wrappers of windows dosbox installs.
