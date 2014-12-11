# muffins

muffins is a Sass-Framework. The special feature of the framework is that it consists exclusively of as a reset, grid and utility classes. Everything else is managed via themes.

**Why you should use muffins?**
  
  - **Create your own grid**
  - Full responsive - Mobile First
  - Built in intelligent HTML5 und CSS3
  - Scalable
  - Extensible Configuration
  - Semantic Markup
  - 100% free under the MIT

  
**Grid**

The muffins grid is fully configurable via variables. Thus excess CSS code is avoided. You can easily define your breakpoints and grid classes. You do not need a breakpoint? No problem, it is only generated the grid code you actually need! You have a finely tuned website that has many breakpoints, no problem! You get all grid classes you need.

**CSS-Reset**

Muffins already includes a standard reset, where HTML5 elements for older browsers and browser-specific CSS preconfigured statements are useful overwritten.

**Utility-Classes**

With the utility classes, you can easily configure content.

**Themes**

The complete style of muffins is outsourced in themes. If you only need a grid, you have therefore no excess CSS code. Would you just quickly create a prototype, you can easily use a theme with all the basic formatting.
p Since the themes are completely cut off from the grid, it is easy to define new ones. Sometimes it is enough to adjust the colors and variables in the config files to get a costumized application or website.


## Setup

### Get started

  1. Download grid and/or theme
  2. Install Ruby
  3. Install Sass
  4. Include the grid and theme in your project

### Download

muffins offers various possibilities for a quick start.

The special of muffins is: It is a pure Sass-Framework! We offer no CSS variants, because you should first create your grid individually. The whole interaction of grid, theme and your costum styles works in Sass.

### Include the grid and theme in your project

#### Include grid

In the download package you will find the folder "muffins" with the following file structure. This folder contains all the components of the grid.

  - muffins/
    - config/
      - _grid.scss
    - mixins/
      - _grid.scss
    - modules
      - _global.scss
      - _grid.scss
      - _utility-classes.scss
    - reset/
      - _base.scss
      - _html5.scss
      - _lists.scss
      - _typography.scss
    - style.scss

Now add the muffins folder in your project.

