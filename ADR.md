# Architecture Decision Record (ADR)

## BFS/DFS Maze Search System

**Course:** 02AML204 – Introduction to Artificial Intelligence  
**Name:** Shreya Bhosale  
**PRN:** 25UAM140

## 1. Context

My project is a BFS/DFS Maze Search System. It finds a path from a starting cell to a goal cell in a maze. BFS and DFS were studied and compared in SLE-2. SLE-3 represented the system using the C4 architecture model. The main challenge is choosing an appropriate search algorithm based on path requirements and performance.

## 2. Decision

I chose BFS when finding the shortest path in an unweighted maze is the main requirement. DFS is retained as an alternative when deep exploration is useful and the shortest path is not necessary.

## 3. Alternatives Considered

- **BFS:** Explores cells level by level using a queue.
- **DFS:** Explores deeply using a stack or recursion.
- **Greedy Best-First Search:** Uses a heuristic to prioritize cells for exploration.

## 4. Rationale / Justification

BFS guarantees a shortest path in an unweighted maze when correctly implemented. DFS does not guarantee the shortest path. In my SLE-2 profiling test, BFS took 0.025739 ms and explored 17 nodes, while DFS took 0.013439 ms and explored 9 nodes. DFS was faster in this particular test. However, algorithm selection depends on the problem requirements, not only execution time. My SLE-3 architecture separates the Search Engine, memory management, path reconstruction, and output responsibilities. The Frontier uses a queue for BFS and a stack or recursion for DFS. This design makes the system easier to understand and maintain.

## 5. Consequences

### Positive
- BFS finds a shortest path in an unweighted maze.
- DFS remains available as an alternative.
- Separate modules improve clarity and maintainability.

### Negative / Trade-offs
- BFS may require more memory.
- BFS was slower in my recorded test.
- Performance may change with different maze sizes and structures.

## 6. References

- SLE-2: BFS/DFS Profiling Report
- SLE-3: C4 Architecture Diagrams
- GitHub: https://github.com/shreyabhosale2912-debug/AI_SLE

## SLE Journey

SLE-1 involved developing the search system. SLE-2 compared BFS and DFS using profiling. SLE-3 represented the system using the four C4 architecture levels. SLE-4 documents and justifies an important design decision.

## AI Contribution Note

- **AI tools used:** ChatGPT and AI-assisted development tools.
- **AI helped with:** Understanding ADR structure and organizing the report.
- **My contribution:** Reviewing the project, profiling results, architecture, and final submission.

## Viva Preparation

- BFS uses a queue; DFS uses a stack or recursion.
- BFS finds the shortest path in an unweighted maze.
- Profiling measures execution performance.
- C4 has four levels: Context, Container, Component, and Code.
- An ADR explains a decision, alternatives, justification, and consequences.
