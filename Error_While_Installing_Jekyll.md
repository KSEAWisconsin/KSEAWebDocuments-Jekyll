# Error While Installing Jekyll

## Failed to build gem native extenstion
- OS: Ubuntu 18.04.3 LTS (Windows Subsystem for Linux, AMD64)
### Description
- While install Jekyll using  
  `gem install jekyll bundler`
- bundler successfully installed, but jekyll has been failed to install
### Solution
- install ruby-dev package  
  `apt-get install ruby-dev`  
  or  
  `apt-get install ruby[your-ruby-version]-dev`
- ruby version can be checked with this commend  
  `ruby -v`