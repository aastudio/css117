# minimalUI

minimalUI provides minimalist, lightweight & effectives Responsive components.

## minimalGrid

A minimal, lightweight (~ 3Ko minified) and highly customizable grid. If **you just need a grid**, minimalGrid is what you need by providing **only the necessary code**.

### How to use

Download the latest release and put the SASS folder in your website directory. If you don’t know SASS have a look at [their website](http://sass-lang.com). 

With the Terminal, go to the desired folder to run SASS: 

```CLI
sass --watch src/sass/main.scss:dist/css/main.css
```
**NOTE** or run it with a task runner : [Gulp](https://www.npmjs.com/package/gulp-sass/), [Grunt](https://www.npmjs.com/package/grunt-sass/), [Broccoli](https://www.npmjs.com/package/broccoli-sass/), ...

Put the required stylesheet ```main.css``` between ```<head>``` tags:

```html
<head>
	...
	<link rel="stylesheet" href="dist/css/main.css">
	...
</head>
```

Set up your HTML markup

```html
<div class="row">
	<div class="col large-4 medium-6 small-12">...</div>
	<div class="col large-4 medium-6 small-12">...</div>
	<div class="col large-4 medium-12">...</div>
	<div class="col large-6">...</div>
	<div class="col large-6">...</div>
	<div class="col large-5">...</div>
	<div class="col large-4">...</div>
	<div class="col large-3">...</div>
</div>
```

### Customize

The ```partials/components/minimalGrid.scss``` file offers few variables that can be customized :

- [```Grid settings```](#user-content-grid-settings)
- [```Mobile first```](#user-content-mobile-first)
- [```floats``` or ```inline-block```](#user-content-floats-or-inline-block)
- [```Development mode```](#user-content-development-mode)
- [```A unique column width for the 'small' breakpoint```](#user-content-one-width-for-the-small-breakpoint)
- [```Offset classes```](#user-content-offset-classes)
- [```Visibility classes```](#user-content-visibility-offset-classes)
- [```Customizable class names```](#user-content-customizable-class-names)

### Grid settings

The ```$breakpoints``` SASS map has three keys :
- ```width```
- ```gutter-width```
- ```nb-of-columns```


```width``` and ```gutter-width``` must be set in pixels. The component will convert ```gutter-width``` in percentage based on the ```width```.

```nb-of-columns``` is a unitless variable. It defines the number of columns you want in your grid. Default value is 12.

### Mobile first

By default minimalGrid is not Mobile First. If you set the variable ```$mobile-first``` to ```true```, you have to inverse the order of the breakpoints in ```mixins/mq.scss``` from ```small``` to ```large```.

The component will automatically switch the ```max-width``` query to ```min-width```.

**The ```small``` breakpoint is a mandatory name for the smallest breakpoint**. Any other name for larger size can be anything.

### floats or inline-block

Don't know the difference between ```floats``` and ```inline-block``` ? check [this page](http://www.vanseodesign.com/blog/demo/inline-block/).

By default the grid is set to ```inline-block``` with the variable ```$positionScheme```:
- It allows you to vertically align elements.
- Because it is an inline behaviour, each ```.col``` automatically goes to a new line if there's not enough space, no matter the heights of previous columns.

If you choose ```floats``` , each row of columns needs to be wrap within a ```row``` class or [with the name of your choice](#user-content-customizable-class-names).

Soon a [```flexbox```](http://www.w3.org/TR/css-flexbox-1/) option will be available.

### Development mode

If set to true, it adds a pink transparent background-color behind elements and blue sides border to each columns.

### A unique column width for the 'small' breakpoint

By default, each columns of the ```small```breakpoints have individual sizes. But in real use, you might want to set a full width for each columns from the small breakpoint.<br/>

Therefore you don't need to add the ```small``` classes to your markup :
```html
<div class="row">
	<div class="col large-4 medium-6">...</div>
	<div class="col large-4 medium-6">...</div>
	<div class="col large-4 medium-12">...</div>
	...
</div>
```

### Offset classes

If you need to move blocks up to 11 columns to the right, set ```$offset``` to true.

### Visibility classes

Visibility classes let you show or hide columns based on screen size.<br>
Set ```$visibility``` to true.

### Customizable class names

Each class name can be customized regarding your naming convention preferences ([BEM](https://en.bem.info/method/naming-convention/), [SUIT](https://github.com/suitcss/suit/blob/master/doc/naming-conventions.md), etc.)

## The Media Query mixin

*SOON*

## TODO

- create a demo page
- create a npm package
- create a flexbox version
- made an online generator for non-SASS users

## License

The code and the documentation are released under the [MIT License](LICENSE).
