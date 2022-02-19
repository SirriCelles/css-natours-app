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

#### A great workflow for coverting px to rem