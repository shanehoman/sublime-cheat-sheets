# Sublime Text Cheat Sheets Plugin

Cheat-sheets is a plugin for quickly accessing cheat sheets in the Sublime Text editor. Typing the key sequence will open a cheat sheet in a new tab. If the sheet is already open, it will simply activate the tab.

![Regular Expressions Cheatsheet](https://raw.github.com/dmikalova/sublime-cheat-sheets/master/example.png "Regular Expressions Cheatsheet")

## Available Cheat Sheets

At the moment all cheat sheets are under heavy development as I use this plugin. Feel free to submit your own. Be aware that edits to the defaults sheets will be erased by an update. If you want to edit a sheet, copy it from `$st3/Packages/Cheat Sheets/cheat-sheets` to `$st3/Packages/Users/cheat-sheets`.

* Bash "cmd/ctrl + shift + c" + "s" + "h"
* Git "cmd/ctrl + shift + c" + "g" + "i" + "t"
* Github Flavored Markdown "cmd/ctrl + shift + c" + "g" + "f" + "m"
* Go "cmd/ctrl + shift + c" + "g" + "o"
* KDE "cmd/ctrl + shift + c" + "k" + "d" + "e"
* Regular Expressions "cmd/ctrl + shift + c" + "r" + "x"
* Sublime Text "cmd/ctrl + shift + c" + "s" + "t"

## How to add your own Cheat Sheets

* Add your cheat sheets to `$st3/Packages/User/cheat-sheets/filename.cheatsheet`.

* Add a keyboard shortcut by adding the following line to `./Packages/User/Default (OS).sublime-keymap` and change the keys and filename:

```
{ "keys": ["ctrl+shift+c", "n", "s"], "command": "cheat_sheet", "args": {"cheatsheet": "filename"} }
```

* Add a menu entry by adding the following to `./Packages/User/Main.sublime-menu` and change both instances of filename:

```
[
  { "id": "tools", "children": [
    { "id": "cheat-sheets", "caption": "Cheat Sheets", "children": [
      { "caption": "Regular Expressions", "command": "cheat_sheet", "args": {"cheatsheet": "Regular Expressions"} }
    ]}
  ]}
]

```
To add multiple entries just copy and paste the caption line and add a comma in between each entry.

* Highlighting follows this format:

```
>\tHeader
>\t\tSubtext
Text
Command or code\s\sText
\tCommand or code # Comments anywhere
```
Where \t means tab and \s means space

* If there's a problem, you can try making a shortcut that runs the tester command. The tester command will print the file paths where it expected your filename to be to the console. The console can be opened with `` Ctrl + \` ``.

```
{ "keys": ["ctrl+shift+c", "r", "y"], "command": "cheat_sheet_tester", "args": {"cheatsheet": "filename"} }
```

## Source
This plugin is based off of Steve Hammond's [Cheater](https://github.com/shammond42/cheater) plugin.