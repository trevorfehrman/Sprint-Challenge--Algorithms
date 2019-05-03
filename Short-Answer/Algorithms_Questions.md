# Analysis of Algorithms

## Exercise I

Give an analysis of the running time of each snippet of
pseudocode with respect to the input size n of each of the following:

```
a)  a = 0
    while (a < n * n * n):
      a = a + n * n
```
O(n)

Complexity increases linearly as n grows.

```
b)  sum = 0
    for i in range(n):
      i += 1
      for j in range(i + 1, n):
        j += 1
        for k in range(j + 1, n):
          k += 1
          for l in range(k + 1, 10 + k):
            l += 1
            sum += 1
```

I think this is O(n^4).  k is not constant; it grows as n grows.

```
c)  def bunnyEars(bunnies):
      if bunnies == 0:
        return 0

      return 2 + bunnyEars(bunnies-1)
```


O(n).  As N grows we recursively compute linearlly.

## Exercise II

Suppose that you have an _n_-story building and plenty of eggs. Suppose also that an egg gets broken if it is thrown off floor _f_ or higher, and doesn't get broken if dropped off a floor less than floor _f_. Devise a strategy to determine the value of _f_ such that the number of dropped eggs is minimized.

Write out your proposed algorithm in plain English or pseudocode and give the runtime complexity of your solution.


This is binary search.  It's an O(log n) problem.

1) Find the middle floor.
2) see if the egg broke.
3) If it broke you know every floor above you would cause it to break as well.
   Find the middle floor of all the floors below you and try again.

4) if it didn't break you know the egg would survive all the floors below you.
   Find the middle floor of all the floors above you and try again.

5) repeat stpes 3 and / or 4 until you find the exact point the egg breaks.