# REFACTORING PERFORMANCE APPROACHES

## Time Budgeting
### time and footprint resource allocations
Used in hard realtime systems

## Constant Attention
- All the time, coding to keep performance high
- Downside is changes here tend to make code harder to read
- Doesn't necessarily give a great boost because 90% of the time the program is
slowing down bc one small section of code

## Well Factored
- Code with refactoring then do a performance optimization stage
- Run program thru a profiler
- Profiling allows you to spend optimization time only on that 10% of code that
is slow
