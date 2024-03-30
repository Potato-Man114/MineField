# Executive Summary

This game is a conceptual clone of MineSweeper, with the major difference being a hexagonoal grid instead of a cartesian grid.

The player's goal is to identify the location of every mine on the board. This is done by either marking the location of all mines or clearing all non-mine spaces. Each space on the board displays information about the number of mines that are adjacent to that space, allowing the player to reason the location of each mine.

## Game Concept

The game is nearly identical to MineSweeper. Differences include a hexagonal grid and marking spaces with mines is optional.

## Genre

- Arcade
- Puzzle
- 2D

## Target Audience

- People who enjoy simple arcade games
- My dad

## Project Scope

This project should take no longer than one month to complete. Without the added pressure of a hackathon or game jam, and while still needing to work on school, work, and life, there will only be about three real days (~36 hours) to spend on this project. However, it is a simple concept. The MVP for the project is to completely implement all items in the [Mechanics](#mechanics) section of this document that are not marked as `Extra`.

# Gameplay

## Objectives

The player wins in one of two ways:

- Marking all spaces containing mines. The player cannot mark more spaces than there are mines.
- Revealing all spaces not containing mines. If the player reveals a space with a mine, the player loses.

## Game Progressions

There are no levels in this game. Instead, the player is given control over the difficulty of the game through the menu. 

## User Interface

### Menuing

Each of the following menus/screens presents the players with at least the following options

- [ ] Main Menu
  - [ ] Start Game
  - [ ] Controls
  - [ ] How To Play
  - [ ] Credits
- [ ] Start Game
  - [ ] Difficulty Select
  - [ ] Field Size Select
  - [ ] Play!
- [ ] In-Game "Pause" menu
  - [ ] Reset Current Field
  - [ ] New Field
  - [ ] How To Play
  - [ ] Quit to Main Menu
- [ ] Controls
  - [ ] Back to main menu
- [ ] How To Play
  - [ ] Back to Main Menu (when navigated from Main Menu)
  - [ ] Return To Game (when navigated from pause menu)

### In-Game Interface

The player is shown their remaining number of flags (initialized to the number of mines in the field)

The player uses the mouse to select a space. Based on the currently connected input device, the top of the screen shows what button to push for each of the following options:

- Clear Space
- Mark/Unmark

### Controls

- Clear Space
  - Mouse
    - Left Click
  - Keyboard
    - Enter
    - Shift + Space
  - Controller
    - Button "A"
    - Left Trigger
    - Left Bumper
- Mark/Unmark Space
  - Mouse
    - Right Click
  - Keyboard
    - Space
    - Shift + Enter
  - Controller
    - Button "A"
    - Left Trigger
    - Left Bumper
- Navigation
  - Controller
    - D-Pad
    - JoyStick
  - Keyboard
    - WASD
    - Arrow Keys

### Game Board Navigation

When playing without a mouse, the player must manually navigate the field. Horizontal navigation is intuitive. Vertical navigation is trickier due to the hexagonal board. Vertical movement is handles as follows:

The game keeps track of whether or not to move to the left or right space when moving vertically. Upon vertical movement, this is alternated. Upon horizontal movement, this is reset to "left". This gives the effect of moving straight up or down the board with multiple consecutive vertical movements. When the current movement left or right is not possible, i.e. on the edge of the board, the other is performed and the cuurrent movement target is unchanged, giving the effect of moving along the edge of the board.

# Mechanics


## Game Board

Within the game, the game board will be refered to as the Field. The game board is a hexagonal grid. The size of the grid is selected by the player from predefined 16:9 options. These options are as follows:

- Small (TODO: TBD)
- Medium (TODO: TBD)
- Large (TODO: TBD)
- Extra Large (TODO: TBD)

Additionally, the player has control over the difficulty of the board, which determines the relative number of mines that will be spawned

- Easy (TODO: TBD%)
- Medium (TODO: TBD%)
- Hard (TODO: TBD%)
- Impossible (TODO: TBD%)

Each space has the following properties:

- [ ] AdjacentMines
  - Describes the number of mines adjacent to the space
- [ ] IsRevealed
  - Desribes whether the space has been revealed. Cannot be undone.
- [ ] IsMine
  - Describes whether there is a mine on this space.
- [ ] Neighbors
  - Contains references to each heighboring space.
- [ ] IsMarked
  - Descirbes whether the space has been markded/flagged.


## Clearing Spaces

A space is cleared based on player input. A cleared space is visibily different than an uncleared one. If a cleared space has 0 adjacent mines, all uncleared adjacent spaces are also cleared. This is done recursively. If a cleared space has adjacent mines, that number is shown. If a marked space is cleared, that mark dissapears. If a cleared space contains a mine, the player loses.

## Marked Spaces

A space is marked based on player input. If the space is unmarked, it becomes marked. If the space is marked, it becomes unmarked. If there are as many marks as there are mines, no marks can be placed until marks are removed.

## Player Defeat

The player is defeated when their clear a space containing a mine. Upon player defeat, they are shown the lcoations of all mines (all spaces are cleared). Then, They are given the option to return to the main menu or play again with the current settings.

## Player Victory

The player wins when all spaces without mines are cleared or all spaces with mines are marked. Upon player victory, they are congradulated and asked to play again with the same settings or return to the main menu.

## Score

There is no score. The player is shown an incrementing timer as the game progresses, then told how long the game lasted upon victory/defeat.

## Difficulty Control

The player sets the difficulty from the menu before starting a game. See [Game Board](#game-board).

## Field Size Control

The player sets the size of the field from the menuu before starting a game. See [Game Board](#game-board).

# Assets

## Sprites

The following items need sprites

- Field Spaces
- Mines
- Marks/Flags
- Numbers

## Particle Effects

Particle effects should exist for the following events:

- Mine revealed (player defeat)
- Game Won!

## Audio

Sounds effects should exist for the following events:

- Clearing a space
- Marking a space
- UnMarking a space
- Player Victory
- Player Defeat
- Menu Select

Background music should also exist.

## Fonts

TODO: TBD

## Other

The following additional assets need to be created

- Game Icon
- Splash Screen