# Knight2Move
Knight2Move is a game where a player can see all the moves a knight can make on a chessboard in exactly 2 turns!

![enter image description here](https://yarden-landscape.s3-us-west-2.amazonaws.com/example.png)


## Installation
```python
### top-level directory

    .
    ├── api                   # API routes
    ├── client                # Client source files
    ├── middleware            # Application middleware
    ├── models                # Database models 
    ├── services              # Functional services 
    ├── CONTRIBUTING.md      
    ├── README.md             
    └── server.js             # Server config
```

Start by cloning a local copy of the project to your Desktop. After that, change directories into the root project folder and install the server-side node modules.

```bash
cd knight2move && npm install
```
```bash
npm start
```
Next, in your terminal open a new tab (cmd + t) to install the client-side node modules.
```bash
cd client && npm install
```
```bash
npm start
```
From here, navigate to http://localhost:3000/ to see the app in the browser.

## Usage
To calculate the possible moves of a knight, here is breakdown of the algorithm: First, it will find all possible X and Y positions. Next, it will iterate through each possible combination of X and Y and if it finds a valid pair, it will add that to the collection of data to be returned. 

```
function calculateNextMoves(cell) {
    var possibleCoordinates = [];
    var xCoordinates = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h'];
    var cellX = xCoordinates.indexOf(cell[0]) + 1; 
    var cellY = parseInt(cell[1]); 
    
    //Find all possible X Positions
    var cellXpositions = [cellX + 2, cellX - 2, cellX + 1, cellX - 1].filter(function(cellPosition) {
        return (cellPosition > 0 && cellPosition < 9);
    })
    
    //Find all possible Y Positions
    var cellYpositions = [cellY + 2, cellY - 2, cellY + 1, cellY - 1].filter(function(cellPosition) {
        return (cellPosition > 0 && cellPosition < 9);
    })
    
    //We now have 2 seperate arrays: One for X Positions, One for Y Positions.
    //Go thru every combination possible and if it is a valid position then push it
    //to the possible coordinates array - if not present already.
    //The trick is to validate the position pair (X, Y) by making sure that 
    //the net X distance plus net Y distance is 3
    for (var i = 0; i < cellXpositions.length; i++) {
        for (var j = 0; j < cellYpositions.length; j++) {
            if (Math.abs(cellX - cellXpositions[i]) + Math.abs(cellY - cellYpositions[j]) === 3) {
                if (!possibleCoordinates.includes([cellXpositions[i], cellYpositions[j]])) {
                    possibleCoordinates.push([cellXpositions[i], cellYpositions[j]]);
                } 
            }
        }
    }

    return possibleCoordinates;
}
```

## Contributing
Pull requests are welcome. See [CONTRIBUTING.md](https://github.com/isaacg11/k2mTest/blob/master/CONTRIBUTING.md) for more info.

## License
[MIT](https://choosealicense.com/licenses/mit/)