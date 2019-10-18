References:  
[Chris Anthropic](https://www.chrisanthropic.com/blog/2016/creating-gem-based-themes-for-jekyll/)  
[Create your own Jekyll theme gem](https://ryandevelops.com/collection/2018-10-07-create-your-own-jekyll-theme-gem) 


# Install as Gem Theme
Jekyll requires Ruby so make sure Ruby is installed before you begin.

### Start a New Site
- Install Jekyll and Bundler
  - `gem install bundler`
- Create a New Site
  - `jekyl new mysite`
- Move into that directory
  - `cd mysite`
- Install Required Gems
  - `bundle install`
- Verify
  - Run `jekyll serve`
  - Browse to [http://localhost:4000](http://localhost:4000)

## Disable the Default Theme
**Be aware, this is only from [Chris Anthropic](https://www.chrisanthropic.com/blog/2016/creating-gem-based-themes-for-jekyll/), not from [Create your own Jekyll theme gem](https://ryandevelops.com/collection/2018-10-07-create-your-own-jekyll-theme-gem).**  

- Delete the line `gem "minima"`
- Tell Jekyll not to use a Theme
  - Open `_config.yml` and delete the line `theme: miniam`
- Do NOT import Any Theme css
  - Open your `css/style.css` and delete the line `@import "minima;"`

## Create Your Theme
- Create the `_Layouts`, `_includes`, and `_sass` directories.
  - This command will create the directories that you need: `jekyll new-theme YourThemeName`
    - `_includes` folder: for reusable theme partials
    - `_layouts` folder: keep the main template files such as **default post layout**
    - `assets` folder: for keeping any images, graphics, etc that you'll want to include in your gem and for import your Sass files
    - `_sass` folder: where your style partials will go
    - `Gemfile`: will point to your `.gemspec` file
    - `README.md`: documentation for your theme where you'll provide including how to install and configure the gem
  - Need to edit `spec.summary` and `spec.hompage` values in order for you to successfully run the `bundle exec jekyll serve --watch` command
- Design your theme
  - Might create a *Demo site* that documents the theme itself and shows all of its features
- Verify
  - Run `jekyll serve`
  - Browse to [http://localhost:4000](http://localhost:4000)

## Create a config file
Create an example `config.yml` file for make it easy for someone downloading your gem to get setup  
Example:
```
title: Dragyong
email: example@example.com
description: >
  This is the Jekyll Theme.
baseurl: ""
url: "https://jekyll-theme-collider.netlify.com"
hosted_url: ""
github_username: ""
linked_in_profile: ""
full_name: Yongsang Park
user_description: Software Engineer
disqus:
  shortname: jekyll-theme-collider-netlify-com
```
You can simply edit the `config.yml` and can change all the variables. Here's the layout that you can refer:
```
<p>{{ site.full_name }}</p>
```
Then it will gives you `<p>Yongsang Park</p>`.

## Create Your Gem
**Be aware, this is only from [Chris Anthropic](https://www.chrisanthropic.com/blog/2016/creating-gem-based-themes-for-jekyll/), not from [Create your own Jekyll theme gem](https://ryandevelops.com/collection/2018-10-07-create-your-own-jekyll-theme-gem).**

Once you are simply ready to test it or happy to go forward, then it's time to create your gem.
- open the `YourThemeName.gemspec` file and edit the spec.files command (at a minimum) since the current version creates imcomplete and sometimes empty Gems.  
**Replace this line**:
```
spec.files = `git ls-files -z`.split("\x0").select { |f| 
  f.match(%r{^(_layouts|_includes|_sass|LICENSE|README)/i}) }
```
**Within this line**:
```
spec.files = `git ls-files -z`.split("\x0").select do |f|
  f.match(%r{^(_(includes|layouts|sass)/|(LICENSE|README)((\.(txt|md|markdown)|$)))}i)
end
```
- Run `gem build YourThemeName.gemspec`

## Test Your Gem
Create a *brand new Jekyll site* and then tell it to *use your local Gem file*.

### Start a New Site
*Same as initial point*
- Install Jekyll and Bundler
  - `gem install bundler`
- Create a New Site
  - `Jekyll new mysite`
- Move into that directory
  - `cd mysite`
- Install Required Gems
  - `bundle install`
- Verify
  - Run `jekyll serve`
  - Browse to [http://localhost:4000](http://localhost:4000)

*More information to test your Gem*  
- Set your Theme
  - Open `Gemfile` and add the line `gem YourTheme, :path => ""`
    - By default it checks Rubygems.org for the Gem and downloads it, but with `:path => ""` we're telling it to use the local version of the gem
  - Run `bundle install`
- Tell Jekyll to use YourTheme
  - Open `_config.yml` and add the line `theme: YourTheme` to this
- Import the Theme CSS
  - Open your `css/style.css` and add the line `@import YourTheme;`
    - The name of the file you `@import` is whatever the **name of your main** `.scss` file in your theme's `_sass` directory

## Push Your Gem
You can optionally share it with the world. It requires you to sign up with [Rubygems.org](https://rubygems.org)

- Build the gem: `gem build YourTheme.gemspec`
  - Then a name of the file in your root directory is `YourTheme.gem'
- Run `gem push YourTheme.gem`
- Enter your Rubygems.org email and password when prompted

If you want to pull it back down:
`gem yank YourTheme -v VersionNumber`

## Push Your Next Gem Version
- In your `.gemspec` file, change the `spec.version` configuration to the desired version number.
  - You can refer this [guide](https://guides.rubygems.org/patterns/#semantic-versioning) to help determine what your version number should be.
- Run `gem build YourTheme.gemspce` again for your next gem version
- Run `gem push YourTheme.gem` again

# Pick up a theme
- [jamstackthemes.dev](https://jamstackthemes.dev/ssg/jekyll/)
- [jekyllthemes.org](http://jekyllthemes.org/)
- [jekyllthemes.io](https://jekyllthemes.io/)
