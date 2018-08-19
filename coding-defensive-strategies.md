# CODING DEFENSIVE STRATEGIES

## The Eight Defensive Programmer Strategies
Once you've adopted this mindset, you can then rewrite your prototype and
follow a set of eight strategies I use to make my code as solid as I can. While
I work on the "real" version I ruthlessly follow these strategies and try to
remove as many errors as I can, thinking like someone who wants to break the
software

- Never Trust Input
- Never trust the data you are given and always validate it.
- Prevent Errors
- If an error is possible, no matter how probable, try to prevent it
- Fail Early And Openly
- Fail early, cleanly, and openly, stating what happened, where and how to fix
it
- Document Assumptions
- Clearly state the pre-conditions, post-conditions, and invariants
- Prevention Over Documentation
- Do not do with documentation, that which can be done with code or avoided
completely
- Automate Everything
- Automate everything, especially testing
- Simplify And Clarify
- Always simplify the code to the smallest, cleanest form that works without
sacrificing safety
- Question Authority
- Do not blindly follow or reject rules
