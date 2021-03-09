# Generate arbitrary special orthogonal matrices

## Compute a basis for the set of skew symmetric matrices

In section 2.1.2 from [my dissertation](https://diginole.lib.fsu.edu/islandora/object/fsu%3A254496), I describe the special orthogonal group. 
I describe a basis for the Lie Algebra (the tangent space at identity) for the special orthogonal group.
Compute that basis $M_{1,2},\ldots M_{d-1,d}$

## Compute a random skew symmetric basis

Compute random skew symmetric matrix as 
$$
A=\sum_{1\leq i<j \leq d} c_{i,j} M_{i,j}
$$
where  $c_{i,j}$ are randomly generated coefficients between -1 and 1. 
Consider using  `numpy.random.uniform`.

- Check that the matrix is skew symmetric ($A^T=-A$).
- Check that the trace is zero `numpy.trace`

## Project from the tangent space to the manifold

The matrix you computed is skew symetric, which means it is an element of the Lie Algebra for the special orthogonal group. The Lie Algebra is the tangent space at the identity.
When you apply the exponential map, you will get a symmetric matrix as an output.

- Consider using `scipy.linalg.expm`, `scipy.linalg.expm`, `numpy.linalg.det` and `np.matmul`
- Be careful because will return a `numpy.array` instead of a `numpy.matrix`. 
- Verify the outputed matrix is orthogonal with determinant 1.

# generate an arbitrary orthogonal matrix

To get a reflection multiple a special orthogonal matrix by $diag((1,1,\ldots, 1, -1))$.
