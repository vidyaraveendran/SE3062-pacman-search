# AI Usage Log

**Module:** SE3062 Intelligent Systems · Take-Home Assignment 04 — Search Algorithms in Pac-Man
**Group:** Group 
**Repository:** https://github.com/vidyaraveendran/SE3062-pacman-search



## 1. Declaration

**Tool used:** Claude (Anthropic)

**Purpose of use:** understanding the A* search algorithm, clarifying the
project's existing interfaces (`util.PriorityQueue`, `SearchProblem`), guidance
on implementing Question 4, and interpreting the autograder output.



## 2. Prompt record — vidyaraveendran (Member D)

**Assigned question:** Q4 — A* Search (`search.py`, `aStarSearch`)

**1 · 2026-09-23**
> "Which function in `search.py` is Q4, and which lines am I allowed to touch without affecting my teammates' questions?"

*Purpose:* identify the exact scope of the individual task.

**2 · 2026-09-23**
> "What methods does `util.PriorityQueue` have, what does `push` take, and what does `getSuccessors` return?"

*Purpose:* understand the existing project interfaces before coding.

**3 · 2026-09-23**
> "How do I track the path to each node — keep it in the queue entry, or rebuild it at the end from a parent map?"

*Purpose:* choose between two path-reconstruction designs.

**4 · 2026-09-23**
> "I have uniform cost search in front of me. What is the smallest change that turns it into A*?"

*Purpose:* isolate the single difference between UCS and A*.

**5 · 2026-09-23**
> "Do I put `g` or `g + h` inside the tuple, and what exactly breaks in the costs if I choose wrong?"

*Purpose:* confirm that the accumulated cost is stored separately from the priority.

**6 · 2026-09-23**
> "Do I check the visited set when I pop a node or when I push its successors, and does the same state reaching the fringe twice cause a problem?"

*Purpose:* correct handling of repeated states in graph search.

**7 · 2026-09-23**
> "Where does the goal test go, and what happens to the result if I put it in the wrong place?"

*Purpose:* establish why the goal test must occur on dequeue.

**8 · 2026-09-23**
> "What does `python autograder.py -q q4` print when it passes, and what does each test name check?"

*Purpose:* interpret the autograder output for Question 4.

**9 · 2026-09-23**
> "The run prints "total cost of 210" and "Search nodes expanded: 549" — what do those mean, and how do I know 210 is the optimal cost and not just a working path?"

*Purpose:* distinguish a valid path from an optimal one when reporting results.

**10 · 2026-09-23**
> "Does my code still behave correctly when the heuristic is zero, and how do I verify that against uniform cost search?"

*Purpose:* verify that A* with `nullHeuristic` reduces to uniform cost search.

**Outcome.** `aStarSearch` implemented with `util.PriorityQueue`, storing `g` in
the fringe entry and using `f = g + h` only as the priority, with the goal test
on dequeue and an expanded set for graph search. `python autograder.py -q q4`
returns **3/3**. On `bigMaze` with `manhattanHeuristic` the path cost is **210**
(optimal) with **549** nodes expanded, against **620** for uniform cost search.

---

## 3. Prompt record — afathi (Member A)

**Assigned questions:** Q1 — Depth First Search · Q5 — CornersProblem

*(to be completed by afathi)*

---

## AI Usage Declaration — Thavaruban

**Tools Used:** ChatGPT and Codex

### ChatGPT — Conceptual Understanding and Planning

ChatGPT was used to understand the theoretical concepts behind Breadth-First Search (BFS) and the Corners Heuristic, including their working principles, admissibility, consistency, and development planning.

**Representative prompt summaries**

1. Explain how Breadth-First Search works in Pac-Man and why a FIFO queue is used.
2. Explain the role of visited states in BFS and how they prevent repeated exploration.
3. Explain the difference between BFS and A* Search.
4. Explain admissibility and consistency in heuristic search.
5. Explain how Manhattan distance can estimate the remaining cost of visiting all unvisited corners.
6. Explain why evaluating different corner-visiting orders can improve heuristic performance.

### Codex — Implementation and Code Review

Codex was used to assist with implementing, reviewing, and testing the BFS algorithm and Corners Heuristic.

**Representative prompt summaries:**

1. Inspect the existing Pac-Man search project and identify the BFS implementation requirements.
2. Implement BFS using a FIFO queue and visited-state tracking.
3. Review the BFS implementation for correctness and unnecessary state exploration.
4. Inspect the existing CornersProblem state representation and plan the Corners Heuristic implementation.
5. Implement the Corners Heuristic using Manhattan distance and permutations of remaining corners.
6. Review the heuristic for admissibility, consistency, and compatibility with A* Search.
7. Run the relevant autograder tests and report correctness and node-expansion results.

### Declaration

ChatGPT was used for conceptual understanding and development planning. Codex was used for code implementation, review, and testing. The final implementations were reviewed and verified using the provided project autograder.


---

## 5. Prompt record — Mayureshan (Member C)

**Assigned questions:** Q3 — Uniform Cost Search · Q7 — foodHeuristic

*(to be completed by Mayureshan)*

---

"
