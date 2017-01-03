# Here are some numpy api functions you may needed
### A Simple Numpy Example

Before we can use NumPy we will have to import it. It has to be imported like any other module:

import numpy
But you will hardly ever see this. Numpy is usually renamed to np:

import numpy as np
We have a list with values, e.g. temperatures in Celsius:

cvalues = [25.3, 24.8, 26.9, 23.9]
We will turn this into a one-dimensional numpy array:

C = np.array(cvalues)
print(C)
[ 25.3  24.8  26.9  23.9]
Let's assume, we want to turn the values into degrees Fahrenheit. This is very easy to accomplish with a numpy array. The solution to our problem can be achieved by simple scalar multiplication:

print(C * 9 / 5 + 32)
[ 77.54  76.64  80.42  75.02]
Compared to this, the solution for our Python list is extremely awkward:

fvalues = [ x * 9/5 + 32 for x in cvalues]
print(fvalues)
[77.54, 76.64, 80.42, 75.02]
### Two- and Multidimensional Arrays
Of course, arrays of NumPy are not limited to one dimension. They are of arbitrary dimension. We create them by passing nested lists (or tuples) to the array method of numpy.
A = np.array([ [3.4, 8.7, 9.9],
               [1.1, -7.8, -0.7],
               [4.1, 12.3, 4.8]])
print(A)
print(A.ndim)
[[  3.4   8.7   9.9]
 [  1.1  -7.8  -0.7]
 [  4.1  12.3   4.8]]
2
B = np.array([ [[111, 112], [121, 122]],
               [[211, 212], [221, 222]],
               [[311, 312], [321, 322]] ])
print(B)
print(B.ndim)
[[[111 112]
  [121 122]]
 [[211 212]
  [221 222]]
 [[311 312]
  [321 322]]]
3
### Shape of an Array

Shape of a two-dimensional array
The function "shape" returns the shape of an array. The shape is a tuple of integers. These numbers denote the lengths of the corresponding array dimension. In other words: The "shape" of an array is a tuple with the number of elements per axis (dimension). In our example, the shape is equal to (6, 3), i.e. we have 6 lines and 3 columns.

x = np.array([ [67, 63, 87],
               [77, 69, 59],
               [85, 87, 99],
               [79, 72, 71],
               [63, 89, 93],
               [68, 92, 78]])
print(np.shape(x))
(6, 3)
There is also an equivalent array property:

print(x.shape)
(6, 3)
Numbering of axis
### Indexing and Slicing

Assigning to and accessing the elements of an array is similar to other sequential data types of Python, i.e. lists and tuples. We have also many options to indexing, which makes indexing in Numpy very powerful and similar to core Python.

Single indexing is the way, you will most probably expect it:

F = np.array([1, 1, 2, 3, 5, 8, 13, 21])
# print the first element of F, i.e. the element with the index 0
print(F[0])
# print the last element of F
print(F[-1])
B = np.array([ [[111, 112], [121, 122]],
               [[211, 212], [221, 222]],
               [[311, 312], [321, 322]] ])
print(B[0][1][0])
1
21
121
Indexing multidimensional arrays:

A = np.array([ [3.4, 8.7, 9.9],
               [1.1, -7.8, -0.7],
               [4.1, 12.3, 4.8]])
print(A[1][0])
1.1
We accessed the element in the second row, i.e. the row with the index 1, and the first column (index 0). We accessed it the same way, we would have done with an element of a nested Python list. There is another way to access elements of multidimensional arrays in numpy.

There is also an alternative: We use only one pair of square brackets and all the indices are separated by commas:

print(A[1, 0])
1.1
You have to be aware of the fact, that the second way is more efficient. In the first case, we create an intermediate array A[1] from which we access the element with the index 0. So it behaves similar to this:

tmp = A[1]
print(tmp)
print(tmp[0])
[ 1.1 -7.8 -0.7]
1.1
We assume that you are familar with the slicing of lists and tuples. The syntax is the same in numpy for one-dimensional arrays, but it can be applied to multiple dimensions as well.

The general syntax for a one-dimensional array A looks like this:

A[start:stop:step]

We illustrate the operating principle of "slicing" with some examples. We start with the easiest case, i.e. the slicing of a one-dimensional array:

S = np.array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
print(S[2:5])
print(S[:4])
print(S[6:])
print(S[:])
[2 3 4]
[0 1 2 3]
[6 7 8 9]
[0 1 2 3 4 5 6 7 8 9]
We will illustrate the multidimensional slicing in the following examples. The ranges for each dimension are separated by commas:

A = np.array([
[11,12,13,14,15],
[21,22,23,24,25],
[31,32,33,34,35],
[41,42,43,44,45],
[51,52,53,54,55]])
print(A[:3,2:])
[[13 14 15]
 [23 24 25]
 [33 34 35]]

### Arrays of Ones and of Zeros

There are two ways of initializing Arrays with Zeros or Ones. The method ones(t) takes a tuple t with the shape of the array and fills the array accordingly with ones. By default it will be filled with Ones of type float. If you need integer Ones, you have to set the optional parameter dtype to int:

import numpy as np
E = np.ones((2,3))
print(E)
F = np.ones((3,4),dtype=int)
print(F)
[[ 1.  1.  1.]
 [ 1.  1.  1.]]
[[1 1 1 1]
 [1 1 1 1]
 [1 1 1 1]]
What we have said about the method ones() is valid for the method zeros() analogously, as we can see in the following example:

Z = np.zeros((2,4))
print(Z)
[[ 0.  0.  0.  0.]
 [ 0.  0.  0.  0.]]
There is another interesting way to create an array with Ones or with Zeros, if it has to have the same shape as another existing array 'a'. Numpy supplies for this purpose the methods ones_like(a) and zeros_like(a).

x = np.array([2,5,18,14,4])
E = np.ones_like(x)
print(E)
Z = np.zeros_like(x)
print(Z)
[1 1 1 1 1]
[0 0 0 0 0]
### Other functions
* np.sum        sum the element of the array
* np.dot        matrix multiply
* np.argmax     get the index of the max element
* np.max        get max element
* np.reshape    adjust matrix dimensions
* np.shape      return the dimensions of matrix
* np.exp        calculate exp on all element
