## Concepts
### Main axis vs Cross axis
One of the most important concepts in flexbox boxes is the main and cross axis.
By default, the main axis is the horizontal axis (or X axis) and the cross axis, obviously, the vertical axis (or y axis).
It means that when elements are being added to a flexbox container, each element will be placed after another in the direction of the main
axis and once there is no space left, the next element is is going be placed in the next space perpendicular to the main axis, therefore
in the cross axis and start fulfilling all the spaces available in the direction of the main axis again.

It is possible to change the default axis using the property "flex-direction". The possible values are row (default),
row-reverse, column, column-reverse.

### Flex Containers
Flex containers are literally containers which will hold items. It defines the main behavior of the elements within it.
The main properties which can be defined in the containers are:

#### flex-direction
This property defines from which position and direction the elements of a container should placed.
Possible values: 
- row - from left to right, from the first to the last (1, 2, 3, 4)
- row-reverse from right to left, from the last to the first (4, 3, 2, 1)
- column - from top to bottom, from the first to the last
- column-reverse - from top to bottom, from the last to the first

#### float
Moves the flexbox container to the left or right

#### justify-content
Works a text-alignment in text editors (text align left or right). Possible values:
- flex-start: respects the initial alignment, considering the flex-direction
- flex-end: moves all the elements to the oposite side
- space-between: puts a space between all the inner elements - keeping the ones on the edge near the border (without space)
- space-around: puts the space around all the elements, so that all the elements have the same space size on both sides 
- space-evenly: puts exactly the same space separating all the elements, even the space on the edges
- center: centers the items 

#### align-items
This property defines how the items should align concerning the cross axis. It is important to notice that if the flex direction 
is the default and the height of the element is not defined, the align-items property is not likely to have much effect, since the element
is likely to be taking all the space already.
- strech (default): occupy all the cross axis space available
- flex-start: align at the top of the container
- flex-end: align at the bottom of the container
- center: in the middle of the container
- baseline: when there is items of different font sizes within the same container, this property makes the baseline of all the elements to be aligned

#### flex-wrap
By default, flexbox containers won't do much if the elements within it overflows its size - it will try to reduce the elements as much as possible
but if it reaches a point where the elements cannot be shrank anymore but the elements are still trespassing the borders, it won't do anything.
This property is meant to change this behavior.
- nowrap (default)
- wrap: makes the items flow to the next line
- wrap-reverse: pushes the newers lines (which flows) above the previous ones

#### flex-flow
flex-wrap and flex-direction are so closely related and used together (they actually set the basic behavior of the container) that this
property has been created to that is possible to define both in one definition.
flex-row: {flex-direction} {flex-wrap};
flex-row: row wrap;

#### align-content
This property only makes any difference if there is more than one row. It is like the justify-content of the cross axis - it will 
determine the behavior of the different rows and how their spacing is distributed along the cross axis.
flex-start: respects the start of the cross axis according to the flex-direction
flex-end: align the items at the end of the cross axis
space-around: the same as justify-content
space-between: the same as justify-content

### Flex Items
#### order
It is possible to change the order of the items of a container only using css (not changing the html elements).
By default all elements are set the order zero. Negative values will come first and positive values next

#### align-self
This property overrides the default behavior set by the container for the cross axis (by the align-items property) by element.
The values this property supports is the same the align-items: strech, flex-start, flex-end, center and baseline.

#### flex-grow
This property tells the flex items how they should grow in case there is space remaining. The default value is 0,
which means, they should not grow.

Defining all the elements with the same value (1 i.e), they will grow exactly the same size each of them.
In case, one or more elements should grow more than the others, then they should be set with a bigger value. In order
to define the right ration, considering the desired proportions, there is a bit of calculation to do:

Suppose a container of 800px and 4 elements of 100px each. In this case, there are 400px to be distributed among all the elements.
- Setting all of them with the same value, each of them will grow by 100px.
- Setting one of the elements with value 3 and the rest with value 1, will lead to the following calculation: divide up the available 
space by the sum of all the weights (in this case, 400/6) and add the found amount to each part. In this case, the one 
which has 3 parts will grow by 200px and the other three by aproximately 67px.

#### flex-shrink
This property is pretty much the opposite of the previous one. In case the container does not have enough space to display all
the items, it sets the rules concerning how the items should shrink. By default, this property is set to 1.
Zero mean the elements should not shrink and any value bigger than zero will cause the elements to shrink proportialnally to the defined values.
Be aware that the items will only shrink to a degree and it depends on the content and padding to not destroy the layout.

#### flex-basis
Depending on the flex-direction, width and height can have a different meaning. When using using and flex-basis, the flexbox only looks
at the flexbasis.
The default value for flex-basis is auto, which means the item is only going to take the necessary width (or height, depending on the direction) to take on the content and padding - only 
when this value is auto (or default), the regular width and height have effect.





