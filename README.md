# EasySet

Set up a new Windows PC the way you like it, from one window of check boxes: Thai and English language settings, the clock, the keyboard, File Explorer, the taskbar, desktop icons and a few Windows settings. You can undo the last change.

EasySet is one small `.exe` file. It needs no installing, and all its settings are inside the file. Its window uses standard Windows controls, so you can use it with the Tab key and a screen reader such as NVDA.

คู่มือภาษาไทย: [README.th.md](README.th.md)

## Download

Download the latest version: [EasySet.exe](https://github.com/oabi-siriwat/EasySet/releases/latest/download/EasySet.exe)

This link always gives the newest version. The checksum and the text manuals are on the [latest release](https://github.com/oabi-siriwat/EasySet/releases/latest) page.

The file is not signed. Windows SmartScreen may warn that it does not know the publisher. Choose More info, then Run anyway.

## Requirements

- Windows 10 or Windows 11
- .NET Framework 4, which comes with Windows
- Some settings change the whole PC. If Windows asks to confirm (UAC), choose Yes. When UAC prompts are already off, nothing is asked.

## How to use it

1. Open `EasySet.exe`. Each check box shows this PC's settings now: ticked means the setting is already set.
2. Tick the settings you want. Press Space to tick or untick.
3. Leave Backup (Alt+B) ticked if you want to be able to undo the change. It is ticked each time the program opens.
4. Choose Apply (Alt+A).

If everything worked, the Status box says `Done.` and no message comes up. A message comes up only when something failed, or when you need to sign out or restart the PC.

Unticking a box and choosing Apply does not turn that setting off, except for Control Panel. To go back, use Undo last change.

## The settings

Tab goes through them in this order.

### Language and region

| Setting | What it sets |
|---|---|
| Regional format: English (United States) | Dates like 11/16/2026, 12-hour time like 2:49 PM, dollars, and the Gregorian calendar |
| Regional format: Thai (Thailand) | Dates like 16/11/2569, 24-hour time like 14:49, baht (฿), and the Thai Buddhist calendar. Weeks start on Monday. |
| Country or region: Thailand | Thailand as the country. Windows and apps use it for local content, and Set time zone automatically uses it to choose the time zone. |
| Languages: English and Thai | English (United States) and Thai as languages, with English first, so Windows menus stay in English |
| Language for non-Unicode programs: Thai (Thailand) | Older Thai programs show Thai correctly. Needs a restart. It applies to every user of the PC. |
| Keyboard layouts and language switch key (Grave Accent) | English and Thai (Kedmanee) keyboards, switched with the Grave Accent key. Adds Thai to the language list if it is not there. |

You can tick only one regional format: ticking one unticks the other. Each sets all the standard formats of that language through Windows itself.

### Date and time

| Setting | What it sets |
|---|---|
| Set time zone automatically | Sets the time zone of the country in Region first, then lets Windows follow the PC's location. It also turns on Windows location. |
| Set time automatically | Keeps the clock in time over the internet. |

The program knows the time zone of Thailand. With another country it leaves the time zone as it is and tells you. When you change the country to Thailand, EasySet sets the time zone again, even if this box was already ticked.

Without an internet connection, the time zone is still set from the country, and Windows updates the clock when it is next online.

### Keyboard and cursor

| Setting | What it sets |
|---|---|
| Keyboard repeat delay: shortest | A held key starts repeating as soon as possible |
| Cursor blink rate: fastest | The text cursor blinks at its fastest |
| Keyboard shortcut for Sticky keys: off | Pressing Shift 5 times no longer turns on Sticky keys |
| Keyboard shortcut for Filter keys: off | Holding the right Shift key for 8 seconds no longer turns on Filter keys |

These work at once, without signing out.

### File Explorer

| Setting | What it sets |
|---|---|
| Show file name extensions | File names show their extension, such as `.txt` or `.exe` |
| Group by: None | Files in a folder are not put into groups |
| Sort by: Name, ascending | Files are sorted by name, A to Z. The desktop icons are sorted by name too. |
| View: Details | Files are shown as a list with columns: name, date, type and size |

The last three apply to every folder, including Downloads and This PC. To do this, EasySet restarts File Explorer: the taskbar goes away for a moment and comes back, and any open folder windows close and then open again. You can still change the view of a folder in File Explorer afterwards.

### Taskbar

| Setting | What it sets |
|---|---|
| Search: Hide | The search box or button is not shown on the taskbar. Press the Windows key and type to search. |
| Task view: Off | The Task view button is not shown on the taskbar. Windows+Tab still opens Task view. |
| Widgets: Off | Turns Widgets (news, weather and more) off and removes its button. It applies to every user of the PC. |
| Unpin all apps | Removes every app pinned to the taskbar, such as Edge, File Explorer and Microsoft Store. Open apps still show while they run. |

Search and Task view change at once. Widgets and Unpin all apps restart File Explorer: the taskbar goes away for a moment and comes back empty. Undo pins the apps back.

### Desktop icons

Computer, User's Files, Network, Recycle Bin and Control Panel show their icons on the desktop. Control Panel works like Windows' own Desktop icon settings: ticked shows the icon, and unticked hides it.

Allow themes to change desktop icons lets a theme change these icons.

### Windows

| Setting | What it sets |
|---|---|
| Classic right-click menu | The classic right-click menu with every command. File Explorer restarts to show it. |
| Recycle Bin: display delete confirmation dialog | Asks before moving a file to the Recycle Bin |
| Clear Run history | Clears the list of commands typed in the Run box |
| Old Notepad | Opens text files (.txt) in the classic Notepad instead of the new one |

### Security

| Setting | What it sets |
|---|---|
| Do not ask for UAC confirmation (less secure) | Programs you start as an administrator get full rights without asking |

This one is less secure: any program run by an administrator can then change the whole PC without a prompt. Choose it only if you understand that.

## When to sign out or restart

Most settings work as soon as Apply is done.

- At once: desktop icons, keyboards and the switch key, languages, country, time zone and clock, keyboard and cursor, Sticky keys and Filter keys, Recycle Bin, Old Notepad and the File Explorer settings.
- File Explorer restarts by itself: Classic right-click menu, Widgets, Unpin all apps and the three folder view settings. The taskbar goes away for a moment and comes back.
- Close and open programs again, or sign out: Regional format. Programs that are open keep the old formats until you open them again.
- Restart the PC: only Language for non-Unicode programs.

If no message comes up after Apply, there is nothing more to do.

## Undo

When the Backup check box (Alt+B) is ticked, Apply first saves the settings it will change as one backup file in the `EasySetBackup` folder beside the program. Each backup is a single .oabi file named by its date and time, such as `20261117_144900.oabi`. If saving fails, nothing is changed. When Backup is not ticked, nothing is saved, so Undo cannot put that change back.

Undo last change (Alt+U) is shown only when there is a change to undo. It asks first, with No as the default, then puts the earlier settings back. It asks you to restart only when it puts back the language for non-Unicode programs. Choose it again to go one more change back.

- Put the program in a folder you can write to, such as Documents or a USB flash drive, not Program Files.
- Only EasySet can open a .oabi file.
- An undone backup stays as a file ending in _undone.oabi. Do not rename or move the .oabi files, or Undo cannot find them.
- Undo puts back each saved part of the settings as a whole. Other settings in the same part that you changed after that go back too.

## Updates

Each time it opens, EasySet checks whether there is a newer version. Nothing else is sent. Without an internet connection, or when there is nothing new, it says nothing.

When there is a newer version, it asks first, with Yes as the default. Choose Yes and it downloads the new version, checks that the file arrived whole, puts it in place of this one, and opens it again. Choose No to keep this version; it asks again next time.

## Other things to know

- If Windows asks for the password of a different administrator account when it asks to confirm, the language, keyboard, desktop, right-click and File Explorer settings go to that account, not to yours.
- A PC managed by an organisation (such as a company or school PC) may set some of these settings back by itself.

## License

Copyright (c) 2026 Oabi. All rights reserved.

EasySet is free to use, at home or at work. You may share it as long as the files are not changed and you do not charge for it. You may not sell it, change it, reverse engineer it, or say that it is your own work. It comes with no warranty: you use it at your own risk. See [LICENSE](LICENSE) for the full terms.

