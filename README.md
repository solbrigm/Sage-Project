Sage-Project
============

Project to test github and sage

function cut_square takes as arguments slope (number >= 0), area (0< number <1), and color. Returns a polygon with 
of the given color that would result from cutting a 1x1 square by a line with given slope such that the part 
remaining in upper left corner has the given area. 

Exapmle 1

sage: cut_square(1,1/2)

#returns purple triangle, vertices [(0,1),(1,1),(0,0)]

Example 2:

sage: slope = 2
sage: n = 15
sage: G = Graphics()
sage: for i in range(0,n):
sage:     G += cut_square(slope,1-i/n, Color((0,1-i/n,0)))
sage:     
sage: G

#divides a square into 15 equal sized portions, with different colors of green

Example 3:

@interact
def _(slope=(0.5..10)):
    n = 15
    G = Graphics()
    for i in range(0,n):
        G += cut_square(slope,1-i/n, Color((0,1-i/n,0)))
    show(G, figsize= [3,3])

#Interactive divided square, can change the slope of the divisions
