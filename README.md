# style_guide_v3
Treehouse Front End Web Development Project 5

### Project Overview

-   #### Organize your Sass files.

    -   Create a `scss` folder in your project.
    -   In the `scss` folder, create the following subfolders to organize your CSS code into SCSS partial files:
        -   `utilities` (a folder to contain partials for global variables, extends, mixins, and functions)
        -   `base` (for the normalize.css file and base styles that are used in the project)
        -   `components` (to contain partials for each part of your site: grid, typography, navigation, images, buttons, forms)
    -   Each subfolder you create should contain an _index.scss file. You'll use that file to import each sass partial file in the folder.
    -   Create a css folder for your compiled CSS. As you work on the project, you'll be able to run `sass --watch scss:css` from the command line to compile the sass that you write.
    
````
D:.
├───base
├───components
└───utilities
````

-   #### Create a styles.scss file in the root of your Sass project (in your 'scss' folder).

    -   Import all of your _index.scss partials into this main `styles.scss` file.
    -   Make sure your imports are listed in the correct order for styling.

-   #### Create a partial for variables in your utilities folder

    -   Use this partial to create variables for your repeated values.
    -   At minimum, create variables for fonts, breakpoints, and colors.
    -   Import this partial into your utilities/index.scss file

-   #### Create a partial for your mixins in your utilities folder

    Inside your mixins partial, you'll want to create mixins for:

    -   Media Queries
    -   Flexbox settings
    -   Element and Modifier BEM Selectors

-   #### Create a partial for your placeholders in your utilities folder

    In your placeholder partial, create placeholders for at least the following:

    -   Links
    -   Images
    -   Headlines
    -   Nav items

-   #### Components

    All your styles for this project will be applied using the classes listed in the comment at the top of the index.html file. You'll style these classes in the components folder. Try not to combine selectors from two different categories. For example, avoid using `.grid__col--8 .link` to style the link in the typography section, as it makes the style of links dependent on what grid column they're in. The best way to organize this is to make a file in the components folder for each of the following:

    -   Grid (recommend using flexbox)
    -   Typography
    -   Navigation
    -   Images
    -   Buttons
    -   Forms

-   #### Base folder

    In your base folder, include a `normalize.css` file and create a `base.scss` file. In the base.scss file, you can only apply styles to three different elements directly:

    -   the universal selector (*)

    -   ul elements
    
 -   #### Use the flexbox mixin you built to apply flexbox properties in your project.
 
 -   #### Use the media query mixin to apply all your media queries.
 
 ````
 // ==========================================================================
// Media Queries
// ==========================================================================

@mixin mq($break) {
    $value: map-get($breaks, $break);
    $med: map-get($breaks, 'med');
    
    @if $value == null {
        @error "`#{$break}` is not a valid breakpoint name";
    }

    @else if $value < $med {
        @media(max-width: $value) {
            @content;
        }
    }

    @else {
        @media (min-width: $value) {
            @content;
}
    }
}

// ==========================================================================
// Flexbox Configuration
// ==========================================================================

@mixin flex($direction: column, $justify: space-between, $wrap: null){
    display: flex;
    flex-direction: $direction;
    flex-wrap: $wrap;
    justify-content: $justify;
}

// ==========================================================================
// BEM Selectors
// ==========================================================================

@mixin e($element) {
    &__#{$element} {
        @content;
    }
}

@mixin m($modifier) {
    &--#{$modifier} {
        @content;
    }
}
 ````
