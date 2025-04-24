# Students of Watan
A variant of the famous board game **Settlers of Catan** developed in **C++** by Sherry Liu, Wayne Hao, and Yang Zhou from the University of Waterloo.  

## Game Overview
Watan is a strategy and resource management board game inspired by the classic "Settlers of Catan," set in a university-themed environment. Four players, each representing a student at the University of Waterloo, compete to be the first to achieve 10 victory points (VP). Players gather resources like Caffeine, Lab hours, Lectures, Study time, and Tutorials by strategically completing academic goals and achievements. But beware—the campus geese may occasionally overrun resources and hinder progress!

## Gameplay and Rules

### Input and Output
This is a terminal based game. All player actions are performed by typing formatted commands that can be recognized by the game into the terminal.  
<img width="724" alt="Screenshot 2025-03-13 at 14 09 25" src="https://github.com/user-attachments/assets/28125d59-d845-40ac-b31c-0f8fd27f1618" />


### Game Setup
- It requires 4 players to start the game.

- The game begins with each player choosing two initial **"Assignments"** (level 1 criteria) located at the intersections on the hexagonal tiles to complete as their starting points.

### Player Turn
- The game progresses in turns, cycling through players in this order: **(Blue → Red → Orange → Yellow)**

- On each turn, a player rolls two dice:

  - **Fair Dice**: Rolls two standard dice randomly.

  - **Loaded Dice** (not recommended): Players choose a specific roll number from 2 to 12.

### Receiving Resources
- Dice rolls determine which tiles produce resources.

- Players receive resources if they own completed criteria on the corners of the tiles that match the dice roll number.

### Resource Types
- **CAFFEINE, LAB, LECTURE, STUDY, TUTORIAL, NETFLIX.**
  
- **NETFLIX** tiles produce no resources.

### Achieving Criteria
- Criteria are vertices of the tiles.

Players must use resources to complete course criteria in the following order:  

- **Assignment** (cost: 1 CAFFEINE, 1 LAB, 1 LECTURE, 1 TUTORIAL)

  - +1 VP.
  - Grants 1x resource from adjacent tiles on dice rolls.

- **Midterm** (cost: 2 LECTURE, 3 STUDY)

  - Upgrades an assignment.
  - +1 VP (2 total).
  - Grants 2x resources from adjacent tiles on dice rolls.

- **Exam** (cost: 3 CAFFEINE, 2 LAB, 2 LECTURE, 1 TUTORIAL, 2 STUDY)

  - Upgrades a midterm.
  - +1 VP (3 total).
  - Grants 3x resources from adjacent tiles on dice rolls.  

A criterion can only be **completed** if:
- No adjacent criterion is completed, **and**
- It is either the beginning of the game, or the player has achieved a goal that is adjacent to the criterion.  

A criterion can only be **improved** if:
- The player owns the criterion, **and**
- The criterion has not been improved to an exam yet.

### Achieving Goals
- Goals are edges of the tiles.
- Achieving a goal costs 1 STUDY and 1 TUTORIAL.
- Achieving goals requires adjacent achieved goals or completed criteria owned by the same player.
- Each goal grants strategic positioning but does not directly award VP nor grant resources.

### Geese
<a href="https://www.instagram.com/geeseofuwaterloo/?hl=en">Geese of UWaterloo</a>

When a player rolls a 7:
- Players holding 10 or more resources lose half (rounded down) randomly to the geese.

- The player can move the geese onto a tile of their choice except where the geese are currently placed, blocking it from producing resources until the geese are moved away.

- The current player can steal one random resource from another player who owns achievements on that tile and has non-zero resources.

*~~'These geese are LOVELY, aren't they?'~~*

### Trading
- During the turn, players are allowed to trade resources with another player.
- One copy of resource at a time, but as many times as they wish!

## Run the Game

In your command line tool, run
```bash
git clone https://github.com/CodingGhoost/Watan.git
cd Watan
```
### Windows
Run `watan.exe` from the root directory.

### MacOS and Linux
Choose a 'watan' executable that matches your operating system, and run
```bash
chmod +x ${name_of_your_executable}
./${name_of_your_executable}
```
You can add the "-bonus" flag for enhanced features and visuals (highly recommended!).  
```bash
./${name_of_your_executable} -bonus
```

## Save and Load    

If you need to be away during a game, you can save the game and come back later.  
In an on-going game, run 
```bash
save <fileName>
```
to generate a save named "fileName.sv"  

When running the game, run
```bash
./${name_of_your_executable} -load <fileName>.sv
```
to load a save.  

<h1 align="center"><strong>Have Fun!</strong></h1>


*Credits to Professor Godfrey, Professor Lushman, Professor Schmitz, and all CS246 Fall 2024 ISAs for the game rules and design guidelines.*  
  
Due to Policy 71 at UWaterloo, we are not allowed to post the source code of the game. *~~althought we really goddamn want to!~~*  
However, feel free to have a look on our UML design of the game :D  [uml.pdf](https://github.com/user-attachments/files/19881616/uml-final.pdf)

