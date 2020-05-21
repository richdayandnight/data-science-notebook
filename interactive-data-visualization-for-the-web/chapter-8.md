# Interactive Data Visualization for the Web
# Chapter 8: Axes

# Axes
- are actually functions whose parameters you define
- when an axis function is called, visual elements of the axis are generated
- scale is a requirement for creating an axis
# 4 different function constructors
- Horizontal:   
- 1. d3.axisTop();
  - 2. d3.axisBottom();
- Vertical:
  - 1. d3.axisLeft();
  - 2. d3.axisRight();


# Tips
- Take note of SVG attribute names in styling your SVG elements using CSS (ex. stroke, fill, and shape-rendering). Using attribute names that are not SVG specific might result into overriding css styles of other html elements.
- To specify Tick Values Manually: call `tickValues()` >> This overrides D3’s default tick-selection logic.
- Use `d3.format()` to format labels