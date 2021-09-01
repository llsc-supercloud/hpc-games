# Instructor Guide

## Learning Objectives

- Understand the concept of memory spaces
- Understand the difference between shared and distributed memory
- Develop intuition about communication and communication latency
- Recognize data distributions (cyclic, block)
- Develop an intuition for load-balancing concerns

## Game Objective

To work collaboratively, mimicking the actions of a multi-core compute cluster to create a phrase or sentence from individual data elements.

*Recommendation*:  If you have an actual program that students will be executing on your cluster it is useful to have them execute it in this game.  The experience provides something you can refer to when they work to develop and execute a parallel program.

## Student Preparation

As HPC architectures evolve, shared and distributed memory computing are joined by hybrid computing paradigms that match hierarchical hardware design.   The full Hybrid version is designed to help students develop intuition about creating applications for modern HPC systems.  

Students will get the greatest gain from this game if it placed in a context of

- System Architecture: ideally the students understand
  - The difference between a local and a remote system
  - The general concepts of
    - Multi-core processor architecture
    - Shared memory
    - Distributed memory
  - Communication networks and the idea of data moving between remote systems
    - Send/recv (traditional HPC)
    - Client/server or pub/sub
- Programming:
  - Writing data to memory (they may only know it as “save”)
  - Parallel programming paradigms - shared, distributed, hybrid
- Awareness that some problems are so big that they must be distributed so that the memory requirements are split over many computers  
- Awareness that some problems are so complex that they require multiple computers to work together to create a solution, sometimes thousands of computers (CPUs/cores)

## Game Set-up (Instructor)

Hybrid – Shared and Distributed Computing Version

### Before the event

1. Select a quote that provides each participant with at least 3 actions
2. Determine the cypher to be used to encode the quote and encode it
3. Distribute the quote across nodes and processors
   1. Whole words to nodes – block distribution
   2. Individual letters to participants – cyclic
   3. check for load balancing and re-balance as necessary
   4. create individual “packets” with the data elements
4. Create Local Memory space for each team (node)
   1. Can be a simple Google Doc (virtual) or physical piece of poster stock (in person)
   1. At the top of the Memory Space - include Node ID
   1. Format an empty table with indices to represent the data registers – must match the data lengths of each team’s (node’s) local data. 
   1. confirm that the memory space is editable for everyone (e.g. google permissions)
5. Create the Global Memory space for the final result
   1. Identify where the first element of the phrase fragment from each Node will be stored
   1. Confirm that each “section of global memory” is large enough for the data coming from a given node
   1. Confirm that the memory space is editable for the Rank 0 and viewable for everyone (e.g. google permissions)
6. Determine how the data is to be gathered
   1. Sent to instructor –alter instructions to ask lead process on node to send the local data
   1. Copied to separate Doc – alter instructions to ask lead process on node to write data to Doc

### Prior to Start of the Game

- Distribute the students into teams, where each team represents a node, e.g. a team of six people is a node with six cores.
- Give each team
  - A card with their Node number within the “world”
  - A local memory space marked with individual memory slots
- Give each participant
  - Instructions for the task
  - The decoding cypher required to complete each task
  - Process ID in the global sense (MPI rank)
  - Data: input character, local memory location where character is to be written

## Game Play

Play begins once all teams have their Node ID and “memory space”  and each participant has received a packet with their data and instructions.

The game play consists of multiple stages:

### Stage 1: Using the instructions provided and the cypher, each individual uses their data to

1. Ttake one of their rows/cards, and
1. Compute the decoded value using as input the data in the first column, and
1. “Write the result to memory” by placing it into the location indicated by the 2nd column
1. Repeat steps 1 - 3 until all rows/cards have been decoded and written to memory

### Stage 2:  The lead process for the node/team gathers the data

Once all of the work is complete, the lead process on the node

- Gathers the data from the local memory location
- Creates a “message” with the following data:
  - Node ID
  - Portion of the phrase in local memory (phrase fragment)
- Sends the “message” to the lead node according to the gather instructions provided. (note: this is based on Step 5 of the Pre-event preparation.)
- “Exits” (breakout room for virtual or sit back for in-person)

The individuals who are not the lead process

- “Exits” (breakout room for virtual or sit back for in-person)

### Stage 3: The lead process for the entire group (Rank 0)

1. Writes the “message” from node 0 into the memory space for Node 0
1. Until all messages have been received, the lead process
   1. Checks for messages from other nodes and
      1. Reads the Node ID
      2. Places the phrase fragment in the appropriate memory location

The game is complete when the full message is in memory and readable by the participants.

## Questions/Discussion

### During the first phase (small teams)

- What did you notice?
- Did you all finish at once?
- Thinking about “writing” your results to memory - how was it laid out?
- How much longer do you think this would have taken for you to complete without team members?  e.g. 2x? 3x? 6x?
- If you were the lead process on a node - what was your experience?

### During Phase 3

- The messages had Node IDs - what would have happened if they did not have Node IDs?
- Did all of the Nodes send their data in rank order (1, 2, 3, etc?) or was it random?
- Did you have to wait for data?
- How does this affect how you might use this distributed data model?

Later in the course, these questions can be revisited.  We found that they were particularly helpful when introducing MPI constructs.
