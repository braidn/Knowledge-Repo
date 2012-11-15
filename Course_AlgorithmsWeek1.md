###Lecture Notes

* Convenient to keep object names to 0 to N-1. Especially good for
   dealing with arrays.
* If objects are "connected" to one another than they follow 3 simple
   rules...
* Reflexive: _p_ is connected to _p_ (connected to itself)
* Symetic: _p_ is connected to _q_ therefore _q_ is connected to _p_
* Transitive: _p_ is connected to _q_ and _q_ is connected to _r_
      then _p_ is connected to _r_
* Find query: check if two objectes are in the same component
* Union command: restructure components after two objects are connected
* When dealing with Arrays, changing connected items can get burdensom
   because all of the ID's will need to be changed...
* this is sometimes known as quadratic time or "quick find"

###Quick Union

* Different than Quick find due to the way id's are used to describe
  "root nodes". Think of a decending forest of items.
* Unions are changed by ONLY changing the root, not the rest of the IDs
* [Slide 19][1] for a good diagram.
* Roots of the component change therefore if union(9,4) and 4 = 8 - 3 -
  4, then 9 would get ID of 8 to connect all the way down to 4. This
  would mean that 9 is ALSO connected to 8 and 3
* _Fails_ when trees get too large and the search for a "root" takes way
  too long.

###Improved Quick union (Weighted)

* Weighted QU is where you would keep track of the size of each tree and
  __always__ root from smaller tree -> larger tree.
* Basically, the smaller tree will always be attached to the larger
  tree, regardless of the way the union command is specified.
* Ensures that no 1 item is too far from the root of the tree.
* _Find_ is identical to the original QU
* Base of any node is [lg][2](base 2) N (objects in list)
* _Union_ time is constant given roots

###Path Compression

* Find distance from X to root. Then set every node touched on the path
  to the direct decendent of root.
* [Example][1] (Slide 28)
* Simple, usually defined with one line of code.
* The time taken is nearly linear; however, theory claims there are no union/find
  linear algorithms.

###Union-Find Application Use

[Percolation][3]

[1]: http://www.cs.princeton.edu/~rs/AlgsDS07/01UnionFind.pdf
[2]: https://en.wikipedia.org/wiki/Logarithm
[3]: https://en.wikipedia.org/wiki/Percolation_theory
