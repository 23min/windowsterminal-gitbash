# My Windows Terminal settings for Git Bash


## Add Git Bash

in `settings.json`, add the following to the `list` array under `profiles§

```
{
    // Git-Bash profile
    "guid": "{e8b37037-d20b-4573-b0c9-2b13d704d80c}",
    "name": "Git-Bash",
    "commandline": "C:\\Program Files\\Git\\bin\\bash.exe -l -i",
    "icon" : "C:\\Program Files\\Git\\mingw64\\share\\git\\git-for-windows.ico",
    "startingDirectory" : "%USERPROFILE%",
    "colorScheme" : "GitBash",
    "acrylicOpacity": 1.0,
    "useAcrylic": true,
    "closeOnExit": true,
    "cursorColor": "#FFFFFF",
    "cursorShape": "bar",
    "fontFace": "Consolas",
    "fontSize": 10
}
```

If you want the Git Bash color scheme in Windows Terminal, add the following to:

```
"schemes" : 
[
  {
    "background" : "#000000",
    "black" : "#0C0C0C",
    "blue" : "#6060ff",
    "brightBlack" : "#767676",
    "brightBlue" : "#3B78FF",
    "brightCyan" : "#61D6D6",
    "brightGreen" : "#16C60C",
    "brightPurple" : "#B4009E",
    "brightRed" : "#E74856",
    "brightWhite" : "#F2F2F2",
    "brightYellow" : "#F9F1A5",
    "cyan" : "#3A96DD",
    "foreground" : "#bfbfbf",
    "green" : "#00a400",
    "name" : "GitBash",
    "purple" : "#bf00bf",
    "red" : "#bf0000",
    "white" : "#ffffff",
    "yellow" : "#bfbf00",
    "grey" : "#bfbfbf"
  },
...
```

…and change “colorScheme” in the profile to “GitBash”:

```
...
"colorScheme" : "GitBash",
...
```

Finally, to add a right-click context menu “Windows Terminal Here” to Windows Explorer, create a new file with “.reg” extension containing:

```
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\Directory\Background\shell\windowsterminal]
@="Windows Terminal Here"[HKEY_CLASSES_ROOT\Directory\Background\shell\windowsterminal\command]
@="\"C:\\Users\\{USERNAME}\\AppData\\Local\\Microsoft\\WindowsApps\\wt.exe\""
```

Replace {USERNAME} with the correct folder name in C:\Users\ on your machine.

Merge the .reg file with your registry by double-clicking it.