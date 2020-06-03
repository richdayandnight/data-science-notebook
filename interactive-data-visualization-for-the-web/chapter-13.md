# Interactive Data Visualization for the Web
# Chapter 13: Layouts

## Layouts
- remaps data to another form of data that is fit to the visual chart you want to display

## List of D3 Layouts
1. Chord
2. Cluster
3. **Force**
4. Pack
5. Partition
6. **Pie**
7. **Stack**
8. Tree
9. TreeMap

## Pie Layout
- used to create donut or pie chart
- automatically sorts data

## Stack layout
- converts two-dimensional data into “stacked” data; it calculates a baseline value for each datum, so you can “stack” layers of data on top of one another
- Given dataset:
```
var dataset = [
				{ apples: 5, oranges: 10, grapes: 22 },
				{ apples: 4, oranges: 12, grapes: 28 }]
```
- Setup stack like this:
```
//Set up stack method
var stack = d3.stack()
              .keys([ "apples", "oranges", "grapes" ]);
```

- To get result:
```
//Data, stacked (categorizes apples, oranges, and grapes -> becomes array with 3 arrays)
// The first value in each two-value array of the series is the baseline value, 
// and the second is the “topline” value—the sum of all the preceding values.
var series = stack(dataset);
```
- Resulting DOM of a stacked bar chart is
  - 3 `g` groups filled with same color but with different x, and y according to the `series`' baseline and topline

- series will be stacked in the order specified in **keys**
- To change order:
```
var stack = d3.stack()
  .keys([ "apples", "oranges", "grapes" ])
  .order(d3.stackOrderDescending); // <-- New order!
```
- Order types
  - d3.stackOrderNone - default
  - d3.stackOrderReverse
  - d3.stackOrderAscending
  - d3.stackOrderDescending

## Force Layout
- they use simulations of physical forces to arrange elements on the screen