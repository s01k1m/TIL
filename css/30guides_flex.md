
# TIL 10-03-2023
# 🚀 What I Will Learn
#FlexboxAxes#flex

<br>
flex 부시기

---

# 💛💛💛💛💛 flex 💛💛💛💛💛


<br><br>
1. float is old, flexbox is new. flexbox is more easier and better! 💛

2. flex container & flex items 💛
	1. in order to get Flexbox to work, you need to set up the Parent-Child relathionship. The parent is the flex container, and everything within it is the children or flex items.

3. Immediate child Only! 💛
	1. one very important thing i want to point out is that the flex container only wraps around its ***immediate children***. So there is NOT a grandchildren or grand-grandchildren relationship.

4.  Flexbox Axes 💛
	1. Flexbox operates in a 2 axes system: a main and a cross axis.

5.  Flexbox Module ( anatomy of Flexbox) 💛
	1. if it's on the main axis, the startin position is called main start and if the ending position is called main end. The same concept applies to the cross axis. Knowing your start and end is important because you can control where your flex items are placed.

6. Parent Properties 💛
	1.  To start this Flexbox party, we need to first create our flex container. There are 2 types of flex container. flex will create a block level flex container, and inline-flex will create an inline level flex container. More on block and inline in the next post.

7. Display 💛
   1. To start this Flexbox party, we need to first create our flex container. This is done by applying flex to the display property on the parent element. Now all its immediate children will become flex items.
```css
.parent {
  display: flex /* default */
        or inline-flex
}
```

8. block vs inline 💛

9. flex-direction 💛
   1.  this is the property that allows us to define our main axis.
```css
   .parent {
  flex-direction: row /* default */
               or row-reverse
               or column
               or column-reverse
}
```

10.  flex-wrap 💛
    1.  By default, flex items will try to shrink itself to fit onto one line, in other words, no wrap.
    2.  However if you wnat the flex items to maintain its size and have the overflow spread on multiple lines in the containers, then you can turn on wrap.
    3.  This property is what will allow flex items in your container to occupy more than one line.
```css
.parent {
  flex-flow: row nowrap /* default */
          or <flex-direction> <flex-wrap>
          or <flex-direction>
          or <flex-wrap>
}
```

11. flex-flow 💛
    1.  `flex-flow` is just a shorthand for `flex-direction` and `flex-wrap`
    2.  you can set both properties at the same time. Or you can ust pass one of them.
    3.  The default value is row & nowrap.
```css
.parent {
  flex-flow: row nowrap /* default */
          or <flex-direction> <flex-wrap>
          or <flex-direction>
          or <flex-wrap>
}
```

12. justfy-content[row] 💛
    1.  This is the property that sets alignment along the main axis. In this example, the main axis lies horizontally.
```css
.parent {
  justify-content: flex-start /* default */
                or flex-end
                or center
                or space-around
                or space-between
                or space-evenly
}
```

13. justify-content [column] 💛
    1.  The main axis can also lie vertically. In that case, flex-direction is set to column.

```css
.parent {
  flex-direction: column;

  justify-content: flex-start /* default */
                or flex-end
                or center
                or space-around
                or space-between
                or space-evenly
}

```

14. space-around vs space-evenly 💛
    1.  In space-evenly, the empty space in between the flex items is always equal.
    2.  However, in space-around, only the inner items will have equal spacing in between each other. The first and last item will only be allocated half the spacing. So Giving the visual appearance of its being more spread out.

15. align-items[row] 💛
    1.  So justify-content controls how items are laid out on the main axis. What about their layout in the cross axis? that's where `align-items` come into play.
    2.  Remeber the cross axis is always perpendicular to the main axis. So if the main axis is sitting horizontally, where flex-direction is row.
```css
.parent {
  align-items: stretch /* default */
            or flex-start
            or flex-end
            or center
            or baseline
}

```

16. baseline 💛
    1.  Baseline has to do with typography or text. It is the imaginary line where the text sits.

17. align-items[column] 💛
```css
.parent {
  flex-direction: column;

  align-items: stretch /* default */
            or flex-start
            or flex-end
            or center
            or baseline
}
```

