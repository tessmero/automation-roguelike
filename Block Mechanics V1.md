# Block System

* a block occupies a single square tile on the map
* there are a small number of unique blocks
* there is no upgrading blocks, and no upgraded versions of blocks
* progression involves using more blocks (e.g. designing scalable modules)

# Shooter Block

The shooter block is the most basic/common type of block. It is used for many purposes throughout the entire game. When a shooter block is placed, the player chooses its orientation (one of the four cardinal directions). Normally, a shooter block fires one projectile per second. The projectile moves in a straight line. Projectiles may have a limited range.

In the beginning of the game, enemies are slow enough that they can be reliably damaged by a single well-placed shooter block.

The shooter blocks projectiles may be able to damage and eventually break some solid blocks. This could be used to access new areas if the map.

## Progressing using Shooter Blocks

Other, more lucrative uses for shooter blocks involve directing them towards other blocks. As the game progresses, this will be necessary to survive.

When a shooter block is hit by a projectile, it consumes that projectile and then fires another projectile. This does not interfere with the shooter blocks 1-second recharge timer, and so this way a single shooter block may fire more than one round per second. However there is an upper limit to the number of projectiles fired by a single block (e.g. 10/sec).

# Money Block

The money block gives the player 1 unit of currency each time it is hit by a projectile. There are only 4 faces that can be hit at once, meaning that there is an upper limit to the rate of a single money block.

# Modules

The design of the block system allows for elegant modules.

One money block and eight shooter blocks can be placed in a spiral shape that pefectly fills a 3×3 space and produces 8 currency per second. This design can be extended by adding more shooter blocks.

Two shooter blocks facing the same direction act like a single shooter block that fires twice per second. More shooter blocks may be stacked to inprove the rate of fire to some extent. This type of module could be used to destroy early- or mid-game enemies, but would eventually become obselete.

Two nearby shooter blocks that are directed towards eachother will create a feedback loop. They will quickly begin firing at the maximum possible rate. Any enemies passing between the shooters will be hit repeatedly. Again, this strategy alone will not be sufficient to defeat late-game enemies.


