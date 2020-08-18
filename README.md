# MESL
This library is designed to create External minecraft scripts. Hence the name MESL (Minecraft External Script Library).
It is NOT a library for creating plugins or forge modifications, clients or datapacks.
The usage of this library may be against the rules of some Minecraft Servers. Use it at your own risk.


## Installation

```py
$ pip install mesl
```

## Issues

Bug / Issue reports are welcome, if you feel like reporting an issue, go ahead.


## Features
### Basic

```py
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

#
```
