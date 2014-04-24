Implicit-Grid
=============

> A sass grid system based on percentages.

##About
Although it is called Implicit Grid, it also contains both implicit and explicit column generators. This grid system is extremely flexible. The total number of columns, width or the gutters, and wrapper size can all be changed in the settings file. 

The col-imp mixin works differently than most grid systems. It requires an inner-wrapper (called inner-wrap) whose width is set larger than the wrapper (called wrap) containing it. An extra wrapper around inner-wrapper is needed to hide the overflow. This hidden extra space allows each element inside the inner-wrap to have a right margin (even the last element!). Hence the imp, sort for implicit. This means you can rearrange these elements and not have to worry about clearing out the right margin on the last element. Whether you're rearranging the order via jQuery, changing elements' column width via media queries, or using js masonry.

[See a working example of this grid](http://jpweller.github.io/)

###Implicit Grid
PROS: No last class needed.
CONS: Extra markup to hide-overflow and have an inner-wrapper.

###Explicit Grid
PROS: No excess markup
CONS: Need to explicitly specify last column.


##mixins avialable:

####wrappers

    wrap
    inner-wrap
    hide-overflow
    
####prefixers for col and col-imp

    last *
    pad *
    inline *
    shift *       - args: $Columns-to-shift: 0 (can be positive or negative)
    fill-left     - args: $Cols-to-Pad: 1
    fill-right    - args: $Cols-to-Pad: 1
    
####the column generater

    col-imp   - args: $Col-Width of $Parent-Size
    col       - args: $Col-Width of $Parent-Size

####add margin to elements the same width as your gutters

    gutter-margin-bottom   - args: $Multiple: 1
    gutter-margin-top      - args: $Multiple: 1
    gutter-margin-right 
    gutter-margin-left   

####add padding to elements the same width as your gutters

    gutter-padding-bottom   - args: $Multiple: 1
    gutter-padding-top      - args: $Multiple: 1
    gutter-padding-right 
    gutter-padding-left 


mixins marked with * must be used above col-imp or col to work properly


####using col-imp, your code would look like:

sass:

    .col-4 {
        @include col-imp(4);
    }
    
html:

    <div class="wrap">
        <div class="hide-overflow">
            <div class="inner-wrap">
                <div class="col-4"></div>
                <div class="col-4"></div>
                <div class="col-4"></div>
                <div class="col-4"></div>
            </div>
        </div>
    </div>
