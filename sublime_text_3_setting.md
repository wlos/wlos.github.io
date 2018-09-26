# Sublime Text 3 设置

## Preference Settings
``` powershell
{
    "trim_trailing_white_space_on_save": true,
	"ensure_newline_at_eof_on_save": true,
    "auto_find_in_selection": true,
    "bold_folder_labels": true,
    "dictionary": "Packages/Language - English/en_US.dic",
    "draw_minimap_border": true,
    "always_show_minimap_viewport": true,
    "draw_white_space": "all",
    "ensure_newline_at_eof_on_save": true,
    "fade_fold_buttons": false,
    "font_size": 21,
    "ignored_packages":
    [
    ],
    "save_on_focus_lost": true,
    "spell_check": true,
    "theme": "Default.sublime-theme",
    "trim_automatic_white_space": true,
    "trim_trailing_white_space_on_save": true
}
```
## Packages
- [**Package Control**](https://packagecontrol.io/packages/Package%20Control)
- [**SideBarEnhancements**](https://packagecontrol.io/packages/SideBarEnhancements)
- **AutoFileName**:  Pressing **Ctrl+Space**, will activate AutoFileName
- **Terminal**: Open Terminal at File Press **Ctrl+Shift+t** on Windows and Linux
- **LaTexTools**: A LaTeX Plugin for Sublime Text 2 and 3
- **ConvertToUTF8**: With this plugin, you can edit and save the files which encodings are not supported by Sublime Text currently, especially for those used by CJK users, such as GB2312, GBK, BIG5, EUC-KR, EUC-JP, etc.
- **Alignment** :  Select the lines you wish to align. Press **Ctrl+Alt+A** (Windows & Linux) or **Command+Ctrl+A** (Mac OS X)
	- setting 
``` powershell
{
   // The mid-line characters to align in a multi-line selection, changing
   // this to an empty array will disable mid-line alignment
   "alignment_chars": [
       "=", ":"
   ]
}
```
- **BracketHighlighter**: matches a variety of brackets such as: [], (), {}, "", '', #!xml <tag></tag>, and even custom brackets.
- **File​Diffs**: Shows diffs between the current file, or selection(s) in the current file, and clipboard, another file, or unsaved changes. 
- **Git​Gutter**: show git diff in gutter
- **SublimeREPL**:  run an interpreter inside ST2 or ST3 (**Python** + virtualenv, R, Ruby, **Matlab**, **Shell**...)
	- New build System for running python with sublimeREPL
``` powershell
{
	"target": "run_existing_window_command",
	"id"    : "repl_python_run",
	"file"  : "config/Python/Main.sublime-menu"
}
```
