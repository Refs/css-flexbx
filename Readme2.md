 # Css flex

 1. Flex basis

 flex basis is pretty similiar to min-width , it defines a starting width of each of our elements , so instead of min-width we could write flex-basis , and all of thoese elements are going to start at the width of 200; so is going to pretty much the same and it's going to behave the same , when it comes to wrapping them 

 ```css

.flex-container {
    display: flex;
    flex-wrap: wrap;
}

.box {
    height: 100px;
    /* min-width: 150px; */
    /* flex-basis: 150px; */

}


.one {
    background: red;
    flex-grow: 1;
    flex-basis: 100px;
}

.two {
    background: green;
    flex-grow:2;
    flex-basis: 200px;
}

.three {
    background: yellow;
    flex-grow:3;
    flex-basis: 300px;
}


```

> the difference between the flex-basis and min-width: when the browser window's width is less than item box's width, the items won't continue to shrink, and the scrollbar will arise. If we want to look at all the content of the item, we have to drag the scrollbar.   But the flex-basis will continue to shrink as the browser window's width is less than flex-basis, and the scrollbar won't appear , they just going to shrink as normal flex items .


conclusion: we have already seen flex-grow, flex-shrink, flex-basis , and all this property can be conbined to a single property, that's `flex`; the first number in the `flex` is going to be flex-grow , the second flex-shrink , the third flex-basis;

```css
.flex-items {
    flex-grow: 1;
    flex-shrink: 1;
    flex-basis: 0;

    flex: 1 1 0;

    flex: 1;

    /* these three sections is euqal to eachother */
}

```

2. flex flow and Axis

the default behavior of the flex items is to stacf horizontally beside eachother in what is essentially a rope going across . But we can kind of override that default behavior by explictly saying look we want.  These items  actually to stack in a column , we can use the flex-flow 

what we want to do is just to apply the flex-flow to the flex container and that control the flow of all the elements within it or rather all the flex elements within it , the flex-flow: row; is the default behavior;

```css

.flex-container {
    display: flex;
    background: #fff;
    flex-wrap: wrap; 
    /* the flex items is going to one on top of another in a column , 
       and the will take up all the space of the column row, the reason is that the flex-items is all block elements , they're going to take up 100% width of their parent element by default .
       and the flex-basis will  no longer control the initial width of the elements, because they're not going to in a row across ;
       
       the conlusion is that when we use flex-flow: columns instead of flex-flow: row; the flex-basis won't take any effect;
    */
    flex-flow: column; 
}

.box {
    height: 100px;
    flex: 0 0 100px;
}


.one {
    background: red;
    flex-grow: 1;
    flex-basis: 100px;
}

.two {
    background: green;
    flex-grow:2;
    flex-basis: 200px;
}

.three {
    background: yellow;
    flex-grow:3;
    flex-basis: 300px;
}


```

The detail: When we use flexbox there are two axis ,there is a mian axis and cross axis , and what we do when we change the flex-flow  is just changing the direction of the axis.

so when the flex-flow is equal to row , the the main axis is going to across in a row , and `the elements always follow the main axis, they line up in the direction of the main axis`. So in this case they go cross in a row by default 

The cross axis is perpendicular to main axis . When we change the flex-flow value to equal column , what happends is the axis kind of swith around and the main axis goes down , the cross axis goes crss.

Remember that elements always follow the flow of the main axis , so they will flowing downwards in a column , that how it works.

waring: There certain properties when we use flexbox that only apply to the main axis and there are certain properties that only apply to the cross axis . Obviously depending on what we have flex-flow set to , the effects of these properties is going to seem a little different :

* justify-content : this property is only applied to the mian axis , if we use flex-flow: row; them the justify-content is going to apply horizontally in a row . If we use flex-flow: column; then the justify-content 


3. align items on the cross Axis `align-items`

we're going to learn certain properties which just affect the cross axis , one of these properties is `align-items` and does the similar thing， but going to the cross axis direction .

align-items will affect the aligning of the elements going across the cross axis instead at the main axis. So we could say something like `align-items:center` and that's going across the cross axis instead of the main axis .

We can set bith justify-content: center, align-items: center, to center the items in the flex-contianer


