# Selectors <!-- omit in TOC -->

- [Introduction and Prerequisites](#Introduction-and-Prerequisites)
  - [Terminology: Rules, Selectors, Declarations.](#Terminology-Rules-Selectors-Declarations)
- [Types of Selectors](#Types-of-Selectors)
  - [Element Selectors](#Element-Selectors)
    - [Example](#Example)
  - [The Universal Selector: `*`](#The-Universal-Selector-)
    - [Example](#Example-1)
  - [Grouped Selectors: `,`](#Grouped-Selectors-)
    - [Example](#Example-2)
  - [Class (.) and ID (#) Selectors](#Class--and-ID--Selectors)
    - [Example - Basic Class and ID Selector](#Example---Basic-Class-and-ID-Selector)
    - [Example - Combining Element and Class Selectors](#Example---Combining-Element-and-Class-Selectors)
    - [Example - Selecting Elements with Multiple Class Names](#Example---Selecting-Elements-with-Multiple-Class-Names)
  - [Attribute Selectors: []](#Attribute-Selectors-)
    - [Simple Attribute Selectors](#Simple-Attribute-Selectors)
    - [Exact Attribute Value Selectors](#Exact-Attribute-Value-Selectors)
    - [Partial Attribute Value Selectors](#Partial-Attribute-Value-Selectors)
- [Acknowledgements](#Acknowledgements)

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

### The Universal Selector: `*`
Introduced in CSS2, the universal selector matches any and all elements of the document. It has specificity `0-0-0` and may cause unintended consequences.

#### Example
```css
/* Apply red font-color to all elements in the document */
* {color: red;}
```

### Grouped Selectors: `,`
While not a type *per se*, all selectors may be grouped together into one rule to keep stylesheets short and maintainable. Separating selectors with a comma groups them together, and applies all declarations to each.

#### Example
The following are logically equivalent:
```css
/* Ungrouped version */
h2 {color: red;}
h3 {color: red;}

/* Grouped version */
h2, h3 {color: red}
```

### Class (.) and ID (#) Selectors
Class Selectors associate styles with elements that are assigned a specific `class` attribute. This allows styling of content independent of element type. To define rules for class selectors, put a period before the class name in the stylesheet.

Recall that elements can have multiple class attributes. Chaining two class selectors together will match elements with both class names, regardless of their order. 

ID selectors are similar to class selectors - they match elements containing a specific `id` attribute. (Recall that in any given document `id` attributes *should* be unique to one element.) Some differences though are:
* A selector can't match multiple IDs, because any HTML element can have one and only one ID (i.e. `<p id="foo bar"><p>` is not valid)
* ID selectors have greater specificity than class selectors

#### Example - Basic Class and ID Selector
```css
.specialText {color: red}
#uniqueText {color: blue}
```

```html
<p id="uniqueText">This text is colored blue</p>
<span class="specialText">This text is colored red</span>
<p>This text is not styled with the above rules</p> 
```

#### Example - Combining Element and Class Selectors
```css
p.specialText {color: red}
```

```html
<p class="specialText">This text is colored red</p>
<span class="specialText">This text is _still_ not colored red</span> 
```

#### Example - Selecting Elements with Multiple Class Names
```css
.specialText.warning {color: red}
```

```html
<p class="specialText warning">This text is colored red</p>
<p class="warning specialText anotherClass">Also red!</p>
<span class="specialText">This text is not colored red</span> 
```

### Attribute Selectors: []
Attribute Selectors allow us to style elements based on attributes (and potentially their value) other than `class` and `id`, which we've already covered. There are four main types.

Attribue selectors are especially useful in XML documents, but use-cases exist in HTML documents too.

#### Simple Attribute Selectors
Simple attribute selectors allow us to select elements that have a certain attribute, regardless of its value. The selector is formed by the element name and the name of the attribute surrounded by square brackets. Multiple attributes may be included in the selector.

```css
a[href][title] {color: brown}
```

```html
<a>Not colored brown</a>
<a href="http://www.google.com">Not brown</a>
<a href="foo" title="title1">Brown!</a>
<a href="bar" title="title2">Also brown!</a> 
```

#### Exact Attribute Value Selectors
Exact Attribute Selectors allow us to select elements containing an attribute of a certain value. They may be chained as well!

```css
a[href="foo.org"][title="someTitle"] {color: brown}
```

```html
<a>Not colored brown</a>
<a href="http://www.google.com">Not brown</a>
<a href="foo.org" title="someTitle">Brown!</a>
```

#### Partial Attribute Value Selectors




## Acknowledgements

Notes adapted from *CSS: The Definitive Guide (4th Edition)* by Meyer & Weyl.