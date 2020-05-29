# Interactive Data Visualization for the Web
# Chapter 12: Selections

## Selections
- are a subclass of array
- inherits array methods such as `array.forEach` (`selection.each` in d3) and `array.map`
- immutable
- has methods like: `selection.each`, `selection.filter`, and `selection.sort`

## Indentation convention on selection
To minimize this confusion, Mike Bostock recommends using an indentation convention of four spaces when the selection is unchanged, but only two when a new selection is returned. Here is an example from Mike, taken from the d3-selection documentation:
```
d3.select("body")
  .append("svg")
    .attr("width", 960)
    .attr("height", 500)
  .append("g")
    .attr("transform", "translate(20,20)")
  .append("rect")
    .attr("width", 920)
    .attr("height", 460);
```
## Arbitrary anonymous function in a selection
```
selection.each(function(d, i) {
    //The 'this' context is now set to
    //the element on which you’re acting.
    //
    //Do something with 'this', d, and/or i here.
});
```

## Notes
- to create a color scale in d3 v5
`var color = d3.scaleOrdinal(d3.schemeCategory10);`
`color(arbitraryColorIndex)`
  