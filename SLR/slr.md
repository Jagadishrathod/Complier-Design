# Constructing a SLR Parse table 
A simple document prepration of slr parse table
* S - Simple 
* L - Left-to-Right Scan of input
* R - Rightmost derivation in reverse

## Create the set of LR(0) states for the parse table
For the rules in an augmented grammar, G’, begin at rule zero and follow the steps below:

### State creation steps (big picture algorithm)
1. Apply the start operation and
2. complete the state:
  * Use one read operation on each item C (non‐terminal or terminal) in the current state  
  to create more states.
  * Apply the complete operation on the new states.
  * Repeat steps  a  and  b  until no more new states can be formed.
