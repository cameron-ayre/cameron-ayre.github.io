## How to have rounded corners without a (visible) border - Power BI

Rounded corners are nice, but needing a border isn't :(

It would be great if you could just set the border width to 0, but Power BI doesn't let you go below 1px. 

Classic Power BI :') Thankfully you can change this with a tiny change to your theme file:

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

Note that if you increase the width, you won't be able to change it back to 0 directly. Just need to click 'Reset to default' and you'll get 0 px back.


That's all :)
- Cam
