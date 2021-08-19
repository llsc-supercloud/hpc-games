# Instructor Guide

## Learning Objectives

- Understand the difference between local and global memory/view from processor perspective
- Understand the difference between shared and distributed memory from an application perspective

## Materials

- 30 piece puzzles for Shared Memory, one puzzle per group
- 100 piece puzzles for Distributed Memory, at least two puzzles to show different distributions
- Zip top bags to hold distributed puzzle pieces
- Cardboard to transport partially-assembled puzzles

## Preparation

Before class, an instructor should measure the time it takes to complete each puzzle ahead of time to get the Serial time for assembling the puzzles. For reference, our 30 piece shared memory puzzle took roughly 7 minutes for a single person to assemble, and the 100 piece distributed memory puzzle took roughly 20-25 minutes.

Distribute the distributed puzzle. One is distributed with a block distribution, the other cyclic. Use one zip top bag for each processor/rank and place the pieces in the bag along with a piece of paper listing the distribution type, process ID, and total number of processes. For example: "Block Distribution; PID 0 of 4 processes".

## Game Play

Game play consists of two rounds: one for shared memory, one for distributed.

### Shared Memory

Break the students into groups of ~4 and have them each work on a puzzle for 10 mins.  Have each group time how long it takes.
At the end of 10 minutes assess the level of “done-ness” to get an estimate of time to complete the puzzle, if not already completed.

#### Shared Memory Questions/Discussion

- Would the puzzle have been completed faster if you had fewer workers?
- Would the puzzle have been completed faster if you had more workers?
- What were the challenges?

### Distributed Memory

#### Instructor Overview

- Explain that we will now build a puzzle using a distributed memory model
- Explain the teams and goal (complete puzzle)
- Note: 4 pairs/puzzle, 1 puzzle is block distributed and 1 is cyclic
- Note: 20-25 minutes for one person to complete puzzle

#### Complete the Puzzle

- Students work in pairs
- Each pair gets a bag of puzzle pieces (chunk)
- Students complete puzzle

#### Distributed Memory Questions/Discussion

- What were the challenges?
- Did you have enough information?
- What information did you need to get ahead of time or learn for yourself?
