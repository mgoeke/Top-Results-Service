# Top-Results-Service
A space to hack away at a coding interview problem that I failed fantastically at during a phone screen

## Problem
```
topN(N,lookback_window)
addEvent(...)
```

### Discovered Constraints
+ Entirely in heap (no state externalization)
+ Prioritize insert speed (way higher levels of addEvent calls to topN calls)
+ UUID is the core return (no need for semantic mapping)

### Initial Thoughts
+ Events need both UUID and timestamp
+ This should be fairly easy using declarative style due to this problem mapping really well to typical functional patterns
  + addEvent -> `map` to collection
  + topN -> `reduce` by window, `group` by UUID and return sorted limit
