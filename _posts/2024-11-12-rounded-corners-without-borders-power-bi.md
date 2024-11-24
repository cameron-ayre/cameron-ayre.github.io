---
title: Rounded corners with no (visible) border - Power BI
date: 2021-11-12 08:00:00 +/-0800
categories: [Power_BI, Themes]
tags: [themes, corners, border]   
---
Rounded corners are nice, but needing a border line isn't :(

It would be great if you could just set the border width to 0px, but Power BI doesn't let you go below 1px. 

Classic Power BI :') 

‎

You can work around this in a few ways, but doing that every time is a pain :(

Luckily you can permanently fix this by by setting the width to 0 in a custom json theme file.

Here's the bare minimum you'd need:

```json
{
    "name": "Theme Name",
    "visualStyles": {
        "*": {
            "*": {
                "border": [
                    {
                        "width": 0
                    }
                ]
            }
        }
    }
}
```

Borders will then default to 0px width, allowing rounded corners without a gross border line.

‎

One less nuisance - hooray!

\- Cam :)
