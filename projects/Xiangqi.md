---
layout: project
type: project
image: img/xiangqi.jpg
title: "ChineseChess_ai"
date: 2026
published: true
labels:
  - Python
  - Object-Oriented Programming
  - Minimax Search
  - Alpha-Beta Pruning
  - Heuristic Evaluation
  - Command-Line Interface
summary: "A command-line Chinese Chess / Xiangqi endgame AI project built in Python."
---

# Xiangqi Endgame AI

A command-line Chinese Chess / Xiangqi endgame AI project built in Python. This project implements core Xiangqi rules, legal move generation, game-state evaluation, and an AI opponent using Minimax search with Alpha-Beta pruning.

## Project Overview

This project focuses on a simplified Xiangqi endgame environment where players can test different strategies against an AI-controlled opponent. The goal of the project is to explore how classical AI search algorithms can be used to make decisions in a turn-based board game.

The AI evaluates possible future board states and selects the move that leads to the strongest position. The project includes rule-based move validation, check/checkmate detection, random and greedy baseline players, and automated evaluation experiments.

## Key Features

- Command-line Xiangqi board display
- Legal move generation for Xiangqi pieces
- Support for important Xiangqi rules, including:
    - General / King palace restriction
    - Advisor diagonal movement
    - Pawn forward and side movement
    - Rook straight-line movement
    - Cannon capture rule with screen piece
    - Flying general rule
    - Check and checkmate detection
- AI opponent using Minimax search
- Alpha-Beta pruning to reduce unnecessary search
- Heuristic board evaluation
- Random and greedy baseline agents for comparison
- Automated experiment results over multiple games

## Tech Stack

- Python
- Object-Oriented Programming
- Minimax Search
- Alpha-Beta Pruning
- Heuristic Evaluation
- Command-Line Interface

## AI Design

The AI uses a Minimax-based search strategy. Since Xiangqi is a two-player competitive game, the AI assumes that both sides will try to make the best possible move.

At each turn, the AI:

1. Generates all legal moves for the current player.
2. Simulates each possible move.
3. Recursively evaluates future board states.
4. Uses Minimax logic to choose the best move.
5. Applies Alpha-Beta pruning to skip branches that do not need to be fully searched.

The evaluation function scores a board state based on several factors:

- Piece values
- Captured pieces
- Mobility
- Check and checkmate states
- Win, loss, and draw conditions

In the current version, the evaluation score is calculated from Red's perspective. When the AI controls Black, it chooses moves that minimize Red's advantage.

## Piece Evaluation

The AI assigns different values to different pieces based on their importance in the endgame.

| Piece | Description | Value |
|---|---|---:|
| K | General / King | 0 |
| A | Advisor / Guard | 40 |
| P | Pawn | 180 |
| C | Cannon | 300 |
| R | Rook | 500 |

The General is not evaluated with a normal material value because losing the General directly determines the outcome of the game.

## Project Structure

```text
.
├── main.py              # Main entry point for running the game
├── game_state.py        # Board representation, pieces, and game state logic
├── move_generator.py    # Legal move generation and rule checking
├── evaluation.py        # Board evaluation function
├── minimax.py           # Minimax search and Alpha-Beta pruning
├── display.py           # Command-line board display
├── random_endgame.py    # Random endgame state generation
└── README.md
```

## How to Run

Run the main program:

```bash
python main.py
```

If your system uses Python 3 explicitly:

```bash
python3 main.py
```

## Evaluation Experiments

To test the AI, I compared it against random and greedy baseline agents over 50 games.

| Red Player | Black Player | Games | Black Wins | Red Wins | Draws | Average Plies |
|---|---|---:|---:|---:|---:|---:|
| Random | AI | 50 | 50 | 0 | 0 | 2.32 |
| Random | Random | 50 | 33 | 2 | 15 | 16.02 |
| Greedy | AI | 50 | 50 | 0 | 0 | 4.00 |
| Greedy | Random | 50 | 21 | 6 | 23 | 30.00 |

## Results Summary

The AI performed strongly against both random and greedy baseline players. In the tested endgame scenarios, the AI won all games when playing as Black.

Compared with the random baseline, the AI was able to find winning moves much faster and more consistently. The average number of plies was also much lower when the AI played, showing that the search-based strategy was able to identify strong tactical decisions quickly.

These results suggest that even a depth-limited Minimax agent can perform effectively in a simplified Xiangqi endgame when combined with a reasonable evaluation function and legal move generation.

## What I Learned

Through this project, I gained hands-on experience with:

- Designing a turn-based game state system
- Implementing legal move generation for a board game
- Applying Minimax search to a real game environment
- Optimizing search using Alpha-Beta pruning
- Designing heuristic evaluation functions
- Comparing AI performance against baseline strategies
- Running automated experiments and interpreting results

## Future Improvements

Possible future improvements include:

- Adding a full Xiangqi starting board
- Increasing search depth with better optimization
- Adding transposition tables
- Improving move ordering
- Adding a graphical user interface
- Supporting human vs AI and AI vs AI modes more fully
- Improving the evaluation function with positional features
- Adding opening and endgame-specific strategies

## Author

Feiyi Chen  
M.S. Computer Science, Northeastern University
