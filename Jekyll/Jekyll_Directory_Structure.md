# Jekyll File Structure
## _config.yml
Holds the configuration for your Jekyll site. This is commonly used to:
- Set **global variables** on the site
- Configure collections or defaults
- **Specify runtime variables** we want to run every time

## _drafts
All our unpublished blog posts. This allows us to work on blog posts **without publishing them** to the live site.

## _includes
Page snippets which can be included throughout our site. Includes are often **used for page sections** which are duplicated across the site like a newsletter subscribe form.

## _layouts
**Templates which wrap around content**. All the repeating HTML on our site like the **header**, **footer** and **navigation** typically live in a layout.

## _posts
Contains our blog posts usually written in Markdown.

## _data
`_data` contains YAML, JSON and CSV files. The data in these files can be used throughout the Jekyll site.

## _site
Once Jekyll has built our site it puts the entire static site including all our assets in `_site`.

## .jekyll-metadata
This file is used by Jekyll’s incremental build feature to **keep track of the files** which have changed.

## Other Files/Folders
Files with front matter are processed and output to `_site` on a build. Files **without** front matter (typically CSS, JavaScript and image files) are copied straight to `_site` on a build.


# Liquid
[Official Site](https://jekyllrb.com/docs/step-by-step/02-liquid/)  
[Liquid Github](https://github.com/Shopify/liquid)  
[Liquid Documentation](https://shopify.github.io/liquid/)

- A template language which contains three main parts (**objects**, **tags**, and **filters**), with very specific requirements
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
- By the `page` variable, we can access the front matter.
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

- In Jekyll, we can use layouts to **eliminate the redundant codes on several pages**.
- For CSS files that will be imported for each pages and other repeating part (like page header, navbar, and footer elements), usually written on `<head>` and `<footer>`, then we should use **layout** to prevent copy and pasting duplicated code.
  + use *default layout* to contain all the same matters.
  + Can use layout inside of the layout.  

See code sample at **[Official Site](https://jekyllrb.com/docs/step-by-step/04-layouts/)**  

Suppose we have a `default.html`, and you want to use this layout's structure for a pages, then we should add ***front matter*** like   
```
---
layout: default
---
```
at the most upper part.  
You can set variables inside and outside of the layout, and on hte other html.  

**Conclusion**  
- Use layout properly as a template for each page.  
- I felt concept of layout in Jekyll is similar to the class of other Object-Oriented Programming languages (like Java, C++, and so on)
  + **Capsulize** the contents and **increase reusability** of code
  + Able to let end-user to **change contents without knowing how developer designed the code** (Abstract)
- Overall, this will increase the productivity of website development


# Includes
[Official Site](https://jekyllrb.com/docs/step-by-step/05-includes/)

- To **reduce the duplicated source codes** on the website  
- To use an include we need to create a new folder called `_includes`
  + Inside this we create the `duplicatedCodes.html`
  + Write down duplicated part on `duplicatedCodes.html`
  + Replace the duplicated codes with this tag: `{% include duplicatedCodes.html %}`  
    This code will retrieve code fragment from `_includes/duplicatedCodes.html`
- Using this to **increase readability of code**, working ***similarly as "Separating methods" on programming***

# Data Files
[Official Site](https://jekyllrb.com/docs/step-by-step/06-data-files/)  
[Reference](https://learn.cloudcannon.com/jekyll/introduction-to-data-files/)

- Loading data from **YAML**, **JSON**, and **CSV**
- Need to be located in a `_data` directory

Creating a folder, `_data`, and inside this we can create a file `fileName.csv`.  
The data file is available at `site.data.fileName`, and we can run this through the *jsonify* filter to output an **array** our JavaScript can understand.  
In JavaScript, we can use jsonify files directly into the variables, so here is the example: `let name = {{ site.data.[fileName] | jsonify }};`.

For the json type, also can access like an **array**.  
Suppose that you have a file `authors.json` like this:
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

Compare between JSON, YAML, and CSV: See [this link](https://github.com/hyecheol123/KSEAWebDocuments/tree/Yongsang_Jekyll_DirectoryStructure/Jekyll/Compare_Data_File_Types)


# Assets
[Official Site](https://jekyllrb.com/docs/step-by-step/07-assets/)
Structure of assets in Jekyll site:
```
├── assets
|   ├── css
|   ├── images
|   └── js
```

You can use either CSS or Sass.  
※[Sass](https://sass-lang.com/) (Syntactically Awesome Style Sheets) is kind of extension of CSS. You can put much more variables and nestings, and also have many functions.

For Sass,
- create a Sass file at `/assets/css/styles.scss` with the following content:
```
---
---
@import "main";
```

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
