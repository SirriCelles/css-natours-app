- Outline the Css colours or themes at the beginning of the theme.css/scss file
## PART ONE
#### Best way to perform basic reset using universal selector
- Use the * selector also, by default every browser sets somem margin and padding on elements.
- `box-sizing: border-box`: Change element to a box model, so that the borders and the paddings are no longer added to the total width or the total height.

#### How to set project wide definitions
- Set over all font sizes in the body element selector because the properties related to fonts are inherited. eg `everything related to fonts`
- body {
    font-family: "Lato", sans-serif;
    font-weight: 400;
    font-size: 16px;
    line-height: 1.7;
    color: #777;
    padding: 30px;
}
#### How to clip parts of an element using `clip-path`
- The clip-path CSS property creates a clipping region that sets what part of an element should be shown. Parts that are inside the region are shown, while those outside are hidden. use this tool for cliping `https://bennettfeely.com/clippy/`.

#### The easiest way to center anything with the `transform, top, and left` properties.
- eg `top: 40px`, has a counting reference from where to start which has it's position. This position is initially has to be set eg `relative`.
- For images, it is preferable to set the height of the element or image and let the browser automatically scale the width.
- Block elements occupy the entire width of the element. More importantly they create line  breaks before and after them.
- To position element use `position` and `top, left` properties.
- transform: translate(-50%, -50%); /* this propety values are nolonger in relation to the parent values, But to the element it self*/

#### How to impliment css animations with `@keyframes` and the `animation` property
- There are generally two types of animations in css. the First one is to use the `transition property` and then change the properties of the elementthat you want to animate on an event like - onhover.
- Use the keyframs-at-rule (@keyframes).
- For browser perfomance is best to only ever animate two properties `opacity` and `transform` property.
- For an animation to work, there are only two properties we have to specify called `animation-name`(name defined for the animation el moveInRight) and the `animation-duration` (duration the animation is to take in seconds eg 3s);
##### Remove shaking from the head element of an animation by setting the
`backspace-visibilty: hidden;`
for the the container element

#### What pseudo-elements and pseudo-classes are
- pseudo classes are a special state of a selector. eg `a:hover` the `hover` is state of the anchor selector.
- An inline-block element can be treated as text in terms of positioning by setting `text-align`
- The transition property has to be on the initial states.

#### How and why to use the `::after` pseudo-element
- The ::after pseudo-element acts like a virtual element riight after the element that we're selecting. You can the style that element. it is powerful to do some cool effects
- The trick is adding the element that looks exactly like the previous but placed behind the previous or original.
- For and after element to be visible you need to specify its `content` property which can be empty as well. Same thing with the `display property`

#### How to creat the creative hover animation effect using `transition` property

## Three Important, Fundamental principles to constantly keep in mind for good modern websites or web apps (The three pillars of writing good HTML and CSS).
- Responsive Design
- Maintainable and Scalable Code
- Web Performance

#### Responsive web design
- Build one website that works beautifully with all screen sizes on all devices. The fundamentals of responsive web design include
- Fluid layouts
- Media Queries
- Responsive Images
- Correct uinits
- Desktop-first vs Mobile-first

#### Maintainable and Scalable Code
- writing code that is clean, easy to understand and supports future growth and reusable.
- To archieve this, you need to care about your css architecture

#### Web Performance
- Making a web app or web site faster and to make it smaller in size.
- Make as little HTTP as possible. Include as little files as possible
- Reduce the use of images
- compress images to use less band width for the final user

#### What happens behind the scenes as we load a webpage
- When the browser starts to load the inital HTML file, it takes the loaded html and parses it(decode the code line by line). From this process it builds a DOM(Document Object Model). The DOM describes the entire web document like a family tree. As the browser parses he html, it also finds the stlye sheets included in the html head and starts loading them as well. Just like that, css is also parsed.
- During the css parsing phase there two main steps
- Firts off - Conflicting Css declarations are resovled through the `cascade` proccess.
- The Second step is to process final css values. After all this is done the final css is stored in a tree like structure called `CSS Object Model` similar to the DOM
- the parsed and stored CSS and HTML form the `Render Tree`. Inorder to render the page, the broswer uses the `Visual Formatting Model`. The algorithm calculates and uses many css features eg box-model, positioning, float.

