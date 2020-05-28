# Interactive Data Visualization for the Web
# Chapter 11: Using Paths

## Visual rhetoric
design decisions that express a point of view by influencing how others interpret our chart

## Extra notes:
```
var rowConverter = function(d) {
    return {
    //Make a new Date object for each year + month
    date: new Date(+d.year, (+d.month - 1)),
    //Convert from string to float
    average: parseFloat(d.average)
    };
}
```
- **+** operator forced `d.year` and `d.month` to be typed as numbers and not string
- Javascript's month starts from 0. 
