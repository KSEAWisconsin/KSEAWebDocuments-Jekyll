# Make Sass Stylesheet
ex) styles.scss:
```
---
# Front matter  // However there is no content, you should declare the front matter
---
Content
```
- Should save the file in the `css` folder
- After finishing the steps and constructing the server, then thie file `styles.css` will be created inside the directory `_site/css/`

# Make a Stylesheet Link in the Layout HTML
Inside the `<head></head>` block, declare the link:
```
<link rel="stylesheet" href="/css/styles.css">
```

# Use Sass Imports
- Put `.scss` files into the `_sass/` directory and combine them by using `@import` on the main scss file

For example, if you created `base.scss`, `font.scss`, and `layout.scss` in the `_sass/` directory, then write into the `styles.scss` like this:
```
# Front matter
---
// import
@import "base";
@import "font";
@import "layout";

```
- Be sure to use only English
- Be sure not to write the front matter in the scss files

# Set _config.yml
- To change the directory:
```
 sass:
 sass_dir: // put the directory to save
```
- To set the style:
```
sass:
 style: // choose one of nested, expanded, compact, and compressed
```
