# Jupyter Lab

[Source](https://youtu.be/A5YyoCKxEOU)

JupyterLab is a next-generation web-based user interface for Project Jupyter.

Jupter Notes has two modes:

1. Command Mode designed for navigating and changing the framework of your notebook.

The framework is composed of cells that keepyour data and code in little containers.

**Shortcuts**

* `a`- Add a cell above

* `b` - Add a cell below

* `c` - copy cell

* `v` - paste cell

* `x` - cut cell

* `dd` - delete

* `z` - undo

* `shift + z` - redo

* `y` - Cell format: Code

* `m` - cell format: Markdown

* `shift + enter` - run cell

* `0 0` - restart kernel

## Numpy

[Source](https://www.dataquest.io/blog/numpy-tutorial-python/)

`NumPy` is a commonly used Python data analysis package.

Developed in the mid 2000s, and arose from an even older package called Numeric. This longevity means that almost every data analysis or machine learning package for Python leverages NumPy in some way.

With NumPy, we work with `multidimensional arrays`.

A 2-dimensional array is also known as a `matrix,`

We can create a NumPy array using the `numpy.array function.`

***One of the limitations of NumPy is that all the elements in an array have to be of the same type***

It’s possible to use NumPy to directly read csv or other files into arrays. We can do this using the `numpy.genfromtxt` function.

****Slicing NumPy Arrays**

 A colon indicates that we want to select all the elements from the starting index up to but not including the ending index. This is also known as a `slice`:

 How to select an entire row example:

```
Wine[3,:]
```

How to select an entire column example:

```
[:,3]
```

How to select an entire array

```
[:,:]
```

We can also use indexing to ***assign values*** to certain elements in arrays. We can do this by assigning directly to the indexed value:

examples

```wines[1,5] = 10
```

```
wines[:,10] = 50
# 
```

You can find the data type of a NumPy array by accessing the `dtype `property:

You can use the `numpy.ndarray.astype` method to convert an array to a different type. The method will actually copy the array, and return a new array with the specified data type. 

NumPy makes it simple to perform mathematical operations on arrays. This is one of the primary advantages of NumPy, and makes it quite easy to do computations.

```
wines[:,11] + 10
array([ 15., 15., 15., ..., 16., 15., 16.])
```

Note that the above operation won’t change the wines array — it will return a new 1-dimensional array where 10 has been added to each element in the quality column of wines.

If we instead did +=, we’d modify the array in place:
An example of this is the numpy.ndarray.sum method. This finds the sum of all the elements in an array by default:

finds the sum of every row

```wines.sum(axis=0)```

finds the sum of every column

```wines.sum(axis=1)```

We can use the ```numpy.ravel``` function to turn an array into a one-dimensional representation. It will essentially flatten an array into a long sequence of values:
Here’s an example where we can see the ordering of numpy.ravel:

```
array_one = np.array(
    [
        [1, 2, 3, 4],
        [5, 6, 7, 8]
    ]
)
array_one.ravel()
array([1, 2, 3, 4, 5, 6, 7, 8])
```

Finally, we can use the ```numpy.reshape function``` to reshape an array to a certain shape we specify.

We can use ```numpy.vstack``` to vertically stack multiple arrays

