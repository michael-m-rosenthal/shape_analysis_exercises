# Computing the center of a shape

In the previous exercise, you learned how center 2D shapes in landmark shape space and the continuous curve shape space.
There is an analogous measure of scale for these two spaces.

Let $C\in \mathbb{R}^{n\times 2}$ denote the shape matrix.
Let $C_{i,j} \in \mathbb{R}$ denote the elements of the shape for $i \in \{ 0,\ldots, n-1\}$ and $j\in \{0,1\}$.
Let $C_i = (C_{i,0},C_{i,1})^T \in \mathbb{R}^2$ denote the 2D coordinates of the shape.

## compute the scale in the landmark shape space



Let $\mu\in \mathbb{R}^2$ denote the center of the points using the landmark shape analysis metrics.
$$
\mu=\frac{1}{n}\sum_{i=0}^{n-1} C_i
$$
For the landmark shape space, the scale of the curve is computed as
$$
\|C\|=\sqrt{\sum_{i=0}^{n-1}(C_{i}-\mu)^T(C_{i}-\mu)}
$$
Note that $C_{i}-\mu$ is represented as a 2D column vector so that the term is the dot product.

One can remove the effect of scale by first translating the curve to the origin and then dividing by the scale.

- Translate the points in `data['C'][0,:,0],data['C'][1,:,0]` using the mean computed in the landmark-base shape space and use `matplotlib.pyplot.scatter`
- compute the scale of the first curve in the landmark shape space. 
- plot the landmarks after centering and scaling them

## compute the scale in the shape space for continuous curves

Let $d_0=0$ and let $d_i= \|C_{i}-C_{i-1}\|$ for $i \in \{ 1,\ldots, n-1\}$.
Let 
$$
t_i= \frac{\sum_{j=0}^i d_j}{\sum_{j=0}^{n-1} d_j}
$$
for each $i \in \{ 0,\ldots, n-1\}$.
Assume that the curve $\beta:[0,1]\rightarrow \mathbb{R}^2$ is piecewise-linear with $\beta(t_i)= C_i$  for each $i \in \{ 0,\ldots, n-1\}$ .

Let $\mu\in \mathbb{R}^2$ denote the center of the points using the continuous curve shape analysis metrics.
$$
\mu=\int_{t=0}^1 \beta(t) dt
$$
For the continuous curve shape space, the scale of the curve is computed as
$$
\|C\|=\sqrt{\int_{t=0} (\beta(t)-\mu)^T(\beta(t)-\mu) dt}
$$
Note that $\beta(t)-\mu$ is represented as a 2D column vector so that the term in the integral is the dot product.
One can remove the effect of scale by first translating the curve to the origin and then dividing by the scale.
The normalized (a.k.a. scale-centered) curve is computed as $(\beta(t)-\mu)/\|C\|$ for each $t \in [0,1]$.

- Translate the points in `data['C'][0,:,0],data['C'][1,:,0]` using the mean computed using the continuous curve shape space and use `matplotlib.pyplot.scatter`
- compute the normalized curve
- plot the curve after centering and rescaling
  
## Plot the scale-centered landmark shape and the scale-centered curve on the same plot 

Plot the landmark shape and continuous curve shape together in one plot to see that they are different.