#### CSS Parsing phase
- In the parsin phase, the first step is to resolve conflicting css declarations and the second step is to process the final css values.
- ##### Cascade
- The process of combining different style sheets and resolving conflicts between different CSS rules and declarations, when more than one rule applies to a certain element.
- In order for CSS to resolve these conflicts from different sources(Author css, User css, Browser/ user agent css) it looks at the `IMPORTANCE(WEIGHT)` > `SPECIFICITY` > `SOURCE ORDER`.
-  The cascade gives the conflicting declarations different importances based on their source ie
1 User declarations markedwith `!important`
2 Author declarations marked with `!important`
3 Author declarations
4 USer declarations
5 Default browser declarations
- Many times there a bunch of Author declaraions without the !important keyword. In this case the cascade will calculate and compare the `specificities` of the declaration selectors.

1 Inline stlyes
2 IDs
3 Classes, Pseudo-classes, attributes
4 Elements and pseudo-elements

- For the Elements with the same specificity, cascade looks a `source order`. Which means the last declaration in the code will override all other declarations and will be applied.
- NOTE: it is best to rely more on `specificity` than the order selectors; cause if you happen to rearrange your css code, you won't have any suprises which will messup your entire code.

#### How values are proccessed in the CSs parsing phase
- going look at the Most commonly used css values eb %. em, rem, px, cm, vh, vw
- font-sizes are parsed by inheritance from the parent values
- lengths values are parsed by inheritance from the width of the parent element

#### Inheritance
- A way of propergating property values from parent elements to children.
- Inheritance parses the values of some speific properties from parents to children - more maintainable code;
- Properties related to text are inherited: font-family, font-size, color etc
- The computed value of a property is what gets inherited, not the declared value.
- Inheritance of a property only works if no one declares a value for that property.
- The `inherit` keyword can be used to force inheritance on certain properties
- The `initial` keyword resets a property to its initial value.

#### How and why to use rem units in our project
- Want an easy way to chnage all the settings of our page. eg when we hit a break point on mobile device. when that happens we want a wa to decrease all the measurements on our site at the same time. instead of writing hundreds of lines of code in the media settings

#### A great workflow for coverting px to rem
- Set the root font and change all units to rem
- this size is set in the HTMl selector.
- It is advisable to set this to a value that is relative to the browser default and not manually impliedet
- Set overall font size to a percentage.

#### Website Rendering Phase `Visual Formatting Model`
- Ii is an algorithm that calculates boxes and determines the layout of these boxes, for each element in the render tree. in order to determine the final layout of the page.
- The algotakes into account factors like
`Dimensions of the boxes, which are calculated by the box model`,
`Box-type which can be inline, block or inline-block`.
`Positioning scheme: floats and positioning`
`Stacking contexts`
Other elements in the render tree;
Viewport size and dimensions of images

### The Box Model
- One of the factors that determines how elements are displayed on a web page and how they are sized.
- Each box can have `width, height, padding, margin and border` which are optional
- total width = right border + right padding + specified width + left paddind + left border
- total height = top border + top padding + specified height + bottom padding + bottom border
- The `border-box: box-sizing` - property sets a default box size including padding and and border.
- This apply to block level boxes elements

### Box Types: Inline, Block-level and inline-block
#### Block-Level boxes
- Elements formatted visually as blocks
- 100% parent's width
- Vertically, one after another
- Box-model applies as showed
- define box by a display property

#### Inline- Boxes
- Content is distributed in lines
- Occupies only content's space
- No line-breaks
- No height and widths
- Paddings and margins only horizontal(left and right).

#### Inline Block boxes
- A mix of block and inline
- Occupies only content's space
- No line breaks
- Box-model applies as showed

### Positioning Schemes: Normal flow, absolute positioning and Floats
#### Normal flow
- what happens to an element if you do not do anything to it at all - The default positioning scheme
- Not floated
- Not absolutely positioned
- Elements laid out according to their source order

#### Floats
- Element is removed from the normal flow;
- Text and inline elements will wrap around the floated element
- The container will not adjust its height to the element.
-`float: left`, `float: right`.
- when using float , add the `clearfix` class ie. .clearfix::after {
    content: "";
    clear: both;
    display: table;
}
#### Absolute Positioning
- Just like with float, when you set the position to `absolute`, the Element is removed from the normal flow
- No impact on surrounding content or elements;
- We use `top, bottom, left` and `right` to offset the element from its relatively positioned container

#### Stacking Contexts
- Stacking contexts are what determines in which order elements are rendered on the page.
- layers to form a stack.
- Each element uses the `z-index` property or `absolutely positioned` elements
- an opacity value different from 1, a transform, filter or other properties will also create new stacking context even with the z-index, the stacking order doesn't work as expected.
-

