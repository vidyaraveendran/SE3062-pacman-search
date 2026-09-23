# Q4 — A* Search

**Module:** SE3062 Intelligent Systems · Take-Home Assignment 04
**File edited:** `search.py` · **Function:** `aStarSearch(problem, heuristic=nullHeuristic)`
**Author:** vidyaraveendran (Member D) · **Branch:** `q4-astar` · **Commit:** `13228e7`
**Status:** Implemented and tested — autograder `q4: 3/3`

## 1. Code block added

Only `aStarSearch` was modified in `search.py`. No other function, class or file
was changed.

```python
def aStarSearch(problem: SearchProblem, heuristic=nullHeuristic):
    """Search the node that has the lowest combined cost and heuristic first."""
    start = problem.getStartState()
    fringe = util.PriorityQueue()
    # Each item is (state, actions so far, cost so far g); priority is f = g + h
    fringe.push((start, [], 0), heuristic(start, problem))
    expanded = set()

    while not fringe.isEmpty():
        state, actions, cost = fringe.pop()
        # Goal test on dequeue, so the first goal popped is the cheapest one
        if problem.isGoalState(state):
            return actions
        if state not in expanded:
            expanded.add(state)
            for nextState, action, stepCost in problem.getSuccessors(state):
                if nextState not in expanded:
                    newCost = cost + stepCost                            # g
                    priority = newCost + heuristic(nextState, problem)   # f = g + h
                    fringe.push((nextState, actions + [action], newCost), priority)
    return []
```

## 2. Autograder evidence

Command run: `python autograder.py -q q4` → **Question q4: 3/3**

Screenshot file: `docs/q4_autograder.png`
*(Figure caption for the report: "Figure 4: Autograder output for Q4 — A* Search")*

## 3. Explanation 

`aStarSearch` implements graph-search A* using the project's `util.PriorityQueue`.
Each fringe entry is a tuple `(state, actions, g)`, where `g` is the exact
accumulated cost of the path so far, and it is pushed with priority `f = g + h`,
`h` being the heuristic supplied by the caller. A `set` of expanded states
ensures no state is expanded more than once, which prevents cycles and removes
repeated work. The goal test is applied when a node is dequeued rather than when
it is enqueued, because a cheaper path to the same goal may still be in the
fringe; testing at dequeue preserves optimality. Only `g` is
stored in the entry, while `f` serves solely as the ordering key, since storing
`f` would add the heuristic a second time at every expansion and corrupt the
accumulated costs. Because the heuristic is received as a parameter, the same
implementation serves the position, corners and food problems, and with
`nullHeuristic` it reduces exactly to uniform cost search. The autograder awards
3/3. On `bigMaze` with the Manhattan heuristic the path costs 210, the optimal
value, expanding 549 nodes against 620 for uniform cost search. Optimality
depends on the heuristic being admissible and consistent.