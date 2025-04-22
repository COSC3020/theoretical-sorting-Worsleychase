# Theoretical Sorting

A Computer Science researcher claims to have come up with a sorting algorithm
that can sort arbitrary elements in $O(n)$ time based on comparisons of two
elements at a time. This would be asymptotically faster than any known general
sorting algorithm. The algorithm itself is proprietary and will be sold by a
company.

How would you verify this claim? You may assume that you have access to a
black-box implementation of the sorting algorithm, i.e. you cannot examine the
source code, but you can use it to sort any list you like. Explain in detail
your method for investigating whether X is correct, including any expected
results you would get.

Also give a theoretical argument for why X could or could not be correct, based
on the complexity of the general sorting problem we covered in class.

Add your answers to this markdown file.

# Solution

## Theoretical

A sorting algorithm that uses comparsions can not be faster than the lower bound $\Omega(n \cdot \log(n))$. This is derived from the decision tree model where each comparison is effectively a binary decision and the height of the tree is at least $\log(n!)$; which is $\Theta(n\cdot \log(n))$. This means that the algorithm doesn't actually compare anything, but may use data-set specific methods.

## Practical

Now that we know it must be a dataset specific method, we can test lots of different inputs. Below is a list of inputs I would want to try:

- Random
- Constant (all elements the same value)
- Sorted
- Reverse Sorted
- Duplicates
- Only even numbers
- Only odd numbers
- Extremely small set of random data
- Extremely, extremely large set of random data
- Perform sort for random arrays of size 1 to size $10^8$, incrementing the size by 1. (Realistically could increment by much larger amount)

These tests should at least identify the datasets that this algorithm doesn't actually achieve O(n) with. With the data from the last input(s), you could plot the time taken as a function of array size (n) to see if it actually behaves linearly. I would also like to test this algorithm against known algorithms like mergesort, quicksort, heapsort, etc. with the same datasets.

I would expect to see this algorithm fail in its claim of O(n) complexity unless fed an extremely specific dataset that the algorithm is made for. If it did perform with O(n) with these datasets one would have to find which datasets it performed the worst with and exploit any holes in the algorithm.

# Disclaimer

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.
