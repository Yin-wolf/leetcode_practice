# Find the Town Judge

[Visit Question](https://leetcode.com/problems/find-the-town-judge/)

## Solution

**GIVEN**:

1. trust[i].lenght = 2
2. a(i) != b(i) --> unique
3. 1 <= a(i), b(i) <= n

**Solve**:

1. Create an array with size `n + 1` of the town people. and intilaize it to 0.

2. When a person trust's someone else than himself, the `trust` value of that person should be decreased

3. If a certain `x` person is trusted by others from town, than this `x` person value should be increased and those who trusted that `x` person there values should be decreased

4. At last traverse through every person of town and while traversing If a person is found with `N-1` trusts than this person should be the judge and return the index of that person

**_Technically_**:

> In a graph the indegree of a person or node is the number of nodes that trusts a given specific node and outdegree of a person or node is the number of nodes that are trusted by given specific node .

    * Out-degree is the number of outgoing edges emanating from a node
    * In-degree is the number of incoming edges onto a node

### Python

    ```python
    class Solution:
    def findJudge(self, N: int, trust: List[List[int]]) -> int:
        Trusted = [0] * (N+1)
        for (a, b) in trust:
            Trusted[a] -= 1
            Trusted[b] += 1
            
        for i in range(1, len(Trusted)):
            if Trusted[i] == N-1:
                return i
        return -1
    ```
