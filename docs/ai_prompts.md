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

## 4. Prompt record — Thavaruban (Member B)

**Assigned questions:** Q2 — Breadth First Search · Q6 — cornersHeuristic

*(to be completed by Thavaruban)*

---

## 5. Prompt record — Mayureshan (Member C)

**Assigned questions:** Q3 — Uniform Cost Search · Q7 — foodHeuristic

*(to be completed by Mayureshan)*

---

"