Here you can have a custom settings for your grid (for further explanation, see Grid. Then you need to include the framework in your project's own Sass file `@import "[Path to muffins]/style"

Now you can use the grid.

#### Include theme

In the download package you will find a folder with the theme name with the following exemplary folder structure. This folder contains all components of the theme. Note here that the files here quite differently named, removed, or may have been added in addition.

  - [filename theme]/
    - config/
      - _buttons.scss
      - _colors.scss
      - _layout.scss
      - _typography.scss
    - mixins/
      - _buttons.scss
      - _typography.scss
    - patterns/
      - blocks/
        - _buttons.scss
        - _code.scss
        - _lists.scss
        - _typography.scss
      - components/
        - _navigation.scss
        - _callouts-prompts.scss
          li.folder
      - modules/
        - _header.scss
        - _layout.scss
        - _topbar.scss
        - _footer.scss
        - _product.scss
    - vendor/
  - style.scss

Now add the theme folder to your project. Then you need to include the framework in your project's own Sass file. `@import "[Path to theme]/style"`

Now you can use the theme.

-------------------------------
## Grid

muffins comes standard with a 12-column repsonsive grid, with the mobile first approach. The grid can be based on the viewport or a maximum width. The special feature of grid in muffins is that you can define both the number of breakpoints and the number of columns and their distances completely variable. So you can  quickly and easily create your own grid.

### Variables

#### grid-max-width

The maximum width of the grids can be specified in pixels, em or percentages. (default: 1440px)

#### space

The distance between the columns, in pixels, em or percentages are given. (default: 8px)

#### total-columns

The number of columns is variable. Thus you can build your individual grid and adapt it to your situation completely. (default: 12)

#### grid-breakpoints

With muffins you can not only determine the number of breakpoints, you can define the class name also quite simple. You want no division in size but in name device name? No problem!

Simply enter your class name, the min-width and max-width and you're ready to generate your own grid. (default: ('xl', 1261px, null), ('lg', 961px, null), ('md', 641px, null), ('xl', 321px, null), ('xs', 220px, null))


### The default grid

The default grid classes are composed of the prefix "col", the class name and the number of columns together (this will be "-" separated), eg . "col-xs-6"

**Usage**

```
<div class="row">
  <div class="col-xs-12">.col-xs-12</div>
</div>

<div class="row">      
   <div class="col-xs-1">.col-xs-1</div>      
   <div class="col-xs-11">.col-xs-11</div>      
</div>

<div class="row">      
  <div class="col-xs-2">.col-xs-2</div>
  <div class="col-xs-10">.col-xs-10</div>
</div>

<div class="row">
  <div class="col-xs-3">.col-xs-3</div>
  <div class="col-xs-9">.col-xs-9</div>
</div>

<div class="row">
  <div class="col-xs-4">.col-xs-4</div>
  <div class="col-xs-8">.col-xs-8</div>
</div>

<div class="row">
  <div class="col-xs-5">.col-xs-5</div>
  <div class="col-xs-7">.col-xs-7</div>
</div>

<div class="row">
  <div class="col-xs-6">.col-xs-6</div>
  <div class="col-xs-6">.col-xs-6</div>
</div>

<div class="row">
  <div class="col-xs-7">.col-xs-7</div>
  <div class="col-xs-5">.col-xs-5</div>
</div>

<div class="row">
  <div class="col-xs-8">.col-xs-8</div>
  <div class="col-xs-4">.col-xs-4</div>
</div>

<div class="row">
  <div class="col-xs-9">.col-xs-9</div>
  <div class="col-xs-3">.col-xs-3</div>
</div>

<div class="row">
  <div class="col-xs-10">.col-xs-10</div>
  <div class="col-xs-2">.col-xs-2</div>
</div>

<div class="row">
  <div class="col-xs-11">.col-xs-11</div>
  <div class="col-xs-1">.col-xs-1</div>
</div>
```

### Nested Grid

All Grid classes you can nest arbitrarily. For this, you need only create a new `row`.

**Usage**

```
 <div class="row">
    <div class="col-xs-11">
       <div class="row">
          <div class="col-xs-4">.col-xs-4</div>
          <div class="col-xs-4">.col-xs-4</div>
          <div class="col-xs-4">.col-xs-4</div>
       </div>
    </div>
    <div class="col-xs-1">.col-xs-1</div>
 </div>
 ```

### Visibilty Classes

With Visibilty classes you can depending of the screen size and orientation and hide elements.

#### Screen sizes detection

**Usage**

```
<div class="row">
  <div class="col-xs-12 hide-md">.col-xs-12 .hide-md</div>
  <div class="col-xs-12 hide-xs show-md">.col-xs-12 .hide-xs .show-md</div>
</div>
```

#### Orientation detection

**Usage**

```
<div class="row">
  <div class="col-xs-12 hide-for-landscape">.col-xs-12 .hide-for-landscape (is portrait)</div>
  <div class="col-xs-12 hide-for-portrait">.col-xs-12 .hide-for-portrait (is landscape)</div>
</div>
```

### Ordering classes

With the ordering classes you can customize the order of your container without changing the HTML code.

**Usage**

```
<div class="row">
  <div class="col-xs-9 push-xs-3">.col-xs-9 .push-xs-3  (1. Div)</div>
  <div class="col-xs-3 pull-xs-9">.col-xs-3 .pull-xs-9  (2. Div)</div>
</div>
```

### Offset Classes

With the offset classes you can add any offset for columns. 

**Usage**

```
<div class="row">
  <div class="col-xs-6 offset-xs-3">.col-xs-6 .offset-xs-3 </div>
</div>
```

-------------------------------

## Browser compatibility


### Browser without media queries

Muffins builds on mobile-first. To even support old browsers that do not yet support media queries (e.g IE > 9) and to ensure a "web view", muffins will create an extra stylesheet that contains no media queries and, moreover, the "mobile-first" statements will be overwritten by the "web view" statements.


#### Create Stylesheet Data 

To create the style sheet file without media queries, you have to create a new `code .scss` file. In this you override the variable `$fix-mqs` with `true`. Well but still have to import the standard styles. To make it easier to hold and nurture avoid double, you can easily import your `style.scss` here.

#### Usage Mixins

Of course you can also use the mixin `fix-media-queries()` in your own styles. It should be noted that you have a `$min-width` as well as a `$max-width` (default: false).

**Usage**

```
.content {

float: left;
 
width: 60%;
 
background-color: red;
 
 
@include fix-media-queries (350px) {
 
background-color: green;
 
}
  
@include fix-media-queries (496px, 1024px) {
 
background-color: blue;
 
}
 
}

```
### Old browser

Old browsers (eg IE < 9) sometimes require a different stylesheet.

With muffins you can include these statements directly in your sass files. With the Mixin `old-browser()` you can explicitly create statements for old browsers that you can separate in a separate stylesheetfile.

**Usage**

```
.content {

width: 80%;

margin: 0 auto;


@include old-browser {

zoom: 1;

whatever-you-need: comes here;

}

}

```

#### Generate stylesheet file

For this, you just have to create a new Sass file and set the variable `$old-browser` to `true` Then import the default style with `@import "style";` and even a stylesheet file for old browsers is generated.

### IE10 "snap" Mode

muffins included a small snippet of code to fix the IE10 "Snap" Mode. More informations you can get a href="http://timkadlec.com/2012/10/ie10-snap-mode-and-responsive-design/"` here.

---------------------------------------------------

## Helper

muffins by default contains some helper classes.

### Classes

#### Floating 

With the classes `.left`, `.right` and `.clearfix` elements can be positioned quickly and easily.

**Usage**

```
<div class="clearfix">
   <a class="btn primary left">.left</a>
   <a class="btn primary right">.right</a>
</div>
```

#### Hide 

##### Hide Elemente

To hide an item you can just use the class `.hide`.

**Usage**

```
<div class="hide"></div>
```

##### Hide Text

To hide only the text you can just use the class `.hide-text` nutzen.

### Mixins

#### Size 

To quickly and easily determine the size of an element, you can use the mixin `size($width, $height: $width)`.

**Usage**

```
div1 {
  @include size(50px);
}
div2 {
  @include size(100px, 20px);
}
```

**Output**

```
div1 {
  width: 50px;
  height: 50px;
}
div2 {
 width: 100px;
 height: 20px;
}
```
#### Positioning 

To quickly and easily position Elemnte you can use the mixins `absolute($args)`, `fixed($args)` and `relative($args)`.

In $args you can indicate all offsets, for example `left 1em top 1.5em` or `top 5px right 10px bottom 15px left 10px`.

#### Fontsizes in Rem

With the `font-size-rem($size)` and `line-height-rem($size)` mixins you can easily convert px in rem to have even px value given to a fallback.

#### Background images

Retina backgroud images make us more problems. With muffins that is no longer a problem. The Mixin `background-image($name, $size:false)` helps you easily integrate retina wallpapers.

In the "_helper.scss" in the "config" folder you can see your image file path (`$image-path`),  your file extension(`$image-extension`) and your retina suffix (`$retina-suffix`) to configure.

#### Styles

muffins contains some mixins for style for different browsers

##### Placeholder

To fetch alle placeholder-versionin css you can easily use the `placeholder()` mixin. 

**Usage**

```
input {
  color: blue;
  @include placeholder {
     color: red;
  }
}
```



---------------------------------

# Authors

Created by [Stefanie Böhme](https://twitter.com/_Funshinebear )
