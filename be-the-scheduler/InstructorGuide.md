# Instructor Guide

## Learning Objectives

- Understand role of scheduler
- Develop intuition about how resources are allocated
- Review scheduler commands
- Understand the range of job types and resources required by each
- Understand resource difference between distributed and shared memory

## Game Assembly

To create the distributed jobs, take the distributed job bricks (the ones with the holes in them) and group them into 4 and 8 piece groups. These correspond to jobs with 4 or 8 ranks/processes, respectively. In each group tie pairs together with yarn or cord, and then tie sets of pairs together in the middle of the yarn or cord to create the 4 and 8 piece groups. If you find your knots want to come apart you can use some tape to keep them together. I've found electrical tape to be great for this.

Print out the game cards on business card paper or cardstock and cut out the cards. If using the Map Reduce cards clip corresponding cards together with paper clips.

Place the node pieces on the game board. You'll want enough of a gap between nodes to demonstrate they are separate, but they should be close enough that individual tasks of distributed jobs can be placed on different nodes.

## Student Preparation

Students should be introduced to the concept of a job scheduler and the different types of jobs used in the game. The game can be made easier or simpler by using fewer job types. The should know the difference between a node, a core, and a cluster. This game was created with current and future users of an HPC system in mind, but could be played as a demonstration to a broader audience with more help from instructors.

## Game Play

**Setup:** Place the board on a table with space for two lines, or queues, of cards below it. Draw 6 cards and “start” them by selecting corresponding pieces and placing them on the board according to the instructions below for each job type. As they start, place the cards back, or job status, side up in the top “Running” Queue. If any Map/Reduce jobs are selected, the Map job should be placed on the board and that card placed in the Running Queue, the Reduce job should be placed in the bottom “Pending” Queue. This does not have to be done in turns. For any jobs remaining in the Pending Queue, select their corresponding pieces and place them on the card.

Players take turns being the scheduler until there are no more job cards. In each turn, the player should:

1. **Clean up completed job:** Roll a die. The number on the die is the job that has completed. Count down the Running Queue to select the job that has completed, remove the corresponding pieces from the board (if there are multiple jobs of the same type don’t worry about selecting the exact right pieces, as long as they match the card), and place the card in the discard pile. Move the cards to the right of the completed job to fill in the empty space. If there is no card in the position corresponding to the die, continue to step 2.
2. **Start new jobs:** Draw a card and place it at the end of the Pending Queue. Select the corresponding job pieces for the drawn card and place them on the card. Then, starting at the beginning of the Pending Queue, start as many new Jobs as you can. To start a job, place the job pieces on the board and pick up the card from the pending queue. Turn the card over and place at the end of the Running Queue and place the pieces on the board. Each Job Type has rules about how/when/where it can run:
   - **Job Array:** Select the number and type of pieces matching the card. These pieces can be placed anywhere on the CPU nodes, they do not have to be on the same node. Not all pieces must be placed at once (put remaining pieces on the card and leave card in the Pending Queue).
   - **Map/Reduce:** The Map Step is scheduled like a Job Array. The Reduce Step cannot start until corresponding Map Job has completed. The card remains in the pending queue until every task in the Map Step has completed.
   - **Shared/Large Memory:** Select the piece corresponding to the number of cores in the Shared/Large Memory job (both the 2x2 and 1x4 pieces can be used for 4 core jobs). Each piece can be placed on only one node (cannot go across multiple nodes).
   - **MPI/Distributed Memory:** Select a cluster that matches the number of tasks on your card. Individual tasks can be placed on different nodes, as they are connected and can communicate over the network.
   - **GPU:** Select a GPU Job piece and place on a GPU node. Each job takes half the node.
When no more jobs can be run the turn is over.

## Questions/Discussion

- Did any interesting situations come up?
- Did you notice any jobs types sitting in the Pending Queue for a particularly long time? Why do you think that is?
- What are the reasons a job might be in the Pending Queue?
