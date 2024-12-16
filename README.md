# Persistent-Homology

Implementation of an algorithm to compute persistent homology with coefficients in the field Z/2Z as described [here][1]
-
## How to Run the Program

1. Update the variable `file_path` in the code to point to the desired text file.
2. Execute all cells in the notebook.
3. The output will be saved as `output.txt` in the same directory as the notebook.

## Input:
The input to the program is a filtration given in an ASCII file with the following format, where each line represents a simplex sigma and is of the form:

`f(sigma)` `dim(sigma)` `v_0 ... v_{dim(sigma)}`


### Where:
- `f(sigma)` is the function value of `sigma` (its "time of appearance" in the filtration).
- `dim(sigma)` is the dimension of `sigma`
- `v_0 ... v_{dim(sigma)}` are the IDs (integers) of the vertices of `sigma`.

## Output:
The output of the program is the barcode corresponding the the filtration as

- Each line represents one interval and contains 3 numbers separated by white space:
  1.   The dimension of the homological feature associated with the interval
  2.   The left endpoint of the interval (which is the filtration value associated with the simplex that created the homological feature)
  3.   The right endpoint of the interval (which is the filtration value associated with the simplex that killed the homological feature)

The barcodes for some important shapes _(Torus, Klein Bottle, Moeibius Strip, Projective Plane, ...)_ are saved as `.png` files under `./Barcodes`

For instance, interval `[b,d)` in dimension `k` is written `k b d`.

---

[1]: https://www.enseignement.polytechnique.fr/informatique/INF556/TD4/index.html
