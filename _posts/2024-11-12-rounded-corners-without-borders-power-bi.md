---
layout: post
title: "Power BI - Rounded corners without a border"
categories: misc
---
## Power BI - Rounded corners without a border 

Rounded corners are nice, but needing a border line isn't :(

It would be great if you could just set the border width to 0px, but Power BI doesn't let you go below 1px. 

Classic Power BI :') 

---

You can work around it in a few ways, but doing that every time is a pain.

Thankfully, you can permanently fix this with a tiny change to your theme file:

```json
{
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

One less nuisance - hooray!



\- Cam :)
