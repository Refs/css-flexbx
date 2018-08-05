# css-flexbx

## Flexbox basics

1. How flex box works 

* first we have to create a container , an element with a display type of flex , so that every direct descendent element within it wil become a flex item. 
* once we do above we can then control the behavior of those flex items using several flexbox css properties applied to the items themselves or the container .
* The behavior includes things like how they grow with the container ,or how they shrink(缩) relative to each other or whether they stack on top of other or side by side . So a lot of things we can do with them 

2. the default behavior of flex item , the stack left to right in a row  ，like float every item then overflow the contianer;

3. Once we make this container we put elements within it then we can control the flexibility, if you like or the functionality of these items things like the spacing , the growth , the shrinking , how they stack. 

2. flex-grow

what we want do is when there's available room left in the container , I want each of these elements to grow into that available room , we do that by using the flex-grow property 

```css
.box {
    height: 100px;
    min-width: 150px;
    
    /* flex-grow: 1; */
    /* what's happening is each one of these elements is growing at rate of 1 and all items grow and get the same rate to take up all the available room in the container  */

    /* flex-grow: 100; */
    /* it will do the same thing like above, the reason is because it's kind of like a growth rate, and right now we're giving all the boxes the same groth rate so they're all growing to the same dimensions */

}

/* however the flex-grow value can make a lot more sense when we set it to a different one on each of flex items , so let's remove the flex-grow in the .box class. and add it ti each one of flex item individually , and give them different flex grow rate */

.one {
    background: red;
    /* 1. we just give the one a flex-grow*/
    /* the two and the three will still remaining 100px in width , because that's a minimum width , but the one is currently growing and it taken up all the extra room */
    /* so utilize this we can control the two and three width constantly, and the one will respectively with the window */ 
    flex-grow: 1;
}

.two {
    background: green;
    /* 2. we set one grow 1. and two grow 2 */
    /* one and two will grow until they take up all the room of the flex container, but two grow twice as much as  one */
    flex-grow:2;
}

.three {
    background: yellow;
    flex-grow:3;
}


```
> warning: note that the width of each item is min-width, so `every item starts with width zero`; so if every item's width flnally bigger than min-width, the two should twice as much as one ind dimension;

we can think of these growth rates a bit columns on a grid. to image bootstrap grid and it has 12 columns , so we've got 12 columns to play with . We could use this flex-grow property , as a way of defining how many columns we want an element to take up , so we've got 12 to play with in total ;

Above is how flex-grow works , we use it to expand elements into available space and the rate at which it expands into that available space is governed by the flex-grow value , so it's all relative to other elements next to it ;

3. flex item's order

> we can use the order of the flex item style property ; 

That is really cool , because we've not had to change the source order at all 。 in the source that html file,  everything is still in the same order, but just  in the css with one property , we've changed the order of how the items like what we want 