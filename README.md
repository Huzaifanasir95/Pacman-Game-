# Pacman-Game-
Welcome to the Multi-Threaded Pac-Man Game project. This project aims to recreate the classic Pac-Man game with a focus on implementing multi-threading and synchronization techniques to manage interactions between Pac-Man and multiple computer-controlled ghosts. Each entity in the game operates on its own thread to ensure smooth and concurrent gameplay.

Project Objective
The primary objective of this project is to develop a multi-threaded version of Pac-Man using synchronization techniques to manage the interactions and data conflicts between Pac-Man and the ghosts. The game will handle data conflicts and ensure smooth gameplay with each entity operating on its own thread.

Technology Stack
Programming Language: C++
Graphics Library: SFML (Simple and Fast Multimedia Library)
Threading Library: pthreads (POSIX threads)
Project Phases
Phase 1: Setting Up Dedicated Threads for Game Modules
Game Engine Thread
Responsibilities: Coordinates the overall game flow, handles player input, updates the game state, and renders graphics.
Main Loop: Continuously updates the game state based on user input and ghost movement.
User Interface Thread
Responsibilities: Manages UI components such as menus, scoreboards, and HUD elements.
Input Handling: Processes input events from the player (keyboard or mouse) and communicates them to the game engine thread.
Ghost Controller Threads
Responsibilities: Controls the behavior of each ghost independently.
Movement Logic: Each ghost thread executes its algorithm to determine movement patterns and actions based on the current game state.
Advanced AI: Implements a simple shortest path algorithm for intelligent ghost behavior or predefined paths for simpler versions.
Phase 2: Basic Game Mechanics
Game Board Initialization
Layout Design: Implements the shared game board layout, including walls, paths, pellet positions, and power pellets.
Initial Positions: Sets starting positions for Pac-Man and the ghosts.
Movement Mechanics
Pac-Man Movement: Allows user input to dictate Pac-Man's direction.
Ghost Movement: Implements basic AI for ghost movement.
Eating Mechanics
Pellet Consumption: Enables Pac-Man to eat pellets, updating the game score.
Power Pellets: Defines effects such as ghosts turning blue when Pac-Man eats a power pellet.
Lives System
Life Count: Implements a system allowing Pac-Man multiple attempts at the game.
Collision Handling: Decrements lives each time Pac-Man collides with a ghost.
Phase 3: Synchronization
Scenario 1: Ghost Movement
Data Conflict Management: Ensures no read operation occurs during a write operation when ghosts and Pac-Man interact with the game board.
Scenario 2: Eating Power Pellets
Conflict Resolution: Ensures no two power pellets are eaten simultaneously and handles the respawning of power pellets.
Scenario 3: Ghost House
Resource Management: Manages limited resources (keys and exit permits) for ghosts to leave the ghost house without causing deadlocks.
Scenario 4: Prioritizing Certain Ghosts
Speed Boost Management: Ensures fair distribution of limited speed boosts among faster ghosts.
Important Instructions
Thread Creation: Separate threads for Pac-Man and each ghost to enable independent movement.
Error Handling: Ensure all threads start correctly and handle any errors during execution.
Concurrency: Implement concurrent execution to allow simultaneous movement of Pac-Man and ghosts without lag or jitter.
Synchronization Primitives: Use semaphores and mutexes for synchronization, avoiding explicit waiting mechanisms like thread.join().
