# MESL

## This library will be rewritten soon.
### If you are looking solely to interact with the in-game chat, look into https://github.com/MrKelpy/PyMChat

This library is designed to create External Minecraft Scripts. Hence the name MESL (Minecraft External Script Library).
It is NOT a library for creating plugins or forge modifications, clients or datapacks.
The usage of this library may be against the rules of some Minecraft Servers. Use it at your own risk.

The library works on all OS's.
The library is fully configurable, you can change the feature keybinds/functions accordingly to your in-game settings, using config.py.

Latest Version: 1.6

WARNING:
Versions lower than 1.4 might be unstable and incomplete; Some of their features are broken and might not work.
Versions lower than 1.3.1 were removed due to complete unstability.

## Installation

```py
pip install meslib
```
PyPi: https://pypi.org/project/meslib

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
#"spring" declares whether you will be sprinting or not.
mc.walk(direction = str, blocks = int, seconds = float, sprint = bool)

#Jumping
mc.jump(direction = str, times = int, cooldown = float, sprint = bool)

#Hold Shift
mc.hold_shift()

#Release Shift
mc.unshift()

#Shift
#"sneaktime" is an alias for "pressTime"
mc.shift(times = int, sneaktime = float, cooldown = float)

#Open MC's Window
#This is used to open the Minecraft Environment. (If it is closed after created)
mc.goto_mc()
```

### Inventory

```js
#Opening Inventory
mc.inv()
OR
mc.inventory()

#Selecting slots
#The library offers a general mapping of all slots in Minecraft, including container and inventory slots.
mc.slot(slotType = SlotNumber)
'''Available Mapped SlotTypes: invslot = None, doubleinv = None, armor = None, craft = None, shield = None, brewing_stand = None, grindstone = None, cartography = None, dropper = None, enchant = None, furnace = None, crafting_table = None, anvil = None, chest = None, doublechest = None, smithing_table = None, shulker = None, dispenser = None, blast_furnace = None, smoker = None'''

#Switching Hotbar
#Hotbars are mapped from 1-9 respectively
mc.hotbar(slot=slot)

#Dropping Items
#"whole", when set to True, drops the whole hotbar.
#"amount" drops the specified amount of items in the hotbar.
mc.drop(whole = Bool, amount = int)

#Send item to Hotbar
#"dest" is the destination (In the hotbar) for the selected item to go to.
mc.sendtohotbar(dest = int)

#Picking/Placing the item
#"relative" Changes the action of left clicking to pick the whole slot up/placing the whole slot up, to the right click action, doing it relatively to the amount of items in the slot.
mc.pickplace(relative = Bool)

#Swap Hands
mc.swap_to_offhand()
```

### Chat

```js
#Understanding Affirmations
'''Affirmations are the objects of the chat messages. All the chat messages are returned in the form of Affirmation Objects. 
You can retrieve "author", "text", "msg" and "id" from an Affirmation.

affirmation = mc.getchat(limit = 1) 
- This returns the last chat message in the form of an Affirmation Object. If you set the limit to anything other than 1, it will return a list with Affirmation Objects (Representing the messages). (Unless you set the limit to 0, in which case it'll return None.) -
 
Let's say the message is: "<ComradeElmo> Hello world!"


The library will parse the data from the message, and will return it in the form of an Affirmation Object. You can then retrieve that data with, (based on the example above):


affirmation.author = 'ComradeElmo'
affirmation.text = 'Hello World!' 
affirmation.msg = "<ComradeElmo> Hello world!"
affirmation.id = The message ID. This ID is static, meaning, it will not be changed. Each message has an unique ID.'''
NOTE: Affirmations do not contain color codes.

#Getting the Chat
#"limit" is the limit of messages to get from the chat. The first message returned is the last message.
#This function returns the last chat message in the form of an Affirmation Object. If you set the limit to anything other than 1, it will return a list with Affirmation Objects (Representing the messages). (Unless you set the limit to 0, in which case it'll return None.)
#DEFAULT - limit : 20
#If the limit is set to None, it'll return all the messages.
message = mc.getchat(limit = int)

#Sending a message
#This will clear the chat and send a message.
mc.say(text = str)
```

### Config
```css
"""|CONFIG--------------------------------------------------------------------------|
Feel free to change the values accordingly to your in-game settings.
DO NOT CHANGE THE VARIABLE NAMES."""

MOVE_FORWARD = 'w'
MOVE_BACKWARDS = 's'
MOVE_RIGHT = 'd'
MOVE_LEFT = 'a'
ATTACK = 'left' #Attack or Destroy
USE = 'right' #Or Place Block
JUMP = 'space'
CROUCH = 'left_shift'
SPRINT = 'left_ctrl'
OPEN_CHAT = 't'
OPEN_INVENTORY = 'e'
DROP = 'q'
WHOLE_DROP = 'ctrl+q'
INVERTED_MOUSE = False
HOTBAR_SLOT_1 = '1'
HOTBAR_SLOT_2 = '2'
HOTBAR_SLOT_3 = '3'
HOTBAR_SLOT_4 = '4'
HOTBAR_SLOT_5 = '5'
HOTBAR_SLOT_6 = '6'
HOTBAR_SLOT_7 = '7'
HOTBAR_SLOT_8 = '8'
HOTBAR_SLOT_9 = '9'
SENSIBILITY = 100
SWAP_OFFHAND = 'f'
CHAR_BEFORE_NAME = '<'
CHAR_AFTER_NAME = '>'

#|CONFIG-END---------------------------------------------------------------------------------|
```
