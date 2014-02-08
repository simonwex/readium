V2 UNDER DEVELOPMENT

# skit
`skit` is a pure sass library which allows you to build websites much easier. In an era of responsive design you have to write more code to generate awesome sites. With `scss` (also known as `sass`) and `skit` you will reduce the lines of code you write during a project.

## Fonts
`skit` comes with a lot of font implementations. You can use _mixins_ to generate the `@font-face` attributes. Lets see an example:

    @import 'font.less'; // import the font container to access the mixins
    @include droid();    // enables droid sans for your project

## Mixins
### Container
With this mixin you can generate a container. The mixin also creates `.span` elements which you can access on your html document.

    // import the util library
    @import "util.scss";

    // generates a container with 1200px and 12 parts (span-1, span-2, span-3 and so on)
    @include container(1200px, 12);

You can also change the position of your container using the third parameter (select between `center`, `left` as well as `right`).

    @include container(1200px, 12, "center");

### Block elements
To change the position of your nodes you can use the mixins `block-center`, `block-right` as well as `block-left`.

    .container {
        width: 1000px;
        @include block-center();
        .sidebar {
            @include block-right();
            &.left {
                @include block-left();
            }
        }
    }

The named mixins also available as css classes:

    <div class="container block-center">
        <div class="sidebar block-right">
        </div>
    </div>

### Borders
The border-radius property is supported in IE9+, Firefox 4+, Chrome, Safari 5+, and Opera. You can access the following border mixins:

 - border-radius
 - border-top-left-radius
 - border-top-right-radius
 - border-bottom-right-radius
 - border-bottom-left-radius
 - border-top-radius
 - border-right-radius
 - border-bottom-radius
 - border-left-radius

Example:

    .content {
        @include border-radius(4px);
        background: #fff;
    }
