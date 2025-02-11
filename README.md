# FLAPPY BIRB AI (NEAT ALGORITHM)

<div align="center">
  

https://github.com/user-attachments/assets/5b5782cc-7546-40a8-896e-9b12ee1383af

</div>



# Flappy Bird AI using NEAT Algorithm

## Overview
This project implements an AI that learns to play Flappy Bird using the NEAT (NeuroEvolution of Augmenting Topologies) algorithm. The AI evolves over generations to master the game mechanics without any prior knowledge of the game rules.

## How It Works

### Game Mechanics
- The game is built using Pygame
- Bird must navigate through pipes by jumping at the right time
- Score increases as the bird successfully passes through pipes
- Game ends when bird hits a pipe or goes out of bounds

### NEAT Implementation
The NEAT algorithm is used to evolve neural networks that control the birds:

1. **Neural Network Structure**
   - Input Layer (3 nodes):
     - Bird's Y position
     - Distance to top pipe
     - Distance to bottom pipe
   - Output Layer (1 node):
     - Jump decision (>0.5 triggers jump)

2. **Evolutionary Process**
   - Each generation starts with multiple birds
   - Each bird has its own neural network
   - Fitness is calculated based on:
     - Distance traveled (+0.1 per frame)
     - Pipes passed (+5 per pipe)
     - Collisions (-1 for hitting pipe)

3. **Selection & Evolution**
   - Best performing birds are selected for breeding
   - New generation inherits and mutates successful traits
   - Process continues until optimal performance is achieved

## Code Structure

### Main Components

1. **Bird Class**
   - Handles bird movement, animation, and collision detection
   - Controls jumping mechanics and rotation

2. **Pipe Class**
   - Manages pipe generation and movement
   - Handles collision detection with birds

3. **Base Class**
   - Controls the moving ground animation
   - Provides ground collision detection

4. **NEAT Configuration**
   - Population size: Defined in config file
   - Fitness function: Based on survival time and pipes cleared
   - Species management: Handled automatically by NEAT

## How to Run

1. Install required packages:
```bash
pip install pygame neat-python

## Understanding NEAT Algorithm

NEAT (NeuroEvolution of Augmenting Topologies) is a genetic algorithm that evolves neural networks. Key features:

### 1. Starting Simple
- Begins with simple networks
- Gradually adds complexity through evolution

### 2. Genetic Encoding
- Each network structure is encoded in a genome
- Includes nodes and connections with weights

### 3. Speciation
- Similar networks are grouped into species
- Protects innovation through similar-with-similar breeding

### 4. Fitness Sharing
- Rewards are shared within species
- Prevents any one solution from dominating

### 5. Innovation Through Evolution
- New nodes and connections can be added
- Existing structures can be modified

## Performance Metrics
- Generation count shows evolutionary progress
- Score indicates current performance
- Birds that survive longer and score higher have better fitness

## Customization

You can modify various parameters in the config-feedforward.txt file:
- Population size
- Mutation rates
- Species threshold
- Network activation functions

