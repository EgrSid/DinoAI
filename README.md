# Dino Game with Pygame and Neural Network Training

This repository contains two main projects related to the classic "Dino" game, famously known from Google Chrome's offline mode. The first project is a simple implementation of the game using Pygame, and the second is an AI-driven version where a neural network learns to play the game autonomously.

## Files and Directories

### 1. `Dino.py`
This script is a Pygame-based recreation of the classic "Dino" game, where a dinosaur character must jump over cacti to avoid collisions. The game includes several enhancements over the original version:
- **FPS Display**: The current frames per second (FPS) are displayed on the screen, providing real-time feedback on the game's performance.
- **Speed Indicator**: The dinosaur's running speed is shown, which increases over time, adding to the game's challenge.
- **Dino Name**: The name of the dinosaur is displayed, personalizing the gaming experience.

This version is a great example of how Pygame can be used to create simple yet engaging games with added features to enhance user experience.

### 2. `DinosaurAI.py`
In this project, the primary focus is on training a neural network to autonomously play the Dino game. This is achieved using the NEAT (NeuroEvolution of Augmenting Topologies) algorithm, a powerful and flexible tool for evolving neural networks. Below is an overview of the NEAT library, its capabilities, and how it is used within this project.

#### What is [NEAT](https://neat-python.readthedocs.io/en/latest/)?
NEAT is an evolutionary algorithm that optimizes neural networks by simulating natural selection. Unlike traditional neural network training methods that rely on backpropagation and gradient descent, NEAT uses genetic algorithms to evolve both the topology and the weights of the network. This means that NEAT not only adjusts the connections between neurons but can also evolve the network structure itself, adding or removing neurons and connections as needed.

#### Key Capabilities of NEAT:
1. **Evolving Network Topologies**: NEAT begins with simple neural networks and gradually complexifies them by adding new nodes and connections. This allows for the automatic discovery of the optimal network structure for a given problem, avoiding the need to manually design the network architecture.
2. **Speciation**: NEAT groups similar neural networks into species to protect innovative structures during the evolutionary process. This prevents premature convergence by allowing new structures to mature before they compete with more established ones.
3. **Crossover and Mutation**: NEAT uses genetic operators such as crossover and mutation to evolve the neural networks. Crossover combines the structures of two parent networks to produce offspring, while mutation introduces random changes to the network structure or weights, promoting diversity within the population.
4. **Fitness Evaluation**: Each neural network in the population is evaluated based on a fitness function, which in this case is how well the dinosaur plays the game. The networks that perform best are more likely to be selected for reproduction, driving the evolution of increasingly proficient AI.

#### How NEAT is Used in `DinosaurAI.py`:
1. **Game Setup and Integration**: Pygame is used to render the Dino game environment where the AI will be trained. The game mechanics, such as detecting collisions with cacti and scoring, are integrated with NEAT to provide feedback to the neural network.
   
2. **Neural Network Configuration**: The neural network's initial configuration, including the number of inputs and outputs, is defined according to the game's requirements. Inputs typically include the distance to the next obstacle, the dinosaur's speed, and other relevant game state variables. The output is a decision—whether to jump or not.

3. **Training Process**: NEAT begins with a population of simple neural networks. Each network controls a dinosaur in the game, and its performance is evaluated based on how long the dinosaur survives without hitting a cactus. Over successive generations, NEAT evolves the networks, improving their ability to play the game.

4. **Parameter Tuning with `config-feedforward.txt`**: The `config-feedforward.txt` file contains all the necessary parameters for NEAT, such as population size, mutation rates, and crossover probabilities. This configuration file is crucial for fine-tuning the evolutionary process, allowing the neural networks to evolve effectively within the constraints of the Dino game.

5. **Running the Algorithm**: The NEAT algorithm iteratively evolves the neural networks over multiple generations. As the generations progress, the dinosaurs controlled by these networks become increasingly adept at avoiding cacti, eventually achieving performance levels far beyond what a human player could maintain as the game speeds up.

6. **Outcome**: The final result is a neural network capable of playing the Dino game indefinitely, making decisions in real-time based on the game's state. This showcases the power of NEAT in solving complex, dynamic problems through evolutionary computation.

#### Why Use NEAT?
- **Flexibility**: NEAT's ability to evolve both the structure and parameters of neural networks makes it suitable for a wide range of problems, including those where the optimal network architecture is not known in advance.
- **Automation**: NEAT automates the process of designing neural networks, which can be particularly useful for complex tasks like game playing, where manual design and tuning of networks can be challenging.
- **Innovation**: NEAT's speciation mechanism encourages innovation by allowing new network structures to develop without being immediately outcompeted by existing networks, leading to the discovery of novel solutions.

This implementation of NEAT within the Dino game project serves as an excellent demonstration of how evolutionary algorithms can be used to train neural networks for real-time decision-making tasks in dynamic environments.

---

This repository is an exciting blend of game development and artificial intelligence, showcasing how a simple game can be transformed into a challenging environment for training neural networks. Whether you're interested in creating games with Pygame or exploring AI techniques with NEAT, this repository offers valuable insights and practical examples to help you get started.
