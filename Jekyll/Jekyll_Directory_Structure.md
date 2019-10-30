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

Compare between JSON, YAML, and CSV: See [this link](https://github.com/hyecheol123/KSEAWebDocuments/tree/Yongsang_Jekyll_DirectoryStructure/Jekyll/Compare_Data_File_Types)

## YAML
[reference](https://idratherbewriting.com/documentation-theme-jekyll/mydoc_yaml_tutorial)

- You can access the value by using dot (.) sign

### Simple File
Suppose you have this simple YAML file named *samplelist*:
```
name:
  husband: Tom
  wife: Shannon
```
Then you can use with using Markdown + Liquid:
```
<p>Husband's name: {{site.data.samplelist.name.husband}}</p>
<p>Wife's name: {{site.data.samplelist.name.wife}}</p>
```
The result is:
> Husband's name: Tom
> Wife's name: Shannon

### Table or List
For the Table or List YAML file named *samplelist* like:
```
toc:
  - title: Group 1
    subfolderitems:
      - page: Thing 1
      - page: Thing 2
      - page: Thing 3
  - title: Group 2
    subfolderitems:
      - page: Piece 1
      - page: Piece 2
      - page: Piece 3
  - title: Group 3
    subfolderitems:
      - page: Widget 1
      - page: Widget 2 it's
      - page: Widget 3
```
You can access the data like:
```
{% for item in site.data.samplelist.toc %}
<h3>{{item.title}}</h3>
<ul>
{% for entry in item.subfolderitems %}
<li>{{entry.page}}</li>
{% endfor %}
</ul>
{% endfor %}
```
Then the result is:
> Group 1
> - Thing 1
> - Thing 2
> - Thing 3
> Group 2
> - Piece 1
> - Piece 2
> - Piece 3
> Group 3
> - Widget 1
> - Widget 2
> - Widget 3
Or if you use `{{ site.data.samplelist.toc[0].subfolderitems[0].page }}`, you can get the value `Thing 1`

### Variables
YAML named *samplelist*:
```
something: &hello Greetings earthling!
myref: *hello
```
Markdown:
```
{{ site.data.samplelist.myref }}
```
Result:
> Greetings earthling!

## JSON
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
Plus, you can reach the data by `{% for data in site.data.fileName %}`

## CSV
[reference](https://talk.jekyllrb.com/t/accessing-specific-entry-in-a-csv-file-in-data-folder/1713/2)  
Suppose you have a CSV file like this:
```
path,filename,width,height
/assets/images,jekyll-search.png,515,446
/assets/images,jamstack-architecture.png,974,463
```
To access each item, you can access by using *Liquid*:
```
<ul>
  {% for image in site.data.images %}
    <li>
      <img src="{{ image.path | relative_url }}/{{ image.filename }}" width="{{ image.width }}" height="{{ image.height }}" />
    </li>
  {% endfor %}
</ul>
```
Or by using `where` filter:
```
{{ site.data.images | where:"filename","jekyll-search.png" }}
```
Or by using its index:
```
{{ site.data.images[0].filename }}
```

# Assets
[Official Site](https://jekyllrb.com/docs/step-by-step/07-assets/)  
Structure of assets in Jekyll site:
```
.
├── assets
|   ├── css
|   ├── images
|   └── js
...
```

You can use either CSS or Sass.  
※[Sass](https://sass-lang.com/) (Syntactically Awesome Style Sheets) is kind of extension of CSS. You can put much more variables and nestings, and also have many functions.

### Need to know Variables
[Jekyll Variables](https://jekyllrb.com/docs/variables/)

# Writing Posts
[Official Site](https://jekyllrb.com/docs/step-by-step/08-blogging/)

### Basic Descriptions
- Live in a folder called *_posts*
- There is no layouts for the `post`
  - Need to create the layout at `_layouts/post.html`
  - set the layout of `post` as `post` to use `_layouts/post.html`

Example of `_layouts/post.html`:
```
---
layout: default
---
<h1>{{ page.title }}</h1>
<p>{{ page.date | date_to_string }} - {{ page.author }}</p>

{{ content }}
```
- `date_to_string` filter makes a date into a nice format

# List Posts
- Jekyll makes posts available at `site.posts`
- File `blog.html` in your root with this code will create the posts:
```
---
layout: default
title: Blog
---
<h1>Latest Posts</h1>

<ul>
  {% for post in site.posts %}
    <li>
      <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
      <p>{{ post.excerpt }}</p>
    </li>
  {% endfor %}
</ul>
```
- `post.url` is the output path of the post
- `post.title` sets `title` in front matter
- `post.excerpt` is the first paragraph of content by default

For *yml* file,  open `_data/navigation.yml` and add an entry for the blog page.  
For example:
```
- name: Home
  link: /
- name: About
  link: /about.html
- name: Blog
  link: /blog.html 
```


# Collection
[Official Site](https://jekyllrb.com/docs/step-by-step/09-collections/)
[reference](https://learn.cloudcannon.com/jekyll/introduction-to-jekyll-collections/)

- Defining Collections happens in a file called `_config.yml` in the root (by default)

You should use Collections when:
```
+-------------------------------------+         +----------------+
| Can the things be logically grouped?|---No--->|    Use pages   |
+-------------------------------------+         +----------------+
                |
               Yes
                |
                V
+-------------------------------------+         +----------------+
|      Are they grouped by date?      |---No--->|Use a collection|
+-------------------------------------+         +----------------+
                |
               Yes
                |
                V
+-------------------------------------+
|            Use posts                |
+-------------------------------------+
```
If you add a data about something, for example cookies, you should add an image, heading and content:
```
...
<div class="cookie">
  <h2>
    <img src="https://upload.wikimedia.org/wikipedia/commons/d/d1/AfghanBiscuit.jpg" alt="Afghan">
    Afghan
  </h2>
  <p>
    An Afghan biscuit is a traditional New Zealand biscuit made from flour, butter, cornflakes, sugar and cocoa powder, topped with chocolate icing and a half walnut. The recipe[1] has a high proportion of butter, and relatively low sugar, and no leavening (rising agent), giving it a soft, dense and rich texture, with crunchiness from the cornflakes, rather than from a high sugar content. The high butter content gives a soft melt-in-the-mouth texture, and the sweetness of the icing offsets the low sugar and the cocoa bitterness. The origin of the recipe and the derivation of the name are unknown, but the recipe has appeared in many editions of the influential New Zealand Edmonds Cookery Book.
  </p>
  <p>Source <a href="https://en.wikipedia.org/wiki/Afghan_biscuit">Wikipedia</a></p>
</div>
...
```
To add more cookies, you might cause some mistake if you copy and paste an existing cookies and update the content.

First, add a collections object in `_config.yml`, then under collections define the collections we want on the site:
```
collections:
  cookies:
```
Documents (the items in a collection) live in a folder in the root of the site named `_*collection_name*`, in this case it's `_cookies`.
  - Could be either **Markdown** or HTML
For the Afghan cookie, create `_cookies/afghan.md`:
```
---
title: Afghan
image_path: https://upload.wikimedia.org/wikipedia/commons/d/d1/AfghanBiscuit.jpg
---
An Afghan biscuit is a traditional New Zealand biscuit made from flour, butter, cornflakes, sugar and cocoa powder, topped with chocolate icing and a half walnut. The recipe[1] has a high proportion of butter, and relatively low sugar, and no leavening (rising agent), giving it a soft, dense and rich texture, with crunchiness from the cornflakes, rather than from a high sugar content. The high butter content gives a soft melt-in-the-mouth texture, and the sweetness of the icing offsets the low sugar and the cocoa bitterness. The origin of the recipe and the derivation of the name are unknown, but the recipe has appeared in many editions of the influential New Zealand Edmonds Cookery Book.

Source [Wikipedia](https://en.wikipedia.org/wiki/Afghan_biscuit)
```
And repeat this for the other cookies that you want to add

Create `cookies.html` and access collections with the code `site.*collection_name*`, in this case it's `site.cookies`:
```
---
layout: page
title: Cookies
---
{% for cookie in site.cookies %}
  <div class="cookie">
    <h2><img src="{{ cookie.image_path }}" alt="{{ cookie.title }}">{{ cookie.title }}</a></h2>
    {{ cookie.content }}
  </div>
{% endfor %}
```
**Remember whenever you change the** `_config.yml` **refresh the jekyll**


# Deployment
[Official Site](https://jekyllrb.com/docs/step-by-step/10-deployment/)

### Basic Descriptions
- Get the site ready for production!!!

## Gemfile
-Create `Gemfile` in the root with the following:
```
source 'https://rubygems.org'

gem 'jekyll'
```
- Run `bundle install`
  - This installs gems and creates `Gemfile.lock`
  - Want to update, run `bundle update`
- When using a `Gemfile`, run `bundle exec jekyll serve`

## Plugins
There are many [plugins](https://jekyllrb.com/docs/plugins/)

Three useful official plugins:
- [jekyll-sitemap](https://github.com/jekyll/jekyll-sitemap): creates a sitemap file to help search engines index content
- [jekyll-feed](https://github.com/jekyll/jekyll-feed): creates an [RSS](https://en.wikipedia.org/wiki/RSS) feed for your posts
- [jekyll-seo-tag](https://github.com/jekyll/jekyll-seo-tag): adds meta tags to help with SEO (Search Engine Optimization)

To use, need to add them to your `Gemfile`:
```
source 'https://rubygems.org'

gem 'jekyll'

group :jekyll_plugins do
  gem 'jekyll-sitemap'
  gem 'jekyll-feed'
  gem 'jekyll-seo-tag'
end
```
Then add these lines to `_config.yml`:
```
plugins:
  - jekyll-feed
  - jekyll-sitemap
  - jekyll-seo-tag
```
Install them by running a `bundle update`

- No need to set up `jekyll-sitemap`

- `jekyll-feed` and `jekyll-seo-tag` are needed to add tags to `_layouts/default.html`:
```
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">
    <title>{{ page.title }}</title>
    <link rel="stylesheet" href="/assets/css/styles.css">
    {% feed_meta %}
    {% seo %}
  </head>
  <body>
    {% include navigation.html %}
    {{ content }}
  </body>
</html>
```

## [Environments](https://jekyllrb.com/docs/configuration/environments/)
In the `build` (or `serve`) arguments, you can specify a Jekyll environment and value
- You can set the environment by using the `JEKYLL_ENV`

Suppose you set this conditional statement in your code:
```
{% if jekyll.environment == "production" %}
   {% include disqus.html %}
{% endif %}
```
When the `if` statement won't be run unless you specify a `production` environment in the build command like this in the therminal:
```
JEKYLL_ENV=production jekyll build
```

- The default value for `JEKYLL_ENV` is `development`
  - Any content inside `{% if jekyll.environment == "development" %}` tags will automatically run

## Deployment
Run a production build:
```
JEKYLL_ENV=production bundle exec jekyll build
```
And copy the contents of `_site` to your server
