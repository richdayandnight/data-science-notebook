# Interactive Data Visualization for the Web
# Chapter 3
My personal notes from the book :)

## DOM
    - rendering - process by which browsers, after parsing the HTML and generating the DOM,, apply visual rules to the DOM contents
## CSS (Cascading Style Sheets)
  selector {
        property: value;
        property: value;
    }

## JavaScript Gotchas
1. Dynamic Typing
   - loosely typed language
   - var foo = 25;
   - typof foo; // Returns "number"
2. Variable Hoisting
3. Function-level scope
   - variables are scoped at the function level
4. Global namespace


## SVG (Scalable Vector Graphics)
- Simple shapes
  - rect
  - circle
  - ellipse
  - line
  - text
  - path

- Styling SVG Elements
  - fill
  - stroke
  - stroke-width
  - opacity (transparent to opaque)
  - font-family
  - font-size


## Extra note on Compatibility
- Use **Modernizr** or a similar JavaScript tool to detect whether or not the browser supports SVG.
  -  If it does, then you can load your D3 code and proceed
as normal. 
    - If SVG is not supported, then you can display a static, noninteractive version of your visualization alongside a message explaining that a current browser is needed.