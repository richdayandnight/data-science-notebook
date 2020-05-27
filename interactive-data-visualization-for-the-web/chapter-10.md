# Interactive Data Visualization for the Web
# Chapter 10: Interactivity

## 2 step process in making visualization interactive
1. Binding event listeners
2. Defining the behavior
   
## Hover
- With CSS
  - ```
	rect:hover {
                fill: orange;
                -moz-transition: all 0.25s;
                -o-transition: all 0.25s;
                -webkit-transition: all 0.25s;
                transition: all 0.25s;
            }	
    ```

## Events on Overlapping elements
- A mouse event will only be triggered by the topmost/frontmost element.
- Use `pointer-events: none;` in css or
```
svg.append("text")
… //other stuff here
.style("pointer-events", "none");
```
for mouse event to ignore the frontmost element.  

## Named transition
- Name transitions can operate concurrently and dont conflict with each other. (assuming they’re not trying to modify the
same attributes) (Check chapter10-project/3_sort_bar_with_gradient_restore_bar_color for reference)

## Object Constancy
```
Animated transitions are pretty, but they also serve a purpose: they make it easier to follow the data. This is known as object constancy: a graphical element that represents a particular data point (such as Ohio) can be tracked visually through the transition. This lessens the cognitive burden by using preattentive processing of motion rather than sequential scanning of labels.
```
[Mike Bostock](https://bost.ocks.org/mike/constancy/)

## Tooltips
1. Default Browser Tooltips
2. SVG tooltip
3. HTML div tooltip
   
## Notes
- Useful event compatibility table for [browsers](https://www.quirksmode.org/dom/events/)
- "It can help to put both the tooltip and SVG chart within the same enclosing element
(like a container div), so then you only have to worry about relative positions." p.214 
- Use `d3.mouse` to get mouse coordinates relative to any other element on the page.
- "The issue of accessibility to visualizations on any sort of device is a huge, mostly unsolved problem."