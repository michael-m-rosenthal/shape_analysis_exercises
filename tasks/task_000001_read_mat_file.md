# read a mat file in python

In the closed_curves_2D directory, there is a file called `toydata.mat`.
This is a matlab data file with some closed curves.
You will need to learn how to read this data into python3.

You can accomplish this with the `scipy.io.loadmat` function.
To use this function, you will need to install the `scipy` module.
Assuming you have already installed `python3`, you can install new modules with the `pip3` command.

```
pip3 install scipy
```

If you are using windows with a version of python less than 3.5.3, then you may need to use the following command:

```
py.exe -m pip3 install scipy
```

After it installs, you can load `scipy.io` module and give it a (short alias)[https://stackoverflow.com/questions/706595/can-you-define-aliases-for-imported-modules-in-python] with the following command.


```
import scipy.io as sio
```

This will allow you to use the `scipy.io.loadmat` function using `sio.loadmat`.
If you do an online search for `scipy.io.loadmat`, you will find detailed examples for using the function. 

(See this one)[https://docs.scipy.org/doc/scipy/reference/generated/scipy.io.loadmat.html] and then try to write a python script which will load `toydata.mat`.
