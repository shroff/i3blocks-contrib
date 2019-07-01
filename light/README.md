# light

Shows the current screen brightness.

Scrolling on the block changes the brightness. Right click resets to lowest, left click increases.

# Usage

This block can be run on an interval or by signal. To run the block using a
signal, it is recommended to add the following to your i3 config.

```
# change volume or toggle mute
bindsym XF86MonBrightnessUp exec light -A 10 && pkill -RTMIN+11 i3blocks
bindsym XF86MonBrightnessDown exec export MIN=$(light -P) && light -N 1 && light -U 10 && light -N $MIN && pkill -RTMIN+11 i3blocks
```

where the number `11` in `-RTMIN+11` can be replaced to another signal number,
as long as it agrees what you put for `signal=` in your i3blocks config.


# Config

```
[light]
#label=
label=BRI 
interval=once
signal=11
#STEP=5
```
