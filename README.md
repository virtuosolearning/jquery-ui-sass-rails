# jquery-ui-sass-rails

This gem packages the jQuery UI 1.10.0 stylesheets in **Sass format (SCSS syntax)** for the Rails 3.1+ [asset
pipeline](http://guides.rubyonrails.org/asset_pipeline.html).

It complements the [jquery-ui-rails](https://github.com/joliss/jquery-ui-rails), which already packages all the plain jQuery UI assets (javascript, css, images) by providing the stylesheets in Sass format allowing much easier customization through Sass variables.  It overwrites the plain CSS stylesheets from `jquery-ui-rails`.

## Installation

This gem already has `jquery-ui-rails` as a dependency, so it's enough to include only it in your Gemfile:

```ruby
gem 'jquery-ui-sass-rails'
```

## JavaScript

For the JavaScript part you should refer to the [jquery-ui-rails documentation](https://github.com/joliss/jquery-ui-rails) and do something like this:

```javascript
//= require jquery.ui.all
```

or this:

```javascript
//= require jquery.ui.datepicker
```

## Sass Stylesheets

For the stylesheets you should use Sass's `@import` instead of Sprocket's `= require`, just as the official `sass-rails` gem [recommends it](https://github.com/rails/sass-rails#important-note).

They way you import the stylesheets would be something like this:

```sass
// app/assets/stylesheets/application.css.sass

@import jquery.ui.core // you always want that stylesheet
@import jquery.ui.theme // import this when you want to build on jQuer UI's themeing
@import jquery.ui.datepicker // import all the modules you need
```

The big advantage that the jQuery UI stylesheets have been converted to Sass in this gem are that you have a super easy way to customize the themes using simple Sass variables.  You only need to specify your own values **before** you import the jQuery UI stylesheets:

```sass
// app/assets/stylesheets/application.css.sass

$bgColorContent: purple // set custom value for jQueryUI variable

@import jquery.ui.core
@import jquery.ui.theme // your custom variables will be used here
@import jquery.ui.datepicker
```

## Credits

This gem is only a complement to the `jquery-ui-rails` gem and wouldn't be possible without it's author [Jo Liss](https://github.com/joliss) and the other [contributors](https://github.com/joliss/jquery-ui-rails/contributors).

Since this is only a gem repackaging the jQuery UI library, the biggest thanks obviously goes out to the [jQueryUI team](http://jqueryui.com/about/).