# Responsive Web Design

## Definition
When we speak about `Responsive Web Design`, we are focusing on three main characteristics:
1. Flexible, grid-based layout
2. Media queries (CSS3)
3. Images that resize based on screen resolution

## Floats: An Overview
`display: float` was one of the original CSS layout hacks. Floats were designed to 'float' images to the left or right and wrap text nicely around the image. 

### Avoiding Collapse: "If you float, you must clear"
When using floats to layout web pages, many problems can be avoided by remembering to "clear" the floats. In short, "clearing" floats allows for subsequent elements to move down past the float, rather than appear next to it. 

A parent element that only contains floated elements will by default "collapse" (i.e. have no height). We can fix this by clearing the float after the floated elements in the container, but before the close of the container. More info [here](https://css-tricks.com/all-about-floats/).

### Recipe: Rows and Cells
```html
<div class="row">
    <div class="col-1"></div>
    <div class="col-1"></div>
    <div class="col-1"></div>
    <div class="col-1"></div>
</div>
```

```css
/* Formula for clearing a row */
.row::after {
    content: "";
    display: table;
    clear: both;
}

.col-1 {
    float: left;
    margin-left: 4%;
    width: 20%;
}
```


## Acknowledgements
Notes are based in part off of the FrontendMasters course [CSS Grids and Flexbox for Responsive Web Design](https://frontendmasters.com/courses/css-grids-flexbox/).
