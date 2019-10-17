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
- Delete the line `gem "minima"`
- Tell Jekyll not to use a Theme
  - Open `_config.yml` and delete the line `theme: miniam`
- Do NOT import Any Theme css
  - Open your `css/style.css` and delete the line `@import "minima;"`

## Create Your Theme
- Create the `_Layouts`, `_includes`, and `_sass` directories.
  - `jekyll new-theme YourThemeName`
  - Copy and paste all of the contents of the *YourThemeName* directory into the root of your Jekyll site.
  - Delete the (now empty) *YourThemeName* directory
- Design your theme
  - Might create a *Demo site* that documents the theme itself and shows all of its features
- Verify
  - Run `jekyll serve`
  - Browse to [http://localhost:4000](http://localhost:4000)

## Create Your Gem
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
You can optionally share it with the world. It only requires you to sign up with [Rubygems.org](https://rubygems.org)

- Run `gem push YourTheme.gem`
- Enter your Rubygems.org email and password when prompted

If you want to pull it back down:
`gem yank YourTheme -v VersionNumber`




