## How to have rounded corners without a (visible) border - Power BI

Rounded corners are nice, but needing a border isn't :(

It would be great if you could just set the border width to 0, but Power BI doesn't let you go below 1px. 

Classic Power BI :') Thankfully you can permanently fix this with a tiny change to your theme file:

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

Borders will default to 0px width and everything else will work as expected. Hooray :')

(If you increase the width, you won't be able to change it back to 0 without clicking 'Reset to default')



\- Cam :)
