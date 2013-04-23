Sage-Project
============

Project to test github and sage

contains two functions, cut_square_python and cut_square_cython. The first uses only Python code, the second uses Cython.

Both takes as arguments slope (number >= 0) and an area (0< number <1). Returns an array of corners
for the polygot that would result from cutting a 1x1 square by a line with given slope such that the part 
remaining in upper left corner has the given area. 



# Example:

sage: slope = 2
sage: n = 15
sage: G = Graphics()
sage: for i in range(0,n):
sage:     G += polygon(cut_square_python(slope,1-i/n),color = Color((0,1-i/n,0)))
sage:     
sage: show(G, figsize= [3,3])

# Timeit Examples:

timeit("cut_square_cython(2,.1)")     625 loops, best of 3: 4.49 µs per loop

timeit("cut_square_python(2,.1)")     625 loops, best of 3: 23.5 µs per loop

Improvement: cython takes about 1/5 the time.

(Similar numbers achieved for various values of slope and area)
