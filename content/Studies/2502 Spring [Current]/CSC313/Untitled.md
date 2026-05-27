---
publish: true
created: 2026-05-20T14:46:26.585+03:00
modified: 2026-05-27T16:31:08.434+03:00
---

## RASHED — Slides 1–3

### Slide 1

> "Good afternoon, everyone. Today our team will be presenting on one of the most foundational algorithms in computer science — **Depth-First Search**, commonly known as DFS. It's one of those algorithms that shows up everywhere once you start looking — from compilers, to network analysis, to puzzle solvers. My name is Rashed, and I'll be presenting alongside Zain, Abdullah, and Abdulrahman. Let's get started."

### Slide 2

> "Here's a roadmap of everything we'll cover today.

> We'll open by explaining what DFS actually is — the core idea behind it. Then we'll look at the code and walk through a full step-by-step example on a real graph so you can see exactly how it behaves at each stage. After that, we'll explore five key applications: path finding, cycle detection, counting connected components, topological sorting, and finding articulation vertices. Finally, we'll wrap up with a discussion of its time complexity, its strengths, and where it falls short.

> There's a lot to cover, so let's jump right in."

### Slide 3 — What is DFS? (Maze Visual)

> "So — what is Depth-First Search?

> Let's start with an analogy. Imagine you're standing at the entrance of a maze. You pick a direction and start walking. You don't stop to check every path as you go — you commit. You keep going deeper and deeper down that one path until you physically can't go any further — you've hit a dead end. Only then do you turn around and backtrack to the last point where you had another unexplored option. You try that direction, commit to it, and repeat the whole process.

> This is exactly how DFS works. It's a graph traversal algorithm that prioritizes depth over breadth. Given a starting node, it explores as far as possible along one branch before backtracking and trying another. It doesn't stop to explore neighbors at the same level first — it goes deep.

> Now contrast this with BFS — Breadth-First Search — which is like exploring a maze by checking every path that's exactly one step away, then every path two steps away, and so on. BFS spreads out wide. DFS drills down deep.

> DFS works on both directed and undirected graphs. It can be implemented recursively — where the call stack handles the backtracking for you automatically — or iteratively using an explicit stack data structure that you manage yourself.

> The recursive version is particularly elegant, which is exactly what we'll look at in the code. Speaking of which — I'll hand it over to Zain to walk us through the implementation."

---

🎤 ZAIN — Slides 4–7 Slide 4 — The Code Slides 5–7 — Traversal Steps (Nodes 0, 1, 2)
ABDULLAH — Slides 8–10 Traversal Steps (Nodes 3, 4, 5)
ABDULRAHMAN — Slides 11–13 Traversal Steps (Nodes 6, 7, Complete)

## RASHED — Slide 14

### Slide 14 — Cycle Detection

> "Now let's talk about what we can actually do with DFS — starting with **cycle detection**.

> A cycle in a graph means there's a path that starts and ends at the same node. Detecting cycles matters in a lot of real contexts — for example, in dependency management systems, a circular dependency would mean package A needs B, B needs C, and C needs A. That's a deadlock. You need to detect and reject it.

> So how does DFS catch cycles? Remember the `else if` branch Zain highlighted in the code — the condition that fires when a neighbor `y` is already discovered, not yet fully processed, and isn't `v`'s parent. When that fires, it means we've found a **back edge** — an edge that leads back to an ancestor node we're still in the middle of processing. In a DFS tree, a back edge can only exist if there's a cycle.

> Look at the example on screen. We have nodes 0, 1, 2, and 3. DFS gives us the parent chain 1→0, 2→1, 3→2. But there's also a direct edge between nodes 1 and 3. When DFS is at node 3 and checks its neighbor 1 — it sees that 1 is already discovered, isn't 3's parent, and isn't fully processed yet, so the back edge is found, and the cycle is confirmed.

> It's quite simple, and it costs nothing extra — we detect cycles as a natural byproduct of the traversal itself. Abdullah will now cover another application."

---

## ABDULLAH — Slide 15

### Slide 15 — Counting Connected Components

## ABDULRAHMAN — Slides 16–17

### Slide 16 — Complexity, Strengths, and Limitations

### Slide 17 — Questions?

> "And that's a wrap on Depth-First Search.

> We covered the algorithm, a full step-by-step trace, cycle detection, connected components, and the complexity tradeoffs. Thank you for your time — we're all happy to take any questions."
