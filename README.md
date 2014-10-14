Game of Life API
=================================

## Application
This application provides an API which given a current generation of cells, will compute the next generation, based on the following set of rules:

1. If a cell has less than two alive neighbours, it will die.
2. If a cell has exactly two alive neighbours, it stays in the same state.
3. If a cell has three alive neighbours, it will be alive.
4. If a cell has more than three alive neighbours, it will die.

## Algorithm Implementation
Cells on a board are usually laid out sparsely, so to compute the number of neighbours for each cell means there would be a lot of unnecessary checking.
This version of the algorithm only computes the neighbours of all the currently alive cells and the cells surrounding those alive cells. For example, given the following board:<br/>

    - - - - -
    - - 1 - -
    - - 1 - - 
    - - 1 - -
    - - - - -

the direct neighbours of these cells would also have the above rules applied to them (marked with 'x'):

    - x x x -
    - x 1 x -
    - x 1 x -
    - x 1 x -
    - x x x -


## To run the application

1. Run the activator shell script - you will need to make it executable, so run: `chmod +x activator`
3. Execute: `activator run`
4. Activator should now download all the required dependencies and start the application when it's done.

To use the API:
[http://localhost:9000/next-generation?N=5&M=5&liveCells=2,1&liveCells=2,2&liveCells=2,3]

where N is the width and M is the height and each alive cell is passed as an individual x,y coordinate.

## A deployed version

The application has been deployed to Heroku, and can be accessed at the following url:

[http://enigmatic-scrubland-2726.herokuapp.com/next-generation?N=5&M=5&liveCells=2,1&liveCells=2,2&liveCells=2,3]
