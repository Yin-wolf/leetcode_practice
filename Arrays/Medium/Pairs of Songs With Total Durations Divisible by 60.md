# Question: Pairs of Songs With Total Durations Divisible by 60

[Visit Question](https://leetcode.com/problems/pairs-of-songs-with-total-durations-divisible-by-60)

## Solution

Code is referred from Submissions Tab of author _(lee215)_

1. `t % 60` -> Reminder range from 0 to 59, _in python, % returns a number between 0 and mod_

2. Count occurance of each remainder

3. For each `t`, there is some `x` that satisfies `(t + x) % 60 = 0`

4. solving this `(t + x) % 60 = 0`

    * the `max` value `t` and `x` can have to get reminder `0` is 30 (*Two-Sum Approach x = 60 - t*) and the `min` value they can have is `0`

    * so, we can take `t%60 + x%60 = 0 or 60`

    * hence, we get `x%60 = 60 - t%60`

This `result += array[-t % 60]`  is important. Here array stores the counter whenever we get the multiple of 60, with any number of `x`. We maintain the counter count by keeping the array size `60`.

### Python

```python
    def numPairsDivisibleBy60(self, time):
        array = [0] * 60 # Size of array 
        result = 0 # Counter
        for t in time:
            result += array[-t % 60] 
            array[t % 60] += 1
        return result
```
