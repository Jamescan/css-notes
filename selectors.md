# Selectors

## Introduction and Prerequisites
Selectors allow CSS to efficiently target sets of elements on the page, as opposed to tediously applying inline styles everywhere, e.g. 
```css
<h2 style="color: gray;">Some Heading</h2>
```

### Terminology: Rules, Selectors, Declarations.
A **rule** in CSS consists of a declaration block (the area surrounded by curly braces). The **declaration block** consists of one or more declarations. Each **declaration** has the format: `propertyName: propertyValue;`, with no regard to whitespace.

Full example:

```css
/* start of rule */
h1 /* the selector */
/* start of declaration block */
{
    /* start of first declaration */
    color: purple;
    /* end of first declaration */

    /* start of second declaration */
    background-color: black;
    /* end of second declaration */
}
/* end of declaration block */
/* end of rule */
```
## Types of Selectors

There are several different types of selectors and their names come from what *things* they select on the page.

### Element Selectors
Element selectors target elements on a page. Most commonly these will be HTML elements, e.g. `<html>`, `<h1>`, etc. But they can also target custom-defined elements in an XML document. 

#### Example
```css
/* Apply white font-color to all paragraph text in the document */
p {color: white;}
```




## Acknowledgements

Notes adapted from *CSS: The Definitive Guide (4th Edition)* by Meyer & Weyl.