# Automation Roguelike

This is a top-down, 2D, action roguelike with an emphasis on building automatic contraptions out of blocks. In order to progress, the player must design contraptions for the purposes of exploration, combat, and producing resources over time. 

Contraptions can be infinitely scaled up by duplicating modules. 

Time can be fast-forwarded, and there is no advantage to running the game AFK like an idle game.



## Gameplay Features

The player moves around the map (top-down view) with WASD and aims with the mouse.

The game features an inifite open-world map with a mixture of fixed and procedural elements. However the game starts in an enclosed "main dungeon" area. The main dungeon is composed of distinct stages which normally can only be accessed in order. The stages are mostly surrounded by solid blocks which are difficult to get through. A normal playthrough of the game ends when the player completes the final stage in the main dungeon.

In order to progress, it is practically necessary to design modules composed of many interacting blocks, which that can be duplicated and combined to form large factories. The player will use the mouse to place blocks and form modules. Then they can click-and-drag to select a rectangular region of blocks and create a schematic. A schematic can be used to automatically build an identical module in another location. This way the player can easily scale-up their factories as long as they have enough space and building materials.


### Stage Time Limit

The player has a limited time on each stage, but the time limit is very long. Normally when the timer runs out, the player is automatically transported to the next stage and the timer resets. A normal playthough ends on the last stage of the main dungeon, but it may possible to keep reseting the timer and continue playing.

After the area nearby the player has been cleared of offensive enemies. The player has the option to fast-forward time to let contraptions run until the stage timer runs out. 

The stage time not meant to restrict the player's play time. Also, the player will learn to explore outside and between stages, and they are never truely restricted to one area of the map. The real purpose of the stage timer is to:
* limit fast-forwarding
* force the player to confront increasingly difficult enemies


### Exploration

The player is free to move infitely in any direction. But to do so they may have to build platforms or break solid blocks, which takes a long time. Exploring in any given direction will eventually lead to special areas with extra space, new threats, and permanent powerups for the player (some random and some fixed). After gaining knowledge of the overall map layout, Players will learn to invest in long-term expeditions using contraptions.

For example, a player might choose to construct a tunnel-digging contraption on stage 1 to dig a tunnel to stage 2. The stage 1 timer would run out before the tunnel is complete. But, later in the game, that player could freely move between stages 1 and 2. 


### Combat

In each stage of the main dungeon has increasingly dangerous enemies which are spread throughout the stage. Some enemies are offensive and will target the player and their contraptions. Once the stage time runs out, the stage is considered "secured" and offensive enemies will disapear from the stage forever. Stationary enemies will always remain on that stage and may still become aggressive when approached by the player.

Players may choose to seek out enemies or play defensively.


### Production

Players must invest some resources into producing more resources later.

The HUD allows players to see how much their contraptions are producing, and how much they will have produced by the time the stage timer expires. Any resources produced will not be available to the player until the start of the next stage. This way there is no reason to AFK.


## Technical Features

Contraptions are always persistent. Any number of off-screen contraptions can be accurately simulated in constant time and constant RAM. Continuous integration tests ensure that the off-screen simulation always matches the on-screen simulation.

The design of the building system ensures that the effect of any contraption over time can always be described by a few numbers, and those numbers add together with other contraptions. So, when more contraptions are built, the game doesn't have to remember more numbers. It just has to remember bigger numbers. Fast-forwarding time just means multiplying numbers.

Contraptions are made up of blocks. Blocks may produce and/or consume resources at a fixed rate, but they cannot permanently contain anything. Ultimately only the player can hold resources. 

Any set of blocks that are interacting form a contraption. That contraption may:
* add resources to the player
* interact with enemies
* modify rectangular regions of the map

Enemies are only simulated in some regions of the map (e.g. nearby the player), so only a limited number of contraptions can possibly interact with enemies at any time. Similarly, contraptions' modifications to the map are only considered when the player is nearby the effected regions.
