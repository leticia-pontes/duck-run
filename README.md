# Duck Run — LCD-Based Endless Runner

**Duck Run** is an endless runner game inspired by the Chrome Dino game, developed in C for the **PIC18F4550 microcontroller**.

The game runs on an LCD display, where a duck must dodge randomly generated obstacles (rocks) by moving between the display's four rows. Players control the duck using a 4x4 matrix keypad. If the duck collides with a rock, the game ends and displays a **Game Over** message.

## Features

- Custom LCD characters for the duck and obstacles.
- Four-row movement system.
- Random obstacle generation.
- Real-time obstacle movement.
- Collision detection.
- Keypad-based player controls.
- Game Over state.

## Hardware Requirements

- PIC18F4550 microcontroller.
- LCD compatible with the `lcd.h` driver.
- 4x4 matrix keypad.
- Microcontroller support library (`xc.h`).

## Project Components

### Source Files and Libraries

| File | Description |
|---|---|
| `config_4550.h` | PIC18F4550 microcontroller configuration |
| `atraso.h` | Delay functions for timing operations |
| `lcd.h` | LCD display control functions |
| `16Keys.h` | 4x4 matrix keypad input functions |

### Core Functions

| Function | Description |
|---|---|
| `special_char()` | Creates and stores custom LCD characters, such as the duck and rocks |
| `print_special_character()` | Displays a custom character at a specified LCD position |
| `lcd_pos()` | Calculates LCD positions based on row and column coordinates |
| `get_random_line()` | Generates a random row for obstacle placement |
| `init_pedras()` | Initializes obstacle positions and game states |
| `launch_pedra()` | Spawns a new rock at a random row on the right side of the display |
| `move_pedras()` | Moves obstacles from right to left across the display |

## Player Controls

The duck can move between the four rows of the LCD using the matrix keypad.

| Key | Action |
|---|---|
| `A` | Move up |
| `B` | Move down |

## How to Play

1. The game starts with the duck positioned on the third row of the LCD.
2. Press `A` to move the duck up.
3. Press `B` to move the duck down.
4. Rocks appear randomly on the right side of the display and move toward the left.
5. Avoid colliding with the rocks to keep playing.
6. If a collision occurs, the game displays **Game Over!**.

## Game Loop

The main game loop follows these steps:

1. Initialize the LCD and display the duck on the third row.
2. Generate obstacles at random positions.
3. Move existing obstacles from right to left.
4. Read keypad input and update the duck's position.
5. Check for collisions between the duck and obstacles.
6. Display the Game Over message if a collision is detected.

Obstacles move at intervals of approximately one second.

## Future Improvements

- **Difficulty levels:** Increase obstacle speed as the game progresses.
- **Scoring system:** Award points for each successfully avoided obstacle.
- **Progressive gameplay:** Gradually increase the challenge over time.

## License

This project is licensed under the MIT License.
