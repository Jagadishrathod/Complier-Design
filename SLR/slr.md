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

#### Operations defined
* A, S, X:  non‐terminals
* w,x,y,z:  string of terminals and/or non‐terminals
* C:  one terminal or one non‐terminal
#### start:   
if S is a symbol with [S ‐> w] as a production rule, then [S ‐> .w} is the item associated with the
start state.
#### read:   
if [A ‐‐> x.Cz] is an item in some state, then [A ‐‐> xC.z] is associated with some other state.
When performing a read, all the items with the dot before the same C are associated with the same
state. (Note that the dot is before anything, either terminal or non‐terminal.)
#### complete:
if [A ‐‐> x.Xy] is an item, then every rule of the grammar with the form [X ‐‐> .z] must be
included within this state.  Repeat adding items until no new items can be added. (Note that the dot is
before a non‐terminal.)
