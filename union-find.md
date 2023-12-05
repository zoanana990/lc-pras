# Disjoint-set/Union-find forest

Operation

- Find(x): find the root/cluster-id of x
- Union(x, y): merge two clusters

Check whether two elements are in the same set or not in O(1)*

Find: O(a(n))*
Union: O(a(n))*
Space: O(n)

note:

- `*` is amortized
- `a(.)` is [inverse ackermann function](https://www.geeksforgeeks.org/inverse-ackermann-function/)

Without optimization: Find O(n)

Two key optimizations:

- Path compression: make tree flat
- Union by rank: merge low rank tree to high rank tree

### Pseudo Code

```txt
class UnionFindSet:
    func UnionFindSet(n):
        parents = [1...n]
        ranks = [0...0]
    
    func Find(x):
        if x != parens[x]:
            parents[x] = Find(parents[x])
        return parents[x]
        
    func Union(x, y):
        px, py = Find(x), Find(y)
        if ranks[px] > rank[py]: parents[py] = px
        if ranks[px] < rank[py]: parents[px] = py
        if ranks[px] == rank[py]: 
            parents[py] = px
            ranks[px]++
```

### Relative Problems

- 399
- 547
- 737
- 684
- 685