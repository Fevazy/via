## a -> b, via what?

First usage is to trace how function calls function B. For example, we want to
see all paths where entry point calls network stack - you export call graph
from, say, Ghidra or your own parser and pass it to via, and it finds all
(or not, as you wish) paths between, say, main and sendto, or MainActivity and
java.net.* - depends on what you decompile

Ghidra and r2 will be used as first backends - you make query to r2 or start
provided Python script inside of Ghidra, xrefs get written int CSV or other
container - and then you feed it to this tool.

First functional will incllude only tracing functions' dependencies since that
is the reason I build this tool, then it may be extended.
