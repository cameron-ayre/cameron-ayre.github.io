---
title: Reload Theme File (Almost) Instantly
author: cameron-ayre
date: 2024-11-25 08:00:00 +/-0800
categories: [Power_BI, Themes]
tags: [themes, autohotkey, extensions]
pin: true
---
> Note:
>
> The return on investment is tiny, so feel free to stop reading :')

‎

## The (minor) problem

Theme files are super handy, but working on them is **very** tedious.

Any time you want to see your changes in action, you have to click:
1. View
2. Themes Dropdown
3. Browse for themes
4. Select your theme
5. Open
6. 'Got it'

And you're gonna be doing that a lot :( Especially when fine tuning font sizes, colours, and so on.

‎

Made a quick change? _Reload the theme file._

Need a adjustment? _Reload the theme file._

Changed something else?  _Reload the theme file._

Took a breathe?  _Reload the theme file._

Giving up creating a custom theme?  _Reload the theme file._

‎

## Slightly better
With some keyboard shortcuts, you might get to avoid another headache.

From anywhere in the report view:
1. Press and release Alt (Microsoft calls these ['KeyTips'](https://support.microsoft.com/en-us/office/use-the-keyboard-to-work-with-the-ribbon-954cd3f7-2f77-4983-978d-c09b20e31f0e) for some reason)
2. Press **V** for **V**iew
3. **H** for t**H**eme
4. **M** for the**M**e also (?)
5. Find your theme
6. Hit Enter to Open
7. Hit Enter for "Got it"

Less painful but we can do even better

‎ 

## Doing Even Better
Download a program for creating macros, like [AutoHotkey](https://www.autohotkey.com/), and get it to do those keyboard presses for you practically instantly.

Here's my current AutoHotkey Script:

```ahk
#Requires AutoHotkey v2.0

!r:: { 
    if WinGetProcessName(WinExist("A")) = "PBIDesktop.exe" {
        Send "{Alt}vhm"
        Sleep 300
        Send "theme{Down}{Enter}"
        Sleep 300
        Send "{Enter}"
    }
}
```
When I press Alt + R, this script will:
1. Check if Power BI is the active window (juuuust in case)
2. Press Alt > V > H > M
3. Wait 300ms in case my computer is being slow
4. Type 'theme', hit the down arrow key, then Enter to open
5. Wait 300ms again while the theme loads.
6. Hit Enter to dismiss the pop-up

Note that step 4 assumes I've manually loaded my theme file once already (PBI will remember the folder) AND assumes the theme file is the first thing in that folder with the word 'theme' in the title.

It seems to run fine with as low as 20ms delays, if not lower. I'm just being cautious :') but you do you

---

Is this useless for anyone but me specifically? Yeah, probably.
Has it saved my sanity? Absolutely.

\- Cam :)
