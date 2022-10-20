2022-10-18, 18:45
Status: #reference
Tags: #game #AI

---

# C2 Game AI

This Chapter looks at the high-level issues around game AI: what kinds of approaches work, what they need to take accout of, and how they can all be put together.

2.1 The Complexity Fallacy
It is a common mistake to think that the more comlex the AI in a game, the better the characters will look to the player.
Knowing when to be complex and when to stay simple is the most difficult element of the game AI programmer's art. The best AI programmers are those who can use a very simple technique to give the illusion of complexity.

The perception Window

Changes of behavior

2.2 The kind of AI in games
AI for a game is equal parts hacking, heuristics, and algorithms.

A heuristic is a rule of thumb, an approximate solution that might work in many situations but is unlikely to work in all.

A handful of heuristics appears over and over in AI and software in general. They are good starting points when initially tackling a problem.

Most Constrained. Do the Most Difficult Thing First. Try the Most Promising Thing First.

Algorithms

2.3 Speed and Memory
2.3.1 Processor Issues
SIMD , Multi-Core Processing and Hyper-Threading, Virtual Functions/Indirection
2.3.2 Memory concerns
Cache
2.3.3 PC Constraints
2.3.4 Console Constraints

2.4 The AI Engine
building a game engine involves building AI tools that can be easily reused, combined, and applied in interesting ways. To support this, we need an AI structure that makes sense over multiple genres.

Toolchain concerns

![[ai_for_games_2_1.png]]
