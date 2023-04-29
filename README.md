# ascon-linear-layer
This [repository](https://github.com/sohamroy19/ascon-linear-layer) contains the results/codes on the paper, "Quantum Implementation of ASCON Linear Layer".

<img src="./ASCON.png" width="320" title="yellow:0, blue:1"/>


## Files

### Matrix 
- [Ascon.py](./matrix/Ascon.py) contains the specification of the linear layer (which is a 320 × 320 binary matrix) as tuple of tuples data structure.
- [Ascon.sobj](./matrix/Ascon.sobj) is the matrix stored in [Sage](https://www.sagemath.org/)'s internal format for efficiency, and can be loaded as:
 `M = load("Ascon.sobj")`.

### Implementations
- Naïve Quantum
    - [naive.txt](./implementations/naive.txt) contains the naïve quantum implementation (that uses 320 ancilla qubits).

- In-place 
     - [gj.txt](./implementations/gj.txt) contains the implementation from the Gauss-Jordan elimination.
     - [plu.txt](./implementations/plu.txt) contains the implementation from the PLU factorization.
     - [xzlbz.txt](./implementations/xzlbz.txt) contains the implementation from modified [XZLBZ](https://github.com/xiangzejun/Optimizing_Implementations_of_Linear_Layers/).

## Note
1. In all the implementations, the dummy variable `x` is used with its index starting at 0. The qubits are denoted as `x[0]`, `x[1]` and so on.
2. The first line for the in-place implementations indicates the relabel of qubits. It can be realized through a series of SWAP gates.
3. In the naïve quantum implementation, the 320 ancilla qubits are used (denoted as `x[320]`, ..., `x[639]`). Those are initialized at $\ket{0}$, then the original qubits are copied.