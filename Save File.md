
This document describes how the infinite tile-based game map is saved permanently. It goes without saying that the save file also contains the player's position, status, and inventory.

The map is a grid of square tiles. The starting game map has a fixed overall layout and some fixed regions. The rest of the map is populated with procedural elements. So, the unmodified map can be represented by just one RNG seed number.

In order to handle modifications to the map (including contraptions added to the map), a chunk system is used. The map is divided into equal-sized square chunks. The save file contains an index of the chunks that have been modified, and then a compressed representation of those modifications. 

For tiles that have been modified by the player, the exact block layout is permanently stored. The design of the building system allows for block layouts to be stored in a highly compressed way.
* There are a small number of unique blocks. Each type of block could be stored as a separate "layer" in which each tile is represented as a single bit (then compressed).
* Large contraption layouts are made up of repeated modules. 
* Large modified regions (modified by contraptions) are homogenous and rectangular.
