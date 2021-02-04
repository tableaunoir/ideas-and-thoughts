Question: should Tableaunoir use bitmap reprenstation or object-based? 

|   | Bitmap | object-based |
|---|--------|-----|
| Drawing | :heavy_check_mark: Allow for pressure change during the drawing. Allow for very nice effect (chalk effect at some point? brushes?)  | :x: Difficult for pressure change   |
| Magnets | :heavy_check_mark: Easy: extract a portion of the bitmap    | :x: Difficult to implement    |
| Erasing | :heavy_check_mark: Easy: draw a transparent line. Handle backgrounds       | :x: Fake erasing by adding a new object    |
| Remove an object (eg. a line) | :x: A bit difficult because there are no objects  | :heavy_check_mark: Easy  |
| Move an object (eg. a circle) | :x: Impossible | :heavy_check_mark: Easy   |
| Big blackboard | :x: Memory issues   | :heavy_check_mark: |
| Complex blackboard | :heavy_check_mark: Just a big 2X2 matrix :)       | :x: Heavy to store 100000 different lines, small details.    |
| Zooming   | :x: Pixels  | :heavy_check_mark: Always nice |
| Mono user Undo/redo | :heavy_check_mark: Easy: store the full canvas or portion of it       | :heavy_check_mark: Easy: remove the last object   |
| Multi-user Undo/redo | :x: Difficult to be properly implemented      | :heavy_check_mark: Easy: remove the last object   |

Currently it is object-based and bitmap once a state is computed, so we can get the best of the two worlds.
