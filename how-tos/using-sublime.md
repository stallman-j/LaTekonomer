
As you're going through the guide, you might get into the question of which LaTex installation to download.

For Mac, you'll want to download Mactex.

For Windows, download MikTex if you want LaTex taking up a little less space on your machine. Remember to allow it to download packages on the fly, though, and allow it to add itself to your paths. Download TexLive if you never want to worry about a missing package or think about LaTex again once you've downloaded it, but are willing to devote some 5G of your computer storage to LaTex. If you're indifferent, go with TexLive. More people maintain it.
        - To get a dark mode that feels a bit like Overleaf, follow [this tutorial](https://medium.com/@iitrabhi/how-to-setup-sublime-as-a-beautiful-latex-editor-dark-mode-windows-7ec5e0a24878) and then navigate to `File` -> `Open Folder` and open your project folder (for me, that's `LaTekonomer` itself). If it's still not working, go to `View`-> `Sidebar` and click `Show Sidebar.`
        - For a light theme, start out following the tutorial for the above (which installs the theme AYU along with setting some other nice settings). I like [AYU light](https://github.com/dempfi/ayu)>, which you can install by using `ctrl`+`shift`+`p` (to open the package manager), then typing `ayu: activate theme` -> `ayu light`.
            - To make the pdf viewer match, I also change a few Sumatra settings (`Settings`->`Advanced Options`). First, I set `MainWindowBackground = #828c99`, and then replace the settings of `FixedPageUI` with the following (colors obtained from [https://github.com/ayu-theme/ayu-colors](https://github.com/ayu-theme/ayu-colors))

          ```
          FixedPageUI [
          TextColor = #5C6166
          BackgroundColor = #FCFCFC
          SelectionColor = #035BD6
          WindowMargin = 2 4 2 4
          PageSpacing = 4 4
          InvertColors = false
          HideScrollbars = false
          ]
          ```
    - [Here's](https://www.sumatrapdfreader.org/settings/settings3-0) how to customize more Sumatra settings. And [here's what to do if your compilation is creating an "untitled" pdf](https://stackoverflow.com/questions/68548517/sublime-text-3-latextool-unintentional-new-window-after-compilation).
    - There's a keyboard shortcut that can help keep your project directory from getting cluttered with aux files, but the default is a little clunky. In Sublime, go to `Preferences-> Package Settings -> LaTeXTools -> Key Bindings - Default.` Search for `delete_temp_files`, and you should see that the default shortcut is `["ctrl+l","backspace"]`. In order to activate this shortcut, you need to 1) compile your .tex file (with `ctrl+b`), and then 2) _while_ your cursor is still focused on that file, hit `ctrl+l`, then release it, then hit `backspace`.
    - If that's an annoyance, you can change this keybinding, replacing for instance `["ctrl+l","backspace"]` with `["f5"]`. You still have to make sure your cursor is focused on the window of the main `.tex` file you want to delete.
        - For example, to delete `master_article.aux`, you would want to have your window open to `master_article.tex` and then hit `F5`.
        - If there's a type of file that you want to be deleted which isn't getting done, go to `Preferences-> Package Settings -> LaTeXTools -> Settings - User` and search `temp_files_exts`. Add the extension of the type of file (e.g. `".synctex"`) to the list.