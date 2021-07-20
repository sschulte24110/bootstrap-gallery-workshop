# Intro to Bootstrap

Welcome to the workshop! Today we're going to run through building the Curiosity
Week webpage using Bootrap. We already have the image assets saved in the
`images/` folder. `index.html` is already set up with the Bootstrap starter
template and stubbed out sections. `style.css` is where we'll do our custom
styling for the page, and `base.css` has some styles that are part of the
EDA branding that are not specific to Curiosity Week (like background tiles and
footer styling). The `content/` folder has code for each step, including the 
finished project.

We'll move pretty quickly but don't worry. You'll have access to the completed
project and recorded video so you can review at your leisure. 

## Core Concepts

### Intro
Bootstrap is a frontend CSS framework created by Twitter that provides a ton of 
utility classes for responsive behavior, component design, and typography.

Bootstrap uses css classes for everything. Their documentation is also stellar,
so I always recommend reading as much of the documentation as possible before
starting a project, otherwise the classes wont make much sense (this isnt something
you can just 'guess' at in most cases).

Bootstrap also uses what is called a 'mobile-first' strategy, which means that
unless otherwise specified, all styles by default are applied to screens at the
"extra-small" size and larger. To override behavior for larger screensizes 
(small, medium, large, extra-large), you have to explicitly specify it.

At a high level, there's two major "domains" that you can use bootstrap for, and
its up to you on how far you want to take it. The first is the responsive grid, 
and the second are component utilities like vertical and horizonal alignment,
navbar, form controls (buttons, inputs, drop-downs, etc), alerts, modals, icons,
and typography.

### Bootstrap Workflow

Our Bootstrap workflow will be as follows. We'll first set the layout with a
a navbar and footer, all working inside the Bootstrap `container` class. Then 
we break our content up into 'sections', each will become a Bootstrap `row`. Each
`row` will contain `columns` that take up a portion of the horizontal area, and we
can specify how those columns will adapt to smaller and larger screensizes.

In general we're "all in" on Bootstrap, so we want to use Bootstrap styles when
possible, even for simple things like typography, padding, margin, and centering.
This is because Bootstrap can adapt these styles behind the scenes as screen
sizes change which is especially helpful for relative consistency. 

Finally we'll take a look at images, centering, and custom theme options that
will work well with the Bootstrap system.

### The Grid
Bootstrap uses the concept of a 12-column "grid" to define how big content should
be in the page layout. It's up to you to decide how many columns a layout block
should take up. For example, for a full width column, simply use 12 columns (which 
is the default if not otherwise specified). For two columns taking up 50% width
each, both can use 6 columns. For 3 columns of equal width, you can use 4 columns
each.

To specify how wide a column should be, use the class `col-X` where X is how many 
columns to take up at all screen sizes. So `col-6` would be an element that takes up
6 columns.

The structure of a bootstrap layout requires the entire layout to have a class of
either `container` or `container-fluid`. Each block of column-based content needs
to be inside a parent that has the `row` class. You can have any number of rows, 
including rows inside of other content blocks (technically each `row` can have 
its own virtual grid of 12 columns too).
``` html
<div class="container">
   <div class="row">
      <div class="col-6"> 
         Left Column Content
      </div>
      <div class="col-6">
         Right Column Content
      </div>
   </div>
</div>
```

In addition, almost every bootstrap class has the ability to specify what screen
sizes you want the class to be active for. By default all classes are implied to
be active for "extra-small" screens and above. If you specify a different screen
size (small, medium, large, extra-large: `sm`, `md`, `lg`, `xl`), Bootstrap will 
apply that rule only for that screen size *and larger* only.

For example: 

  - `col-12` will take up all 12 columns on extra-small screens and larger (so all sizes)
   This can be short-cutted to simply `col` which implies taking up all 12 columns at
   all screen sizes. With Bootstrap, not specifying a screen width defaults to
   extra-small.
  - `col-md-6` will take up 6 column on medium screens and above, but drop back to 12 
   columns on `xs` and `sm` screens (like mobile phones).
  - `col-md-6 col-lg-3` will take up 12 columns on extra-small and small, 6 on medium, 
   3 on large.

You can also apply this strategy to utility helpers like margin and padding control,
typography, and responsive image controls.

### Margin and Padding

Bootstrap provides 5 levels of margin and padding, and they're super simple to use.
They can be applied to pretty much any html element. `m-x` for margin and `p-x` for
padding, where x is a number between 1 and 5 with 1 being the lowest value, and 5 being
the highest value. This applies the value to all 4 sides of the box model: top, right, 
bottom, and left. 

If you would like to specify adding padding to only one side of the box, you can specify
that too with `mt, mr, mb, ml` and `pt, pr, pb, pl`: `mt-3` will apply margin level 3 to 
just the top. `pt-1 pb-5` will apply padding level 1 to the top, padding level 5 to the
bottom.

Just like with the grid system, it is implied that unless otherwise
specified, padding/margin are applied at "extra-small screensizes and above" (so by 
default, all screen sizes). Often you may want to add padding around a container in large 
screens but a very little or no padding on mobile. Bootstrap makes this crazy simple. 
Just add the screensize to target like this: `p-xs-1 p-md-5` which says "Use padding 
1 to extra-small and small screens, but padding 5 for medium and large screens". As
mentioned before, "extra-small and larger" is implied by default so you can shorthand 
this to `p-1 p-md-5` (no need to specify `xs`).

### Typography and misc tooling.

Bootstrap provides a ton of commonly used functionality: text-centering, auto image resizing, 
buttons, typography heirarchy, vertical and horizontal centering, and other misc tooling 
like modals, form layouts, responsive navbars, and modals. As you can imagine, it's pretty 
easy to see how you could build a simple webpage using just Bootstrap for utilities, grid, 
and layout, and custom CSS for additional theming. Feel free to read the Bootstrap 
Documentation for more info.

## More Info

Read the Bootstrap Documentation, especially the section on the Grid and Components:
  - https://getbootstrap.com/docs/4.3/

More info on Bootstrap Starter Template:
  - https://getbootstrap.com/docs/4.3/getting-started/introduction/

More info on Font-Awesome and Bootstrap:
  - https://www.w3schools.com/bootstrap4/bootstrap_icons.asp

List of Font Awesome icons in the free package:
  - https://fontawesome.com/icons?d=gallery&m=free
