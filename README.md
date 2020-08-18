# MESL
This library is designed to create External minecraft scripts. Hence the name MESL (Minecraft External Script Library).
It is NOT a library for creating plugins or forge modifications, clients or datapacks.
The usage of this library may be against the rules of some Minecraft Servers. Use it at your own risk.

The library is fully configurable, you can change the feature keybinds/functions accordingly to your in-game settings, using config.py.


## Installation

```py
$ pip install mesl
```

## Issues

Bug / Issue reports are welcome, if you feel like reporting an issue, go ahead.


## Features
### Basic

```js
import mesl

#Creating the MC Environment
#While doing so, Use only the version down to their decimals. Ex: 1.16 = Correct // 1.16.1 = Wrong
mc = Mc.Minecraft('primary.secondary')
#Available from ALPHA - 1.16


#Attacking
#"times" is the amount of times the user will be repeating the task.
#"cooldown" is the amount of time in seconds that the user will wait between tasks.
mc.attack(times = int, cooldown = float)

#Destroying blocks
#"pressTime" is the amount of time in secs that the player will be holding down the button to perform the task.
mc.destroy(times = int, pressTime = float, cooldown = float)

#Placing blocks
mc.place(times = int, cooldown = float)

#Using containers, items, blocks
mc.use(times = int, pressTime = float, cooldown = float)

#Walking
#"direction" is the direction the player will walk. Since there is no "turn" feature, all directions are implemented.
#Allowed Directions : 'fwd': MOVE_FORWARD, 'forward': MOVE_FORWARD, 'front': MOVE_FORWARD, 'bwd': MOVE_BACKWARDS, 'backwards': MOVE_BACKWARDS, 'back': MOVE_BACKWARDS,'right': MOVE_RIGHT, 'left': MOVE_LEFT
#"blocks" is the amount of blocks the player will walk in a certain "direction" (OPTIONAL)
#"seconds" is the time in seconds the player will talk in a certain "direction" (OPTIONAL)
mc.walk(direction = str, blocks = int, seconds = float)

#Jumping
mc.jump(direction = str, times = int, cooldown = float)

#Hold Shift
mc.hold_shift()

#Release Shift
mc.unshift()

#Shift
#"sneaktime" is an alias for "pressTime"
mc.shift(times = int, sneaktime = float, cooldown = float)

#Swap Hands
mc.swap_to_offhand()```


