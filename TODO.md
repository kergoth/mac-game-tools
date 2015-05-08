- Consider setting LSApplicationCategoryType to public.app-category.games for
  all the games, rather than relying on the 'Game' tag.

    https://developer.apple.com/library/ios/documentation/General/Reference/InfoPlistKeyReference/Articles/LaunchServicesKeys.html#//apple_ref/doc/uid/TP40009250-SW8

    They can be found via:

    ```
    mdfind "kMDItemContentType == 'com.apple.application-bundle' && kMDItemAppStoreCategoryType == 'public.app-category.games'"
    ```

    Note that when doing so, we'd need to exclude game launchers (openemu,
    game center, etc), as well as the steam libraries, and any game tools.
