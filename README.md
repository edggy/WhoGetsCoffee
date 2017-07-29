# Who Gets Coffee

A server to decide who is the *lucky* person that fetches the coffee
A provably fair algorithm
2 versions, Aborting and Non-Aborting

## Aborting:

This version allows parties to abort, but they are more likely to be elected.

1. Each person in the group gets assigned a number

1. Each party locally generates a random number, r, and some randomness, s.

1. Then they commit to that randomness and publish, c = Commit(r, s)

1. After all commitments are in (or after a timeout) all parties open their commitments by publishing o = Open(r, s)
    1. If a party doesn’t open or announces an invalid opening, then remove all the indexes from the parties who did open and renumber the non-openers from 0 to N’-1.  For the rest of the protocol set N=N’

1. After all parties open their commitments take all of the r’s and add them together to get R, and the person with number R % N is elected.




## Non-Aborting:

This version tolerates if up to 1/2 of the parties abort.

TODO