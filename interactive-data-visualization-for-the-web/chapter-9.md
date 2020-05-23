# Interactive Data Visualization for the Web
# Chapter 9: Updates, Transitions, and Motion

## Easing
The quality of motion used for a transition is called easing. In animation terms, we think about elements easing into place, moving from here to there
## Different types of ease
- d3.easeCubicInOut (default) - gradual acceleration and deceleration
- d3.easeLinear
- d3.easeCircleIn
- d3.easeElasicOut
- d3.easeBounceOut

## Scalability of code
- Remember to scale attribute values dynamically to the length of the dataset

## on() 
- either at **start** or **end** of a transition
- an anonymous function
- Don't put an extra transition on the on("start", )
  - "By default, only one transition can be active on any given element at any given time. Newer transitions
interrupt and override older transitions."

- 2 types of transition
    - combo transition with on()
      - ```
        svg.selectAll("circle") 
					.data(dataset)
					.transition()
					.duration(1000)
					.on("start", function() {
						// <-- Executes at start of transition
						d3.select(this)
							.attr("fill", "magenta")
							.attr("r", area + 1);
					})
					.attr("cx", function(d) {
						return xScale(d[0]);
					})
					.attr("cy", function(d) {
						return yScale(d[1]);
					})
					.attr("r", function(d) {
						return area;
					})
					.on("end", function() {
						d3.select(this)
							.transition()
							.duration(1000)
							.attr("fill", "black")
							.attr("r", 2);
					});
         ```
    - chained transition
      - ```   
        svg.selectAll("circle")
					.data(dataset)
					.transition() // <-- Transition #1
					.duration(1000)
					.on("start", function() {
						d3.select(this)
							.attr("fill", "magenta")
							.attr("r", 7);
					})
					.attr("cx", function(d) {
						return xScale(d[0]);
					})
					.attr("cy", function(d) {
						return yScale(d[1]);
					})
					.transition() // <-- Transition #2
					.duration(1000)
					.attr("fill", "black")
					.attr("r", 2);
        ```

## Clipping Paths
- How to use a clipping path
1. Define the clipPath and give it an ID.
2. Put visual elements within the clipPath (usually just a rect, but this could be
circles or any other visual elements).
3. Add a reference to the clipPath from whatever element(s) you wish to be
masked.
## Notes
- Rounding float pixel values like 12.123 to 12, using `d3.round(true)` has a net effect similar with `shape-rendering: crispEdges`. "This is helpful for keeping visual elements lined up precisely on the pixel grid for clean, sharp edges."
- Fuzzy bars may be due to antialiasing the half-pixel values
- Warning: **Transitions** can only operate on values that already exist; if you initiate a transition on a value that doesn’t exist yet, you’ll get some
unexpected and undesirable behavior. Make sure that attributes in the post-transition is existing the in the pre-transition
- Avoid putting **magic numbers**/ constant numbers that are chosen arbitrarily all over your code. Rather, put them inside variables. 
- Code with scalability in mind.