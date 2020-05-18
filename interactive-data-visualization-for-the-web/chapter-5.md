# Interactive Data Visualization for the Web
# Chapter 5: Data

Data must be bound to elements within the page

python3 -m http.server 8888 &.

python -m SimpleHTTPServer 8888 &.

## Chaining Methods
    - handoff
      - order matters
      - output of the previous chain link must match the input of the next chain link

## Bind data
- Data visualization is a process of mapping data to visuals
- ```
  d3.select("body").selectAll("p")
    .data(dataset)
    .enter()
    .append("p")
    .text(function(d) { return d; });
  ```
- When you chain methods together, anytime after you
call data(), you can create an **anonymous function** that accepts d as input.

## Loading data
  1. d3.csv("food.csv", rowConverter).then(function(data){
        console.log(data);
    });
  2. d3.tsv() - for tab-separated data
  3. d3.json()

# Recommended Tool
- [Mr. Data Converter](https://shancarter.github.io/mr-data-converter/) - converts excel, csv, etc to json or other formats

## Sample template when loading data
```
  var dataset;
  d3.csv("food.csv", function(error, data) {
    if (error) { //If error is not null, something went wrong.
      console.log(error); //Log the error.
    } else { //If no error, the file loaded correctly. Yay!
      console.log(data); //Log the data.
    //Include other code to execute after successful file load here
    dataset = data;
    generateVis();
    hideLoadingMsg();
    }
  });
```
