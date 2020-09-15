---
layout: post
title: "ML4T-笔记---01-03-The-power-of-NumPy"
date:
categories: 计算机科学
excerpt:
auth: conge
---
* content
{:toc}

# Lesson 4

##  01 - What is NumPy
![ ](/assets/images/计算机科学/118382-c6e80d5e80104bf5.png)

NumPy:
* is a Python library that acts as a wrapper around underlying C and Fortran code. Thus, very fast.
* focuses on matrices which are called in nd-arrays.
It's syntax is very similar to MATLAB, 

# 02 - Lesson outline

> *If you're familiar with NumPy (esp. the following operations), feel free to skim through this lesson.*
> 
> *   Create a NumPy array:
>     *   from a pandas dataframe: [pandas.DataFrame.values](http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.values.html)
>     *   from a Python sequence: [numpy.array](http://docs.scipy.org/doc/numpy/reference/generated/numpy.array.html)
>     *   with constant initial values: [numpy.ones](http://docs.scipy.org/doc/numpy/reference/generated/numpy.ones.html), [numpy.zeros](http://docs.scipy.org/doc/numpy/reference/generated/numpy.zeros.html)
>     *   with random values: [numpy.random](http://docs.scipy.org/doc/numpy/reference/routines.random.html)
> *   Access array attributes: [shape](http://docs.scipy.org/doc/numpy/reference/generated/numpy.ndarray.shape.html), [ndim](http://docs.scipy.org/doc/numpy/reference/generated/numpy.ndarray.ndim.html), [size](http://docs.scipy.org/doc/numpy/reference/generated/numpy.ndarray.size.html), [dtype](http://docs.scipy.org/doc/numpy/reference/generated/numpy.ndarray.dtype.html)
> *   Compute statistics: [sum](http://docs.scipy.org/doc/numpy/reference/generated/numpy.sum.html), [min](http://docs.scipy.org/doc/numpy/reference/generated/numpy.min.html), [max](http://docs.scipy.org/doc/numpy/reference/generated/numpy.max.html), [mean](http://docs.scipy.org/doc/numpy/reference/generated/numpy.mean.html)
> *   Carry out arithmetic operations: [add](http://docs.scipy.org/doc/numpy/reference/generated/numpy.add.html), [subtract](http://docs.scipy.org/doc/numpy/reference/generated/numpy.subtract.html), [multiply](http://docs.scipy.org/doc/numpy/reference/generated/numpy.multiply.html), [divide](http://docs.scipy.org/doc/numpy/reference/generated/numpy.divide.html)
> *   Measure execution time: [time.time](https://docs.python.org/2/library/time.html#time.time), [profile](https://docs.python.org/2/library/profile.html)
> *   Manipulate array elements: Using [simple indices and slices](http://docs.scipy.org/doc/numpy/reference/arrays.indexing.html#basic-slicing-and-indexing), [integer arrays](http://docs.scipy.org/doc/numpy/reference/arrays.indexing.html#integer-array-indexing), [boolean arrays](http://docs.scipy.org/doc/numpy/reference/arrays.indexing.html#boolean-array-indexing)


# 03 - Relationship to Pandas
![](/assets/images/计算机科学/118382-131f64033896f705.png)

Pandas is a kind of wrapper for NumPy.

* Data frame is just a wrapper around this ndarray, access the columns with symbols and the rows by dates. And you CAN treat DF as an ndarray directly.
*However, data frame allow us get many more routines.

## 04 - Notes on Notation

![](/assets/images/计算机科学/118382-9f7c6833ed04ad0a.png)

how to access cells within ndarray.
> nd1(row,col)

*  in NumPy, our columns and rows begin at 0. nd1[0,0] is the first item.
###  slicing: address sub portion of the nd array?
* Use the colon `:`
> nd1[0:3,1:3]

[0:3,1:3] indicates starting at the zeroth row to just __before__ the third and the first column to just __before__ the third. The last value is __one past__ the one that you actually want to include.

* use the colon by itself in the rows position to access all of the rows.
* Negative index: the last row = -1, the second to last row would be -2.

## 5. Quiz: Replace a slice
![answer to the quiz](/assets/images/计算机科学/118382-724dc94c1ffdb7c0.png)
Suppose we have these two ND arrays, nd1 and nd2. And we want to replace some of the values in nd1, with these values from nd2.

Which are correct?

## 06 - Creating NumPy arrays

* You can access the underlining NumPy array within a Pandas data frame using the values property.

### Let's create NumPy arrays from scratch.

 one dimensional array from known values.
![](/assets/images/计算机科学/118382-dd2c2b4fe3351dcf.png)

Use the __array__ function to convert most array-like objects into an ndarray.

* The code above import the library numpy and rename it as np, then call a function np.array and pass a list which has value [2,3,4].
* np.array function can take as input a list, a template, or other sequences.

![](/assets/images/计算机科学/118382-ec8a1f93bd8100d9.png)

Now create a 2D array by passing in a sequence of sequences to the np.array function.
* the sequence of sequences are a list of lists or tuple of lists...

## 07 - Arrays with initial values
![Empty array](/assets/images/计算机科学/118382-83f1a733b1815711.png)

* `np.empty()` function takes the shape of the array as input.
* For the example above, we will create an empty array with five rows.
* Passing in a tuple with values 5 and 4 will create an empty array with five rows and four columns.
* just add another number to the sequence to create arrays of higher dimension.
* __The empty array is not actually empty!!!__ the elements of the array read in whatever values were present in the corresponding memory location.
* And by default the elements are the floating points.


![np.ones](/assets/images/计算机科学/118382-62af1e6d94bcc45b.png)

Next, we create an array full of ones.
using `np.ones()`, the above example creates an array of 5 rows and 4 columns with all the values equal to 1.

## 08 - Specify the datatype

![ ](/assets/images/计算机科学/118382-055b6a4969c07d16.png)

What parameter do you need to add to this function to create an array of integers instead?

Documentation for the `array.ones()` function might be helpful.
> Documentation: [numpy.ones](http://docs.scipy.org/doc/numpy/reference/generated/numpy.ones.html)
> 
> *   [numpy.ones](http://docs.scipy.org/doc/numpy/reference/generated/numpy.ones.html)
> *   [Data types](http://docs.scipy.org/doc/numpy/user/basics.types.html)
> 
> NumPy User Guide: [Data types](http://docs.scipy.org/doc/numpy/user/basics.types.html)
> 
> #### Documentation:
> 
> *   [numpy.empty](http://docs.scipy.org/doc/numpy/reference/generated/numpy.empty.html)
> *   [numpy.ones](http://docs.scipy.org/doc/numpy/reference/generated/numpy.ones.html)
> *   [numpy.zeros](http://docs.scipy.org/doc/numpy/reference/generated/numpy.zeros.html)
> *   [numpy.array](http://docs.scipy.org/doc/numpy/reference/generated/numpy.array.html)
> *   [numpy.ndarray](http://docs.scipy.org/doc/numpy/reference/generated/numpy.ndarray.html) (direct `ndarray` constructor)

Answer: dtype is the parameter the values to be integers using NumPy data type np.int_.

## 09 - Generating random numbers
### Numpy functions to generate arrays filled with random values.
> np.random.random(), np.random.rand(), np.random.normal(),
![np.random.random](/assets/images/计算机科学/118382-3e528d2ba2b1be22.png)

*the `np.random.random()` function generates __uniformly sampled__ floating point values in [0.0, 1.0).
* Note: the array shape is a tupple, however, np.random.rand() accepts a sequence of numbers as arguments and straight of the tuple. `np.random.rand(5,4) is give the same results as np.random.random((5,4))`. Numpy provides this to achieve compatibility with the  Matlab syntax.

### What if you wanted a sample from a different distribution?
![](/assets/images/计算机科学/118382-2d431d04e1217f5d.png)

`np.random.normal()` function samples from normal distribution. the function also accepts mean and std of the distribution as input.

To generate integers, use the `np.random.randint()` function
![](/assets/images/计算机科学/118382-0d5fb178bb7e000d.png)

* Passing to values 0 and 10, `np.random.randint()` WILL generate a single integer between the range 0 and 10.
* Passing size= 5 to `np.random.randint()` to generate  5 integers between 0 and 10.
* passing a tuple value to the attribute size, which will create a 2d array with all the values between the range 0 and 10.
* Check out the random sampling routines on the numpy website for more distribution and usage radiations.

> NumPy Reference: [Random sampling](http://docs.scipy.org/doc/numpy/reference/routines.random.html)
> 
> #### Sampling functions:
> 
> *   [numpy.random.random](http://docs.scipy.org/doc/numpy/reference/generated/numpy.random.random.html): Samples a Uniform distribution in [0.0, 1.0)
> *   [numpy.random.rand](http://docs.scipy.org/doc/numpy/reference/generated/numpy.random.rand.html): Like `random`, but slightly different syntax
> *   [numpy.random.normal](http://docs.scipy.org/doc/numpy/reference/generated/numpy.random.normal.html): Normal or Gaussian distribution
> *   [numpy.random.randint](http://docs.scipy.org/doc/numpy/reference/generated/numpy.random.randint.html): Integers from Uniform distribution

## 10 - Array attributes

__Attributes like size and shape are very useful when you have to over array elements to perform some computation.__

given ndarray a, ` a = np.random.random((5,4))`:
`a.shape` will return the __shape__ of it as a tuple ( (5,4))
`a.shape[0]` will return number of rows (5)
`a.shape[1]` will return number of columns (4)
`len(a.shape)`  and `a.ndim` will return the __dimension__ of the array, e.g. a has 2 dimensions
`a.size` returns the total number of elements in an array.
`a.dtype` checks the data type of the values present in array A.

> Attributes of [numpy.ndarray](http://docs.scipy.org/doc/numpy/reference/generated/numpy.ndarray.html):
> 
> *   [numpy.ndarray.shape](http://docs.scipy.org/doc/numpy/reference/generated/numpy.ndarray.shape.html): Dimensions (height, width, ...)
> *   [numpy.ndarray.ndim](http://docs.scipy.org/doc/numpy/reference/generated/numpy.ndarray.ndim.html): No. of dimensions `= len(shape)`
> *   [numpy.ndarray.size](http://docs.scipy.org/doc/numpy/reference/generated/numpy.ndarray.size.html): Total number of elements
> *   [numpy.ndarray.dtype](http://docs.scipy.org/doc/numpy/reference/generated/numpy.ndarray.dtype.html): Datatype


Time: 00:02:33

## 11 - Operations on ndarrays

__mathematical operations on np arrays__

* Use `seed` to generate random numbers

```
import numpy as np

np.random.seed(693)
a = np.random.randint(0,10, size = (5,4))
```

The output is an array with five rows, four columns, and all the values between the range 0 and 10. And since `seed` function is used, the random number generator with the constant, to get the same sequence of numbers every time.

* Summing  
![](/assets/images/计算机科学/118382-48faf6f158dfbfc2.png)

`a.sum()` sums all the elements in an array
`a.sum(axis = 0)` returns the sum of each __columns__.
`a.sum(axis = 1)` returns the sum of each __rows__.

*  minimum, maximum, and mean of an array.
![](/assets/images/计算机科学/118382-e477f722180845b0.png)

`a.min(axis = 0)` minimum of each column
`a.max(axis = 1)` the maximum of each row
`a.mean()` the mean of the entire array.

* More operations:
> #### NumPy Reference: [Mathematical functions](http://docs.scipy.org/doc/numpy/reference/routines.math.html)
> 
> *   [numpy.sum](http://docs.scipy.org/doc/numpy/reference/generated/numpy.sum.html): Sum of elements - along rows, columns or all
> *   [numpy.min](http://docs.scipy.org/doc/numpy/reference/generated/numpy.min.html), [numpy.max](http://docs.scipy.org/doc/numpy/reference/generated/numpy.max.html), [numpy.mean](http://docs.scipy.org/doc/numpy/reference/generated/numpy.mean.html): Simple statistics
> 
> Also: [numpy.random.seed](http://docs.scipy.org/doc/numpy/reference/generated/numpy.random.seed.html) to (re)set the random number generator.

Time: 00:03:40

## 12 - Quiz Locate maximum value

* finding the position of some element in an array

![](/assets/images/计算机科学/118382-e088fc070936be40.png)

The answer could also be `return a.argmax()`
> NumPy Reference: [Sorting, searching, and counting](http://docs.scipy.org/doc/numpy/reference/routines.sort.html)

## 13 - Timing python operations

![](/assets/images/计算机科学/118382-64e3b47a677a5d49.png)

* how to time a particular operation.

the _time_ library can help us know how fast our operation is.

capture the time snapshot before and after the operation is performed and subtract the two times.

Time: 00:00:56
> #### Documentation:
> 
> *   [time.time](https://docs.python.org/2/library/time.html#time.time): Time in seconds, as a floating-point number


## 14 - How fast is NumPy

This module demos how fast NumPy can perform certain operations. will skip this one. All you need to know is that NumPy is fast

> #### Documentation:
> 
> *   [time.time](https://docs.python.org/2/library/time.html#time.time): Current time in seconds (float value)
> *   [timeit](https://docs.python.org/2/library/timeit.html): Average execution time measurement
> *   [profile](https://docs.python.org/2/library/profile.html): Code profiling
> 
> #### iPython "[magics](https://ipython.org/ipython-doc/dev/interactive/tutorial.html#magic-functions)":
> 
> *   [%time](https://ipython.org/ipython-doc/dev/interactive/magics.html#magic-time): How long does it take to run once
> *   [%timeit](https://ipython.org/ipython-doc/dev/interactive/magics.html#magic-timeit): Averaged over multiple runs
> *   [%prun](https://ipython.org/ipython-doc/dev/interactive/magics.html#magic-prun)/[%lprun](https://ipython.org/ipython-doc/dev/interactive/magics.html#magic-lprun): Per-function/line profiling



## 15 - Accessing array elements

`a[3,2]`
`a[0:2, 0:2]`
`a[:,0:3:2` n is to m is to t, will give you values in the range n before m, but in steps of size t, hence this statement will give you values of the column 0.Skip the values of the column one, and then give the values of the column 2.

> NumPy Reference: [Indexing](http://docs.scipy.org/doc/numpy/reference/arrays.indexing.html)
> 
> Note: Indexing starts at `0` (zero).

Time: 00:02:29

## 16 - Modifying array elements

`a[0, 0] = 1` This will give us access to the element at the position 0, 0 in the a and Using the assignment operator `=` to assign a value one to it.

`a[0, :] = 2` can assign value of 2 to the entire row.

`a[:, 3] = [1, 2, 3, 4, 5]` can assign a list of values to a row or a column.

Time: 00:01:32

# 17 - Indexing an array with another array


![image.png](/assets/images/计算机科学/118382-66ce3239392d4f67.png)
* NumPy array can be indexed with other arrays.

the length of the indices array and the returned array will be the same. Also it return value from array a at index 1,1,2,3.

> #### NumPy Reference: [Indexing](http://docs.scipy.org/doc/numpy/reference/arrays.indexing.html)
> 
> *   [Integer array indexing](http://docs.scipy.org/doc/numpy/reference/arrays.indexing.html#integer-array-indexing): Select array elements with another array

Time: 00:01:33

## 18 - Boolean or mask index arrays

![](/assets/images/计算机科学/118382-cf597d3e8ccb8b5d.png)

`a[a < mean]` for each value in array A, compare it with the mean, If it is less, we retain the value.

`a[a < mean] = mean` replace these values with the mean value.

> #### NumPy Reference: [Indexing](http://docs.scipy.org/doc/numpy/reference/arrays.indexing.html)
> 
> *   [Integer array indexing](http://docs.scipy.org/doc/numpy/reference/arrays.indexing.html#integer-array-indexing)
> *   [Boolean array indexing](http://docs.scipy.org/doc/numpy/reference/arrays.indexing.html#boolean-array-indexing)

Time: 00:01:47

## 19 - Arithmetic operations

* Arithmetic operations on arrays are always applied element-wise.

`2 * a` it is element-wise multiplication.

`a / 2.0` if the array and the divisor are integers, the output will also be integers. Using 2.0 instead of 2 as the divisor, we will get float values.

![ ](/assets/images/计算机科学/118382-bd2bd1a22a11c20f.png)

* important note: the shape of a and b should be similar before the operation a + b, else it will throw error.

`a + b`
![ ](/assets/images/计算机科学/118382-3fd06ba9789a5ef0.png)

`a * b`
![image.png](/assets/images/计算机科学/118382-4b20fd0b00093f43.png)

`a / b`

![ ](/assets/images/计算机科学/118382-983ab375f47e51a7.png)

As seen before, since array a and b are integers, we get the final array in the form of integers as well. convert one of the arrays to float to get results as float .

## 20- Learning more NumPy

> #### Resources from NumPy [User Guide](http://docs.scipy.org/doc/numpy/user/index.html) and [Reference](http://docs.scipy.org/doc/numpy/reference/index.html):
> 
> *   [The N-dimensional array](http://docs.scipy.org/doc/numpy/reference/arrays.ndarray.html)
> *   [Data types](http://docs.scipy.org/doc/numpy/user/basics.types.html)
> *   [Array creation](http://docs.scipy.org/doc/numpy/user/basics.creation.html) [[more](http://docs.scipy.org/doc/numpy/reference/routines.array-creation.html)]
> *   [Indexing](http://docs.scipy.org/doc/numpy/user/basics.indexing.html) [[more](http://docs.scipy.org/doc/numpy/reference/arrays.indexing.html)]
> *   [Broadcasting](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)
> *   [Random sampling](http://docs.scipy.org/doc/numpy/reference/routines.random.html)
> *   [Mathematical functions](http://docs.scipy.org/doc/numpy/reference/routines.math.html)
> *   [Linear algebra](http://docs.scipy.org/doc/numpy/reference/routines.linalg.html)


Time: 00:00:16

Total Time: 00:35:59

```
First Draft 2019-01-10
```
