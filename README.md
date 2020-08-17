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

### Examples

```py
import mesl
#Creating the MC Environment

#While doing so, Use only the version down to their decimals. Ex: 1.16 = Correct // 1.16.1 = Wrong
mc = Mc.Minecraft('1.16')


#Attacking
mc.attack(times=2, cooldown=0.5)

#Destroying
#Press time is the amount of time in secs that the player will be holding down the DESTROY/ATTACK button.
mc.destroy(times=1, pressTime = 5, cooldown = 0.5)
```
