Implicit-Grid
=============

a sass grid system based on percentages

###mixins avialable:

####wrappers

    wrap
    inner-wrap
    hide-overflow
    
####prefixers for col and col-imp

    last *
    pad *
    inline *
    shift *   - args: Columns-to-shift: 0 (can be positive or negative)
    fill-left *   - args: Cols to Pad: 1
    fill-right *  - args: Cols to Pad: 1
    
####the column generater

    col-imp   - args: Col-Width of Parent-Size, Last: false, Col shift: 0
    col     - args: Col-Width of Parent-Size, Last: false, Col shift: 0, Inline: false

####add margin to elements the same width as your gutters

    gutter-margin-bottom   - args: Multiple: 1
    gutter-margin-top     - args: Multiple: 1
    gutter-margin-right 
    gutter-margin-left   

####add padding to elements the same width as your gutters

    gutter-padding-bottom   - args: Multiple: 1
    gutter-padding-top     - args: Multiple: 1
    gutter-padding-right 
    gutter-padding-left 


Take note that mixins marked with * must be used above col-imp or col to work properly


col-imp works differently than most grid systems. It requires an inner-wrap whose width is set larger than the wrap containing it. A wrap around inner-wrap is needed to hide the overflow. This hidden extra space allows each element inside the inner-wrap to have a right margin (even the last element!). Hence the imp, sort for implicit. This means you can rearrange these elements and not have to worry about clearing out the right margin on the last element. Whether you're rearanging the order via jQuery, changing elements' column width via media queries, or using js masonry.

####using col-imp, your code would look like:

sass:

    .col-4 {
        @include col-imp(4);
    }
    
html:

    <div class="wrapper">
        <div class="hide-overflow"> <!-- only if needed -->
            <div class="inner-wrapper">
                <div class="col-4"></div>
                <div class="col-4"></div>
                <div class="col-4"></div>
                <div class="col-4"></div>
            </div>
        </div>
    </div>
