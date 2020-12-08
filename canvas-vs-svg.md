Question: should Tableaunoir use Canvas or SVG?

|   | Canvas | SVG |
|---|--------|-----|
| Storage | Just a big 2X2 matrix :)       | Heavy to store 10000 different lines, small details    |
| Drawing | Allow for pressure change during the drawing  | Difficult for pressure change   |
| Magnets | Easy: extract a portion of the canvas    | A nightmare to implement    |
| Erasing | Very easy: draw a transparent line. Handle backgrounds       | Fake erasing by adding a new object    |
| Remove an object (eg. a line) | A bit difficult because there are no objects  | Easy  |
| Move an object (eg. a circle) | Impossible | Easy   |
| Mono user Undo/redo | Easy: store the full canvas or portion of it       | Easy: remove the last object   |
| Multi-user Undo/redo | Difficult to be properly implemented      | Easy: remove the last object   |