### CSS Architechture
- we aim to write clean, modular, reusable and ready for growth code.
- THE THINK - BUILD - ARCHITECT MINDSEt
#### THINK
- Think about the layout of your webpage or web app before writing code
##### COMPONENT DRIVEN DESIGN
- `Modular building` block that make up interfaces. We can think our interfaces as a `collection of components` held together by the `layout of the page`.
- Re-usable accross the project and accross different projects.
- Components should be `Independent`, allowing us to use them anywhere on the page. ie should not depend on their parent elements.

#### BUILD
- Build your layout in HTML and css with a consistent structure for naming classes.
##### BEM
- `Block Element Modifier`. It is nice clean system for marking up our layouts. class names look like this
-  BLOCK `.block {}`- stand alone component that is meaningfull on it's own and can be reused.
- ELEMENT `.block__element {}`, part of a block that has no meaning on its own. provides low specificity.
-  MODIFIER:`.block__element--modifier {}` a different version of a block or na element. flag that can be put on block or element to make a diff version
- ei `.recipe` `.reciper__hero`, `.recipe__stats-box`, `.recipe__stat-name`
-
#### ARCHITECT
- Create a logical architecture for your CSS with files and folders. there are diff options here but the common and simple one is
##### THE 7-1 PATTERN
- 7 different folders for partial Sass files, and 1 main Sass file to import all other files into a compiled CSS stylesheet.
base/ - put basic definitions
components/ - One file for each component
layout/ - Define the  overall layout of the project
pages/ - styles for specific pages of the project
themes/ - If you want to implement different visual themes
abstracts/ - code that  doesn't output any css
vendors/ - all third party css goes

## SASS
#### What is SASS and How does it work?
- Sass is a CSS preprocessor, an extension of CSS that adds power and elegance to the basic language
- SASS code > compiled to > (sass compiler) >> complied CSS code.
- CSS gets very messy very quickly, we use SASS to fix these problems.
- SASS provides a couple of handy features and tools css doesnot have

#### MAIN SASS Features
- VARIABLES: for reusable values such as colors, font-sizes, spacing etc
- NESTING: To nest selectors inside one another to allow us write less code.
- OPERATORS: For mathematical operations right inside CSS.
- PARTIALS AND IMPORTS: Most important and most useful features of Sass. to write CSS in different files and importing them all into one single file;
- MIXINS: to write usuable pieces of css code
- FUNCTIONS: similar to mixins, with the differnce that they produce a value that can be used.
- EXTENDS: Can be used to make different selectors inherit declarations that are common to all of them.
- CONTROL DIRECTIVES: For writing complex code using conditionals and loops.

### Installing Sass
- npm init
- npm install node-sass --save-dev
- compile node-sass by writing an npm script

#### 7-1 Pattern.
- Partial files always start with an import
- This architecture is designed to handle large multi-page websites or web apps.
-
### Basics of Responsive Design
####  FLUID GRIDS AND LAYOUTS
- To allow content to easily adapt to the current viewport width used to browse the website. Uses % rather than px for all layout-related lengths.
- There are currently three major ways of laying out a web page or app.
- Apart from float layouts modern alternatives include flex box and css grid
- FLEX BOX offers an amazing way of laying out elements in a one dimensional row,
- Css grid is perfect for creating the overall layout of a page. with two dimensional grids.

##### How to architect and build a simple grid system;
- A grid is a design system which allows us to build consistent interfaces. Allows us to devide our available space is a specified number of parts.
##### How Attribute selector works
##### How the `:not` pseudo-class works
##### How `calc()` works and whats the differences between `calc()` and simple Sass operations


#### FLEXIBLE/RESPONSIVE IMAGES
- Images behave differentl than text-content, and so we need to ensure that they also adapt nicely to the current viewport.
- This is done by defining their dimensions in % rather than fixed values
- make up the biggest part of the site in terms of size so, we shold optimize the images for different width.

#### MEDIA QUERIES
- allows us to change styles on certain viewport widths(break points) allowing us to create different version of ou website fo our website for different widths

- ##### LEARNING
- Thinking about components
- How and why to use utility classes
- How to use `backgroud-clip` property
- How to `transform` multiple properties at the same time
- How to use `outline-offset` property together with outline
- How to style elements that are not hovered while others are.
-

- Utility classes in css are very simple css classes with just one goal

- How to build an amazing rotating card effect
- How to use `perspective` in css
- How to use `backface-visibility` property
- Using background blend model
- How and when to use `box-decoration-break`

## USEFUL LINKS
- `unsplash.com`
