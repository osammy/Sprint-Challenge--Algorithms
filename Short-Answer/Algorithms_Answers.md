#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

a) `O(n)` because `a` increases by `n^2` for each loop, negating the while loop's `n * n * n` condition back down to just `n`, hence `O(n)`


b) `O(n log n)` because even though we have nested loops (would normally be `O(n^2)`), the second loop's step incrementation is multiplied by 2 each cycle, making it a simpler `O(log n)`, so in total we'd have `O(n) * O(log n)`.


c) `O(1)` because this is just a function declaration and it has not been called, hence the code is not run. If this function was called and we considered the `bunnies` parameter as `n`, it would run at `O(n)`, just like a for loop, but with recursion in this case.

## Exercise II

Suppose that you have an n-story building and plenty of eggs. Suppose also that an egg gets broken if it is thrown off floor f or higher, and doesn't get broken if dropped off a floor less than floor f. Devise a strategy to determine the value of f such that the number of dropped + broken eggs is minimized.

`n` is number of floors in a building
`f` is the floor number at which an egg breaks if dropped
`floorFound` is a flag that will tell us if minimum `f` was found
`droppedEggs` is the number of dropped eggs
`brokenEggs` is the number of broken eggs


### Finding the lowest floor that if I drop an egg, it breaks

def findFloorF(n)
  if n < 1: return n
  set `dropped eggs` to zero
  set `broken eggs` to zero
  set the `f` to zero 
  for nFloor in range(n)
    try to drop egg on floor `nFloor` (0, 1, 2, ...)
    increment `dropped eggs` + 1
    if the egg broke
      increment `broken eggs` + 1
    if the egg did not break
      `f` equals to nFloor - 1
      break from for loop
  return `f`

### The runtime complexity of this function would be `O(n)` 