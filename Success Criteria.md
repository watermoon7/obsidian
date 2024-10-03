---
tags: turtle
---
# Turtle

1. A turtle will sufficient fuel and a floppy disk (with the code on) has a higher than 50% chance of reproducing. It should also provide it's offspring with enough fuel so that it too can reproduce. 
2. Each turtle should collect data about the surrounding blocks and send it to the central server. 
3. The turtles can query the server to calculate a route between two locations.
4. A turtle can be assigned one of the following jobs:
	1. Miner - mines for ores underground
	2. Explorer - scours the surface for resources like flowers, sugar cane, sand, logs and maps the world
	3. Farmer - harvests resources from farms, and processes the items
	4. Logistics - transports items to and from the storage system
	5. Builder - focuses on expanding farms and building structures
	6. General worker - does odd jobs such as block collection and maintenance on turtles that have run out of fuel or are unresponsive

# Central Server

1. A virtual map of the world is stored on the server.
2. The server can calculate a route between two locations by using the virtual map and a pathfinding algorithm.
3. The server can allocate priority jobs to turtles.

# Program structure

## Server

1. The server should take queries from clients and store them in a queue if the current query hasn't been completed yet
2. The server should take data from clients including: positions, jobs, block data etc.
3. The server should recognise the current tier of civilisation and delegate jobs accordingly

## Client (turtle)

1. Contains functions for all jobs
2. Contains a queue for jobs and a priority queue for priority jobs
3. Each job should be split into sub-jobs. Each sub-job must be completed before another sub-job can start. This allows large jobs to be interrupted midway through and to be restarted later. 
4. Each sub-job must have an estimated fuel cost and there must be a procedure for refuelling in different situations.
5. The turtle should contain these utility functions: orient, move, table manipulation, refuel etc.
6. The turtle should send the server it's position data and surrounding block data every time it moves
7. There should be queuing procedures in case two turtles want to go to the same position at the same time
8. Turtles should be able to request the help of others e.g. in the case of a turtle running out of fuel

# Tiers of civilisation

1. **Single turtle**
	- First the turtle will mine for resources to self replicate.
2. **First farm** 
	- Once the second turtle is born, both turtles will work together to chop down trees and build a tree farm for fuel. 
	- One of the robots will be designated as the lumberjack who tends to the tree farm, mining trees as they grow, replanting, smelting the logs, and storing the charcoal in chests and the other turtle will focus on self replication.
3. **Baby boom**
	- Now that there is stable source of fuel, the focus is on self replication.
	- All newly born turtles will work together to gather resources for self replication. 
	- One turtle will make and tend to a sugar cane farm.
4. **Infrastructure Expansion** 
	- A proper storage system will be established for ores, cobblestone, wood, charcoal, sugar cane, sand and bone meal.
	- More farms will be built for: logs, sugar cane and wheat (used in a composter for bonemeal for dye).
	- Teams of miners, explorers, farmers, builders, general workers, and logistics will be established.
5. **Colony construction**
	- Houses, shops and other buildings will be constructed as well as a perimeter wall. 
	- Paths and underground tunnels will connect the colony houses and farms together. 

# Colony

1. The colony should have a central storage area.
2. The colony should have designated areas for farming
3. The colony should have mining tunnels wide enough for multiple turtles to go up and down at once
4. There should be underground mines with refuelling stations, temporary storage areas and queuing areas. 
5. The colony should be properly terraformed, have paths and look visually pleasing (in civilisation stage 5)

# Software criteria

1. The client code must fit onto a turtle storage (without editing the config).
2. The turtle should never be idle unless idling is an intentional part of a turtle's job e.g. farming turtles waiting for crops to grow.
3. All errors in the program must be handled appropriately with procedures in case of fatal errors.