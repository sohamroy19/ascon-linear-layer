# ascon-linear-layer
Contains the results of the paper titled "Quantum Implementation of ASCON Linear Layer".

[`ASCON.py`](./ASCON.py) contains the definition of the linear layer as a tuple of tuples.  
[`ASCON.sobj`](./ASCON.sobj) is the same matrix stored in [Sage](https://www.sagemath.org/)'s internal format for efficiency, and can be loaded with [Sage](https://www.sagemath.org/) as follows:
```py
M = load("Ascon.sobj")
```

- [gj.txt](./gj.txt) contains the implementation from the Gauss-Jordan elimination.
- [plu.txt](./plu.txt) contains the implementation from the PLU factorization.
- [xzlbz.txt](./xzlbz.txt) contains the implementation from the modified XZLBZ algorithm.
