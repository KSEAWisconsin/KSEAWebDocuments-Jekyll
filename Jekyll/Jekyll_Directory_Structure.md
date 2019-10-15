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
  + Example: `{{ "hi" | capitalize }}`  
    Will gives output of `Hi`
  + Not only the [standard filters (see the list on the responsible category)](https://shopify.github.io/liquid/filters/abs/) of Liquid, Jekyll also has its [own filters](https://jekyllrb.com/docs/liquid/filters/).


# Front Matter
[Official Site](https://jekyllrb.com/docs/step-by-step/03-front-matter/)

Front matter lives between **two triple dashed lines (---)** at the **top** of the file.  
Write YAML to set variables.

For example,
```
---
hello_text: "Hello there!"
---
...
    <p>{{ page.hello_text }}</p>
...
```
will give the result of "Hello there!" inside the paragraph.
- *hello_text* is a name of the variable.
- *"Hello there!"* is the value of the variable.
- To use this, must use **[liquid](https://github.com/hyecheol123/KSEAWebDocuments/blob/Yongsang_Jekyll_DirectoryStructure/Jekyll/Jekyll_Directory_Structure.md#liquid)**.

We can put **Arrays** inside the front matter like this:
```
fruit:
  - apple
  - banana
  - orange
```
Each item is **indented with two spaces then starts with a hyphen**.  
To **set the value** in the body of the page we will **iterate over the items** and output them as an **unordered list**.
```
<ul>
  {% for item in page.fruit %}
    <li>{{ item }}</li>
  {% endfor %}
</ul>
```

Also you can put nested array inside the front matter:
```
fruit:
  - name: apple
    cost: $1
  - name: orange
    cost: $1
```
Instead of having strings as the array items, we want them to be **keys and values**.
```
<ul>
  {% for item in page.fruit %}
    <li>{{ item.name }}, cost: {{ item.cost }}</li>
  {% endfor %}
</ul>
```


# Layout
[Official Site](https://jekyllrb.com/docs/step-by-step/04-layouts/)  
[Reference](https://learn.cloudcannon.com/jekyll/introduction-to-jekyll-layouts/)

- Markdown as well as HTML
- In Jekyll, we can use layouts to **eliminate the repetitions** page by page.
  + Like *header*, *footer*, and same codes, then we can use default.html as layout.
    - *default.layout* is a layout that contains all the same matters.
  + Can use layout inside the layout.  

Suppose you have a *default.html* and you want to add all the single pages, then use  
```
---
layout: default
---
```
at the most upper part then you can see every single *default.html* page where you used that format. You can set veriables inside the layout and can set the value outside the layout, or other html.  

Once again, the purpose of the layout is **reducing repetitions**.  

Also inside the code, we can put conditions with the liquid format. On our landing pages (which used the default.html as a layout) we can set conditions or values in the front matter.

# Includes
[Official Site](https://jekyllrb.com/docs/step-by-step/05-includes/)

### Basic Descriptions
- Also the purpose is decreasing the duplicated source codes on the website.

To use an include we need to create a new folder called *_includes*. Inside this we create the duplicatedCodes.html. Now we can implement this source code across to each page. Replace the duplicated codes like this:  
`{% include duplicatedCodes.html %}`

# Data Files
[Official Site](https://jekyllrb.com/docs/step-by-step/06-data-files/)

### Basic Descriptions
- Loading data from **YAML**, **JSON**, and **CSV**
- Need to be located in a *_data* directory

Creating a folder, *_data*, and inside this we can create a file *fileName.csv*. The data file is abailable in Jekyll at *site.data.fileName* and we can run this through the *jsonify* filter to output an **array** our JavaScript can understand.  
In JavaScript, we can use jsonify files directly into the variables, so here is the example: `let name = {{ site.data.[fileName] | jsonify }};`.

For the json type, also can access like an **array**.  
Suppose that you have a file *authors.json* like this:
```
{
  "mike": {
    "full_name": "Mike Neumegen",
    "image_path": "/images/mike.jpg",
    "twitter_handle": "mikeneumegen"
  },
  "george": {
    "full_name": "George Phillips",
    "image_path": "/images/george.jpg",
    "twitter_handle": "gphillips_nz"
  }
}
```
then you can access the data of mike like `{{ site.data.authors[mike] }}`.  
Also you can set the value of the author to access each by each inside the front matter for the layouts or includes.


# Assets
[Official Site](https://jekyllrb.com/docs/step-by-step/07-assets/)

### Basic Descriptions

### Features


# Writing Posts
[Official Site](https://jekyllrb.com/docs/step-by-step/08-blogging/)

### Basic Descriptions
- Live in a folder called *_posts*.


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
