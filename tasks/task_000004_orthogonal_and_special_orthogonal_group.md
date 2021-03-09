# Generate arbitrary orthogonal matrices

It is useful to be able to generate arbitrary orthogonal and special orthogonal matrices to work with while you are learning about these geometries. 
This will show you one way to do so.

# Compute a basis for the set of skew symmetric matrices

In section 2.1.2 from [my dissertation](https://diginole.lib.fsu.edu/islandora/object/fsu%3A254496), I describe the special orthogonal group. 
Compute that basis $M_{1,2},\ldots M_{d-1,d}$.

# Compute a random skew symmetric basis

Compute random skew symmetric matrix as 
$$
A=\sum_{1\leq i<j \leq d} c_{i,j} M_{i,j}
$$
where  $c_{i,j}$ are randomly generated coefficients between -1 and 1. 

- Consider using  `numpy.random.uniform`.
- Check that the matrix is skew symmetric ($A^T=-A$).
- Check that the trace is zero `numpy.trace`

# Project from the tangent space to the manifold

The matrix you computed in the previous part is skew symetric, which means it is an element of the Lie Algebra for the special orthogonal group. 
The Lie Algebra is the tangent space at the identity.
When you apply the exponential map, you should get a special orthogonal matrix as an output.

- Be careful because `scipy.linalg.expm` will return a `numpy.array` instead of a `numpy.matrix`. 
- Consider using `scipy.linalg.expm`, `numpy.linalg.det` and `np.matmul`
- Verify the outputted matrix is orthogonal with determinant 1.

# Generate an arbitrary orthogonal matrix

To get a reflection multiply special orthogonal matrix with $diag((1,1,\ldots, 1, -1))$.

- Verify the outputted matrix is orthogonal with determinant -1.
