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