# Sublime Text 3 
## Install
Install the GPG key:
```
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
```
Ensure apt is set up to work with https sources:
```
sudo apt-get install apt-transport-https
```
Select the channel (Stable) to use:
```
echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
```
Update apt sources and install Sublime Text
```
sudo apt-get update
sudo apt-get install sublime-text
```
## License
Edit hosts：
- Ubuntu `sudo vim /etc/hosts`
- Windows `C:\Windows\System32\drivers\etc\hosts`
```
127.0.0.1       www.sublimetext.com
127.0.0.1       license.sublimehq.com
```
Sublime text 3176 license:
```
----- BEGIN LICENSE -----
sgbteam
Single User License
EA7E-1153259
8891CBB9 F1513E4F 1A3405C1 A865D53F
115F202E 7B91AB2D 0D2A40ED 352B269B
76E84F0B CD69BFC7 59F2DFEF E267328F
215652A3 E88F9D8F 4C38E3BA 5B2DAAE4
969624E7 DC9CD4D5 717FB40C 1B9738CF
20B3C4F1 E917B5B3 87C38D9C ACCE7DD8
5F7EF854 86B9743C FADC04AA FB0DA5C0
F913BE58 42FEA319 F954EFDD AE881E0B
------ END LICENSE ------
```
Sublime text 3143 license
```
—– BEGIN LICENSE —–
TwitterInc
200 User License
EA7E-890007
1D77F72E 390CDD93 4DCBA022 FAF60790
61AA12C0 A37081C5 D0316412 4584D136
94D7F7D4 95BC8C1C 527DA828 560BB037
D1EDDD8C AE7B379F 50C9D69D B35179EF
2FE898C4 8E4277A8 555CE714 E1FB0E43
D5D52613 C3D12E98 BC49967F 7652EED2
9D2D2E61 67610860 6D338B72 5CF95C69
E36B85CC 84991F19 7575D828 470A92AB
—— END LICENSE ——
```

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
