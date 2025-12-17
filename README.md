# Asteroids

A classic Asteroids arcade game implementation in Python using Pygame. Destroy asteroids while avoiding collisions in this action-packed retro-style game.

## Overview

This project recreates the iconic Asteroids arcade game, where the player controls a spaceship that must destroy incoming asteroids while avoiding collisions. The game features smooth physics-based movement, shooting mechanics, and asteroid splitting dynamics.

## Features

-   **Player Control**: Navigate and rotate your spaceship with keyboard controls
-   **Shooting Mechanics**: Fire shots with cooldown management
-   **Asteroid Dynamics**: Asteroids split into smaller pieces when destroyed
-   **Collision Detection**: Full collision detection between player, asteroids, and shots
-   **Game State Logging**: Event and state logging for gameplay analysis
-   **High Performance**: Runs at 60 FPS with smooth animations

## Requirements

-   Python 3.12+
-   Pygame 2.6.1

## Installation

1. Clone the repository:

```bash
git clone <repository-url>
cd asteroids
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

Or with uv:

```bash
uv pip install pygame==2.6.1
```

## Running the Game

Start the game with:

```bash
python main.py
```

## Controls

| Key       | Action        |
| --------- | ------------- |
| **W**     | Move Forward  |
| **S**     | Move Backward |
| **A**     | Rotate Left   |
| **D**     | Rotate Right  |
| **SPACE** | Shoot         |
| **Q**     | Quit          |

## Game Mechanics

### Asteroids

-   Asteroids spawn continuously and move across the screen
-   Hitting an asteroid with a shot splits it into two smaller asteroids
-   Smallest asteroids are destroyed completely
-   Colliding with an asteroid ends the game

### Player Ship

-   Triangular spaceship that can rotate and move in any direction
-   Rotation speed: 300°/second
-   Movement speed: 200 pixels/second
-   Shot cooldown: 0.3 seconds between shots
-   Shot speed: 500 pixels/second

### Rules

-   Destroy asteroids to eliminate them
-   Larger asteroids split into smaller ones when destroyed
-   Avoid collisions to keep playing

## Project Structure

```
asteroids/
├── main.py              # Main game loop
├── player.py            # Player ship class
├── asteroid.py          # Asteroid class
├── asteroidfield.py     # Asteroid spawning system
├── shot.py              # Shot/bullet class
├── circleshape.py       # Base class for circular objects
├── constants.py         # Game configuration constants
├── logger.py            # Event and state logging
├── game_events.jsonl    # Event log file
├── game_state.jsonl     # State log file
└── README.md            # This file
```

## Configuration

Game parameters can be adjusted in [constants.py](constants.py):

-   `SCREEN_WIDTH` / `SCREEN_HEIGHT`: Game window dimensions (1920x1440)
-   `PLAYER_RADIUS`: Size of the player ship (20)
-   `PLAYER_SPEED`: Player movement speed (200)
-   `PLAYER_TURN_SPEED`: Rotation speed (300)
-   `ASTEROID_MIN_RADIUS`: Smallest asteroid size (20)
-   `ASTEROID_SPAWN_RATE_SECONDS`: How often asteroids spawn (0.8)
-   `SHOT_RADIUS`: Size of shots (5)

## Logging

The game logs gameplay events and state to JSON files:

-   `game_events.jsonl`: Records significant gameplay events (asteroid_split, asteroid_shot, player_hit)
-   `game_state.jsonl`: Logs game state snapshots (positions, velocities, etc.)

These logs can be used for gameplay analysis and debugging.

## Architecture

The game uses an Entity-Component-System (ECS) inspired approach:

-   **CircleShape**: Base class for all circular game objects
-   **Player**: Player-controlled spaceship with shooting capability
-   **Asteroid**: Destructible asteroids that split when hit
-   **Shot**: Projectiles fired by the player
-   **AsteroidField**: System that manages asteroid spawning

All game objects are organized into sprite groups for efficient updating and rendering.

## Author

Daveian Gordon
