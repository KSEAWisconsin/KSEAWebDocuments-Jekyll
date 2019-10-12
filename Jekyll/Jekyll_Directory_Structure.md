# Liquid
[Official Site](https://jekyllrb.com/docs/step-by-step/02-liquid/)  
[Liquid Github](https://github.com/Shopify/liquid)  
[Liquid Documentation](https://shopify.github.io/liquid/)

### Basic Descriptions
- A template language which contains three main parts (**objects**, **tags**, and **filters**), with very specific requirements

### Features
- Allow to reuse common parts of website instead of making separated HTML files by hands.
  + Need to tell Jekyll to process Liquid on **[Front Matter](https://github.com/hyecheol123/KSEAWebDocuments/blob/Yongsang_Jekyll_DirectoryStructure/Jekyll/Jekyll_Directory_Structure.md#front-matter)**.
  + Front Matter contains data for Liquid object
- Objects  
  + `{{ page.title }}`
  + To tell Liquid to output contents, using `{{` and `}}` to represent object
  + When sample code contains in the page, Liquid will render the contents of an object named `page.title`
- Tags  
  ```
  {% if page.show_sidebar %}
    <div class = "sidebar">
      sidebar content
    </div>
  {% endif %}
  ```
  + Creating logic and control flow for template
  + Denoted by `{%` and `%}`
  + Tag does **not produce any visible text**, just *help* site-generator to build the page without showing the logic behinds it.
  + More information for tag supported by Jekyll can be found at the [official documentation](https://jekyllrb.com/docs/liquid/tags/)
  + Tag are categorized as three types
    * [Control Flow](https://shopify.github.io/liquid/tags/control-flow/)
    * [Iteration](https://shopify.github.io/liquid/tags/iteration/)
    * [Variable](https://shopify.github.io/liquid/tags/variable/)
    * See more details about available tags and usage of it on Liquid's official documentation site
- Filters
  + Used to change the output of a Liquid object
  + denoted by `|`
  + Example: `{{ "Hi" | capitalize }}`  
    Will gives output of `Hi`
  + Not only the [standard filters (see the list on the responsible category)](https://shopify.github.io/liquid/filters/abs/) of Liquid, Jekyll also has its [own filters](https://jekyllrb.com/docs/liquid/filters/).


# Front Matter
[Official Site](https://jekyllrb.com/docs/step-by-step/03-front-matter/)

- Snippet of YAML which sits between two triple-dashed lines at the top of a file.  
Ex)
```
---
my_number: 5
---
```

To use the font matter, we need to refer this:

```
---
title: Home
---
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">
    <title>{{ page.title }}</title>
  </head>
  <body>
    <h1>{{ "Hello World!" | downcase }}</h1>
  </body>
</html>
```

Looks like more complicate than HTML, but it is highly related with **Layout**.

# Layout
[Official Site](https://jekyllrb.com/docs/step-by-step/04-layouts/)
- Markdown as well as HTML



# Includes
[Official Site](https://jekyllrb.com/docs/step-by-step/05-includes/)

### Basic Descriptions

### Features


# Data Files
[Official Site](https://jekyllrb.com/docs/step-by-step/06-data-files/)

### Basic Descriptions

### Features


# Assets
[Official Site](https://jekyllrb.com/docs/step-by-step/07-assets/)

### Basic Descriptions

### Features


# Writing Posts
[Official Site](https://jekyllrb.com/docs/step-by-step/08-blogging/)

### Basic Descriptions

### Features


# Collection
[Official Site](https://jekyllrb.com/docs/step-by-step/09-collections/)

### Basic Descriptions

### Features


# Deployment
[Official Site](https://jekyllrb.com/docs/step-by-step/10-deployment/)

### Basic Descriptions

### Features


# Theme

### Basic Descriptions

### Features
