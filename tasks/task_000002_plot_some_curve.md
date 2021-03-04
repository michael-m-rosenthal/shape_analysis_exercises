# plot curves found in the toydata.mat

Do the previous exercise before moving onto this one.

In the previous exercise, you loaded `toydata.mat` using the `scipy.io.loadmat` function. Now it is time to plot some curves. 


In the closed_curves_2D directory, there is a file called `toydata.mat`.
This is a matlab data file with some closed curves.
You will need to learn how to read this data into python3.

We will want to more python modules installed: `numpy` and `matplotlib`
They can be installed using the following `pip3` commands:

```
pip3 install numpy
pip3 install matplotlib
```

Once they are installed, you import them into you python script and create aliases for them.
The standard alias you will find in most web tutorials are below.

```
import scipy.io as sio
import numpy as np
import matplotlib.pyplot as plt

# load the data
data = sio.loadmat('closed_curves_2D/toydata.mat')

# Examine the data 
data.keys()
# ignore the keys beginning and ending with `__`. There is only one variable called `C` (C for curves).

# Examine the `C` data
d,n,N=data['C'].shape

# d is the dimension of space the curve is in (2D plane)
# n is the number of points in the curve
# N is the number of curves
# so you have 1300 2D curves with 100 points each.

# print the first curve to screen
print(data['C'][:,:,0] )

# put your code here to plot the curve
```


Use the `matplotlib.pyplot.plot` function and `matplotlib.pyplot.show` function to plot the first curve.
