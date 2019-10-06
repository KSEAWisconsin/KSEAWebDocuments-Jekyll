# Error While Installing Jekyll

## Failed to build gem native extenstion
- OS: Ubuntu 18.04.3 LTS (Windows Subsystem for Linux, AMD64)

### Description
- While install Jekyll using  
  `gem install jekyll bundler`
- bundler successfully installed, but jekyll has been failed to install

### Solution
- install **ruby-dev** package  
  `apt-get install ruby-dev`  
  or  
  `apt-get install ruby[your-ruby-version]-dev`
- ruby version can be checked with this commend  
  `ruby -v`


## ERR_CONNECTION_REFUSED while trying to access from the other device
- OS: Raspbian 10 (armv7l)

### Description
- When serving jekyll page  
  `jekyll serve`  
  it runs webserver **only listening connection from localhost(127.0.0.1)**, not any other ip addresses
- Causing ERR_CONNECTION_REFUSED if we trying to access the jekyll site from other devices with machine's ip address
- Felt like it is related to the firewall setting, but the problem is that the webserver, hosting jekyll,
  **does not listen the other interface except for localhost**

### Solution
- When serving jekyll, use option `--host`  
  `jekyll serve --host=0.0.0.0`  
  which means the webserver **will listen all available interface**
- Can add setting `host: 0.0.0.0` to `_config.yml` of jekyll website
- [Reference from StackOverflow](https://stackoverflow.com/questions/16608466/connect-to-a-locally-built-jekyll-server-using-mobile-devices-in-the-lan)
