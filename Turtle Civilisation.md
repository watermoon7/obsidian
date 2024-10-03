---
tags:
  - project
  - gaming
  - coding
---
The Turtle Civilisation Project (TCP) is a project aiming to simulate a civilisation being built up from a single autonomous robot. Using Minecraft as the simulation environment, a turtle (autonomous robot) will gather resources, reproduce, and build structures based on an algorithm.

# Links
[[Success Criteria]]
[[Design of the program]]
[[Research Information]]
[[Testing]]

# Overview of the project details

## Environment

A Minecraft world is a simple recreation of Earth including different biomes, plants animals, caves and ores. The world is split into a rigid grid of 'blocks' representing 1x1m areas.

This environment is non hostile and static. Blocks can only be placed and destroyed by turtles and there are no predators.

## Turtles

A turtle is a robot that interacts with the world. It can hold two items to be used as peripherals and has 16 inventory slots. A turtle can:
- Move forwards, backwards, up and down
- Turn left or right
- Dig blocks forward, up or down
- Place blocks forward, up or down
- Drop items forward, up or down
- Manipulate items in its inventory (select an item slot, move items, get item count)
- Detect a block forward, up and down
- Attack entities forward, up or down
- Get the fuel level
- Refuel using fuel in its inventory
- Equip peripherals
- Get information about the blocks forwards, up and down

## Simulation 

The simulation will take place in a Minecraft world over a large chunk loaded area.
The simulation will start with a fully fuelled turtle containing a disk drive and a floppy disk (with the code).
The turtle will be placed on the surface in a forest biome to give it the best chance of reproducing early on. 

## Tiers of civilisation

1. **Single turtle**
	- First the turtle will mine for resources to self replicate
2. **First farm**
	- Once the second turtle is born, both turtles will work together to chop down trees and build a tree farm for fuel. 
	- One of the robots will be designated as the lumberjack who tends to the tree farm, mining trees as they grow, replanting, smelting the logs, and storing the charcoal in chests. 
3. **Baby boom**
	- Now that there is stable source of fuel, the other turtle will focus on self replication.
	- All newly born turtles will work together to gather resources for self replication. 
	- One turtle will be assigned to create and tend to a sugar cane farms
4. **Infrastructure Expansion**
	- A proper storage system will be established for ores, cobblestone, wood, charcoal, sugar cane, sand and bone meal
	- More farms will be built for: logs, sugar cane and wheat (used in a composter for bonemeal for dye)
	- Teams of miners, explorers, farmers, builders, block collectors, maintenance and logistics will be established.
5. **Colony construction**
	- Houses, shops and other buildings will be constructed as well as a perimeter wall. 
	- Paths and underground tunnels will connect the colony houses and farms together. 

## Program main functions

>1. Self replication

To self replicate, a turtle needs these three items: 
- A new floppy disk to copy the code to
- A disk drive to access the floppy disk
- Another turtle


In total, a new mining turtle needs:
14 cobblestone, 7 raw iron, 6 sand, 4 redstone dust, 3 sugar cane, 3 logs, 3 diamonds, and 1 dye (any colour).
It will also need sufficient fuel to power the newly born turtle as well as itself.

The steps to self replication are:
1. Gather logs on the surface
2. Mine underground for coal, redstone, gold and diamonds
3. Scour the surface for sugar cane, sand and flowers

Throughout these actions, the turtle will constantly be observing the surrounding blocks for resources. For example, if, when mining underground, the turtle detects lapis, it will use this as a substitute for the dye. 

The turtle will also prioritise coal and logs as these resources can be used as fuel.

>2. Mapping and communicating

Every time a turtle moves, it will inspect the blocks around and send the information to the server. This data will be used to build a virtual map of the visited surroundings which can be used for pathfinding.

There will also be a communication system between turtles through the server. The server can send out jobs to turtles who will periodically check for job requests from the server. 

>3. Resource management

Turtles will work together to gather resources and will allocate their time to jobs that will better the species rather than themselves. 

Once the population reaches a certain size, teams of turtles will work on different larger goals such as exploring, mining or farming. 

>4. Building

Turtles will be able to build complex farms and structures from predefined structure files. This function will work best when there are teams of turtles to build, collect blocks, and farm for fuel simultaneously.