18. align-content 💛
    1.  Remember we had flex-wrap where we allow flex items to wrap on separate lines
```css
.parent {
  align-content: stretch /* default */
              or flex-start
              or flex-end
              or center
              or space-between
              or space-around
}
 
```

19. Child Properties 💛
    1. We made it through the parent properties.
    2. now, we gonna learn about the Child properties

20. order 💛
    1.  By, default, flex items are displayed in the same order they appear in your code. But what if you want to change that? Use the order property to change the ordering of your items.

```css
.child{
  order: 0 /* default */
    or <number>
}
```

21. flex-grow 💛
    1.  This is where Flexbox shines. The flex-grow property allows our flex item to grow if necessary. So if there is extra free space n my container, I can tell a particular item to fill it up based on some proportion. Now with this `flex-grow` property, it's like it has its own brain and it will adjust its size depending on the container.
```css

.child {
  flex-grow: 0 /* default */
          or <number>
}
 
```
22. flex-grow calculation 💛
    1. [flex-grow calculation]

23. flex-shrink 💛
    1.  So flex-grow will expand to fill the extra space if there are any. The opposite of that is flex-shrink. What happens when you run out of space. This is the property that controls how much your flex items will shrink to fit. Note the larger the number, the more it will shrink.

24. flex-shrink calculation 💛
    1.  [flex-shrink calculation]

25. flex-basis 💛
    1.  with the flex-basis property, this is where we set its initial size. You can think of this property as the width of our flex items.
    2.  the difference between width and flex-basis.
        1.  so your browser will always tro to find the flex-basis valuse as the size indicator. And if it can't find it, then it has no choice but to go with your width property. Don't make the browser do extra work.
```css
.child {
  flex-basis: auto /* default */
           or <width>
}

```
26. flex-basis vs widths 💛
    1.  The browser will always use the value set with flex-basis.
    2.  But, if  you also set a min-width and max-width. In those cases, flex-basis will lose and will not be used as the width.

27. flex shorthand 💛
```css

.child {
  flex: 0 1 auto /* default */
     or <flex-grow> <flex-shrink> <flex-basis>
     or <flex-grow>
     or <flex-basis>
     or <flex-grow> <flex-basis>
     or <flex-grow> <flex-shrink>
}

```
28. align-self 💛
    1.  our align-items property where we can set the flex item along the cross axis. The thing with align-items is that it forces all of the flex items to play with its rules.
    2.  But what if you want one of them to break the rule?
    3.  you can use `align-self`. this property accepts all of the same values given to align-items, so you can easily break from the pack.
```css
.child-1 {
  align-self: stretch /* default */
           or flex-start
           or flex-end
           or center
           or baseline
}

```
29. flexbox cheatsheet 💛
 
|Direction |AlIGNMENT|SIZE|
|---|---|---|
|flex-direction<br>flex-wrap<br>flex-flow<br>order|justify-content<br>justify-content<br>align-items<br>align-content<br>align-self|flex-grow<br>flex-shrink<br>flex-basis<br>flex|

        
30.  Bonus: Aligning with Auto Margins 💛
     1.  when we want to place items on top `margin-bottom: auto`
     2.  when we want to place items at bottom  `margin-top: auto`
     3.  when we want to place items at center `margin: auto`
     4.  when we want to place items at right `margin-left: auto`
     5.  when we want to palce items at left `margin-right: auto`










---

# 참조

[https://w3.org/TR/css-flexbox-1/#align-items-property](https://w3.org/TR/css-flexbox-1/#align-items-property)
[https://www.samanthaming.com/flexbox30/6-parent-properties/](https://www.samanthaming.com/flexbox30/6-parent-properties/)

This is the end of Today I Learned

오늘도 한걸음씩! 능력있는 개발자가 됩시다 🙋


[flex-grow calculation]: https://www.samanthaming.com/flexbox30/22-flex-grow-calculation/
[def]: https://www.samanthaming.com/flexbox30/24-flex-shrink-calculation/