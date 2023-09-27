```
object.setToolTip("Your text here")

if object.tooltip_is_nothing:
  try:
    # wrap them inside <font> element
    object.setToolTip("<font color=\"blue\">Your text here</font>")
  except:
    # accept the fate
```
