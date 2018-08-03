# SOFTWARE DESIGN OBSERVER

## PARTS
### subscribers
The Observer Pattern defines a one-to-many dependency between objects so that when one object changes state, all of its dependents are notified and updated automatically.

### One to many
Each subject can have many observers

### Subject
Adds observers
Removes observers
Notifies observers

### Loosely coupled
- add new observers at any time.
- never need to modify the subject to add new types of observers.
- can reuse subjects or observers independently of each other.
- changes to either the subject or an observer will not affect the other.
