---
id: WaitForGraph
aliases: []
tags: []
---

# Wait For Graph

The following algorithm can be used to test a schedule for conflict serializability. The algorithm looks at only the read_item and write_item operations in a schedule to construct a **precedence graph** (or **serialization graph**), which is a **directed graph** that consists of a set of nodes and a set of directed edges. **There is one node in the graph for each transaction in the schedule**. 

Algorithm:
    1. For each transaction Ti participating in schedule S, create a node labeled Ti in the precedence graph.
    2. For each case in S where **Tj executes a read_item(X) after Ti executes a write_item(X), create an edge (Ti -> Tj)** in the precedence graph.
    3. For each case in S where **Tj executes a write_item(X) after Ti executes a read_item(X), create an edge (Ti -> Tj)** in the precedence graph.
    4. For each case in S where **Tj executes a write_item(X) after Ti executes a write_item(X), create an edge (Ti -> Tj)** in the precedence graph.
    5. The schedule S is serializable if and only if the precedence graph has no cycles.

If there is a cycle in the precedence graph, schedule S is not (conflict) serializable. A **cycle** in a directed graph is a **sequence of edges** C = ((Tj →Tk), (Tk → Tp), ..., (Ti → Tj)).

If there is no cycle in the precedence graph, we can create an **equivalent serial schedule** S' that is equivalent to S, by ordering the transactions that participate in S as follows:
    - Whenever an edge exists in the precedence graph from Ti to Tj, Ti must appear before Tj in the equivalent serial schedule S'.
