## CSS Combinators
- Adjacent sibling combinator (+):
    - separates two selectors and matches the second element only if it immediately follows the first element, and both are children of the same parent element.
    - `former_element + target_element {...}`
- Child combinator (>):
    - is placed between two CSS selectors. It matches only those elements matched by the second selector that are the direct children of elements matched by the first.
    - `selector1 > selector2 {...}`
- Column combinator (||):
    - it is placed between two CSS selectors. It matches only those elements matched by the second selector that belong to the column elements matched by the first.
    - `selector1 > selector2 {...}`
- General sibling combinator (~):
    - separates two selectors and matches all iterations of the second element, that are following the first element (though not necessarily immediately), and are children of the same parent element.
    - `former_element ~ target_element { style properties }`


## Units
### Absolute Units
- `cm`   - centimeters
- `mm`   - millimeters
- `in`   - inches (1in = 96px = 2.54cm)
- `px` * - pixels (1px = 1/96th of 1in)
- `pt`   - points (1pt = 1/72 of 1in)
- `pc`   - picas (1pc = 12 pt)

### Absolute Units
- `em`   - Relative to the font-size of the element (2em means 2 times the size of the current font)	
- `ex`   - Relative to the x-height of the current font (rarely used)- `ch`   - Relative to width of the "0" (zero)	
- `rem`  - Relative to font-size of the root element	
- `vw`   - Relative to 1% of the width of the viewport*	
- `vh`   - Relative to 1% of the height of the viewport*	
- `vmin` - Relative to 1% of viewport's* smaller dimension	
- `vmax` - Relative to 1% of viewport's* larger dimension	
- `%`	   - Relative to the parent element