# Jekyll

## Basic Description
- blog-aware
- **static site generator**
- Written in **Ruby**
- Official Website: https://jekyllrb.com/
- MIT license

## Feautures
- **Not** using **backend databases**
  - Takes the content
  - Renders Markdown or TExtile and **Liquid** templates
  - Produces a complete, static website ready to be served by Apache HTTP Server
- Engine behind **GitHub Pages**
  - No additional cost, **Free**
-Flexible
- Can be used in **combination with front-end frameworks**
  - Like Bootstrap
- Can be connected to cloud-based CMS software, enable to modify site content **without having to know how to code**
  - CloudCannon
  - Forestry
  - Netlify
  - Siteleaf
- Editor: Jekyll-atom --> Jekyll in Atom


## Octopress (static Contents Management Tool based on Jekyll)
- **Obsessively** designed framework for Jekyll blogging.
- **Blogging framework** for Jekyll

### Features
- Concentrated on readability and friendliness towards **mobile device**
- Support **Bootstrap**
  - Navigation bar
  - Models
  - Tooltip
  - etc.
- **Some plugins** have been just created **only for Octopress**
- Need **Ruby**, as it is based on Jekyll
- Should be comfortable running **shell commands** and familiar with the basics of **Git**

## Reason for Choosing Jekyll
1. Simple
   - No database
     - Nothing runs on the surver
   - Supports markdown for posts and pages
2. ~Light, Fast and Secure~
   - Has very less code
   - Compare to other CMS tools Using backend database server (e.g. WordPress)  
     + All of our competitors do not rely on server-side rendering, therefore, this cannot be an advantage of using Jerkyll
     [Reference](https://blog.webjeda.com/why-jekyll-over-wordpress/#1-jekyll-is-simple)
3. Lots of References (as it supported by Github Pages)
4. Officially supported by github pages
   - Might not need to build if we service on github pages (Github automatially builds the website)
5. Lots of plug-ins

## Reason for Refusing Jekyll
1. Build speed is slower than other Static Website Generators
2. Have long history, but there also exists other ***rising*** tools to make static website
3. Hard to configurate Ruby environment
   - version compatibility issue
