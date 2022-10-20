2022-10-18, 18:45
Status: #reference
Tags: #game #AI

---

# C1 What is AI

Aritificial intelligence is about making computers able to perform the thinking tasks that humans and animals are capeble of.
As games developers, we are primarily interested in only the engineering side: build algorithms that make game characters apper human or animal-like.

1.1.1 Academic AI
The Early Days: The early days include the time before computers, where philosophy of mind occasionally made forays into AI with such question as: "What produces thought？""Could you give life to an inanimate object?"

The Symbolic Era
From the late 1950s through to the early 1980s the main thrust of AI research was "symbolic" system. A symbolic system is one in which the algorithm is divided into two components: a set of knowledge(represented as symbols such as words, numbers, sentences, or pictures) and a reasoning algorithm that manipulates those symbols to create new combinations of symbols that hopefully represent problem solutions or new knowledge.

An expert system, one of the purest expressions of the approach, is the most famous AI technique.

The Modern Era
The effect was a move toward natural computing: techniques inspired by biology or other natural systems. These techniques include neural networks, genetic algorithms, and simulated annealing.

1.2 Model of Game AI

![[ai_for_games_1_1.png]]

Movement refer to algorithms that turn decisions into some kind of motion.
Decision making involves a character working out waht to do next.
You can go a long way with movement AI and decision making AI, and most action-based three-dimensional games use only these two elements. But to coordinate a whole team, some strategic AI is required.
Each character in the group may have their own decision making and movement algorithms, but overall their decision making will be influenced by a group strategy.

1.2.4 Infrastructure
The movement requests need to be turned into action in the game by using either animation or, increasingly, physics simulation.
Similarly, the AI needs information from the game to make sensible decisions.This is sometime called "perception"(especially in academic AI): working out what information the character knows.

1.2.5 Agent-based AI
In this context, agent-based AI is about producing autonomous characters that take in information from the game data, determine what actions to take based on the information,and carry out those actions.
In contrast, a non-agent-based AI seeks to work out how everything ought to act from the top down and builds a single system to simulate everything.

1.3 Algorithms, Data Structures, and Representations

Algorithm

* The problem that the algorithm tries to solve
* A general description of how the solution works
* a pseudo-code presentation of the algorithm
* An indication of the data structures required to support the algorithm
* Particular implementation nodes
* Analysis of the algorithm's perormance
* Weakness in the approach
