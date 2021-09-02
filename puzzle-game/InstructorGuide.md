# Instructor Guide

## Learning Objectives

- Understand the difference between local and global memory/view from processor perspective
- Understand the difference between shared and distributed memory from an application perspective
- Learn about data distributions

## Materials

- 30 piece puzzles for Shared Memory, one puzzle per group
- 100 piece puzzles for Distributed Memory, at least two puzzles to show two different distributions (block and cyclic)
- Zip top bags to hold distributed puzzle pieces
- Cardboard or similar to transport partially-assembled puzzles

## Preparation

Before class, an instructor should time themselves completing each puzzle ahead of time to get the Serial time for assembling the puzzles. For reference, our 30 piece shared memory puzzle took roughly 7 minutes for a single person to assemble, and the 100 piece distributed memory puzzle took roughly 20-25 minutes.

Distribute the distributed puzzles. At least one is distributed with a block distribution, the other cyclic. Complete each puzzle to distribute. For block take contiguous columns, for example, if there are 10 columns make 4 chunks: columns 1-3 are in the first chunk, 4-6 in the second, 7-8 in the third, and 9-10 in the fourth (see Block_Distribution.png). For cyclic take columns one at a time, for 10 columns, columns 1,5,9 are in the first group, 2,6,10 are in the second, 3,7 in the third, and 4,8 in the fourth (see Cyclic_Distribution.png). Use one zip top bag for each processor/rank and place the pieces in the bag along with a piece of paper or index card listing the distribution type, process ID, and total number of processes. For example: "Block Distribution; PID 0 of 4 processes".

Note that the numbers and sizes of groups were determined based on a class size of around 16. For more or fewer students these numbers may need to be adjusted. You will want to have a general idea of how many students you expect so you can appropriately distribute the pieces ahead of time. The Shared Memory puzzle requires less planning, other than knowing how many puzzles to have.

## Game Play

Game play consists of two rounds: one for shared memory, one for distributed.

### Shared Memory

Break the students into groups of ~4 and have them each group work together to complete a puzzle for 10 mins.  Have each group time how long it takes to complete.
If using a more complicated puzzle, have everyone stop after 10 minutes and assess the level of “done-ness” to get an estimate of time to complete the puzzle, if not already completed.

#### Shared Memory Questions/Discussion

- Would the puzzle have been completed faster if you had fewer workers?
- Would the puzzle have been completed faster if you had more workers?
- What were the challenges?

### Distributed Memory

Break students up roughly into pairs with 4 pairs for each puzzle. Give each pair of students a bag of pre-distributed puzzle pieces. Explain to the students that they should complete their portion of the puzzle, and then bring it to PID 0 for their distribution, who will join each part together. To transport the completed portions, gently slide them off the table onto cardboard or similar portable surface and walk to PID 0. Once the students understand the task, start the timer and tell them to begin. Note down the time when each puzzle is completed.

The students will likely run into some challenges: some groups completing their portion slower than others, time spent gently carrying the completed portions, dropped pieces, etc. These are all teachable and correspond to challenges with running parallel programs on distributed systems. Living out these challenges is part of the exercise.

#### Distributed Memory Questions/Discussion

- What were the challenges?
- Did you have enough information to complete the puzzle?
- What information did you need to get ahead of time or learn for yourself?
