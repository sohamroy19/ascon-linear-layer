# ascon-linear-layer
This [repository](https://github.com/sohamroy19/ascon-linear-layer) contains the results/codes on the paper, "Quantum Implementation of ASCON Linear Layer".

<img src="./ASCON.png" width="320" title="yellow:0, blue:1"/>


## Files

### Matrix 
- [Ascon.py](./matrix/Ascon.py) contains the specification of the linear layer (which is a 320 × 320 binary matrix) as tuple of tuples data structure.
- [Ascon.sobj](./matrix/Ascon.sobj) is the matrix stored in [Sage](https://www.sagemath.org/)'s internal format for efficiency, and can be loaded as:
 `M = load("Ascon.sobj")`.

### Implementations
- Naive Quantum
    - [naive.txt](./implementations/naive.txt) contains the naive implementation that uses 320 ancillary qubits initialized to 0 appended to the first 320 qubits.

- In-place *(The first line indicates the relabel of qubits and it can be implemented through a series of SWAP gates)*
     - [gj.txt](./implementations/gj.txt) contains the implementation from the Gauss-Jordan elimination.
     - [plu.txt](./implementations/plu.txt) contains the implementation from the PLU factorization.
     - [xzlbz.txt](./implementations/xzlbz.txt) contains the implementation from modified [XZLBZ](https://github.com/xiangzejun/Optimizing_Implementations_of_Linear_Layers/).
