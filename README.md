# Via

**a -> b, via what?**

Tool to trace whether a function calls another one, and how, if it does.

For example, you need to know where app calls network - you export call
graph, feed it to Via and get paths from `main()` to `sendto()`, or from
`MainActivity` to `java.net.*`

### WHY??

Fair question, appreciate that. In r2, you have to analyze xrefs switching
between them manually. In Ghidra, call graphs are there, but they fail when
there's a lot of nodes. If they don't, you need to trace code flow yourself -
and DFS is far faster and less error-prone than every eye on this planet.

### Status

Very WIP. Not even MVP yet. First features to implement:
- r2 backend (export xrefs into CSV)
- DFS/BFS for finding reachability

### What would be later?

- Ghidra as backend (python script for exporting)
- Performance tuning up (multithreading, two-way DFS etc etc)
- Functionality expansion (xrefs, not only function calls)

### Installation

Not yet. After r2 and pathfinding - yes, it will be available.

### License

Apache 2.0. See project root.
