# Jekyll Install Procedure (Ubuntu)
- The following commends has been tested on the **Ubuntu 18.04.3 LTS** environment
  (architecture: AMD64).
- For the other environments, please use this document as a reference, 
  but you should **change some commends** (e.g. `apt-get install`) for your own environment.
- All the information has been created based on the quickstart guide on Jekyll's official website  
  URL: https://jekyllrb.com/docs/

## Requirements
- **Ruby** (2.4.0 or above)  
  Checks the installed ruby version by using `ruby -v`
- **RubyGems**  
  Check the installation and running of RubyGems by using `gem -v`
- **GCC** and **Make**  
  Check installation of compilers and make by using following codes: `gcc -v`, `g++ - v`, `make - v`</br>  

For the whom missing any requirements, you should **install the dependencies**.
1. **Update the Package Index** (Optional)  
   Make APT package index, containing information of available packages, have latest information.  
   If you just installed Ubuntu, or have been a while update the package index, I recommend you to update it before we use other apt commends.  
   `sudo apt update`  
   Note that it requries root permission
2. **Upgrade Packages** (Optional)  
   Get all package updates (Require root permission)
   `sudo apt upgrade`
3. **Install Dependencies**  
   Before Install Jekyll, we should installed required dependencies.  
   It contains **ruby**, **GCC**, and **Make**. It requires root permission  
   `sudo apt install ruby-full build-essential zlib1g-dev`  
   Installing three packages, named **ruby-full**, **build-essential**, **zlib1g-dev**.
4. Setting up RubyGems **environment variables**  
   Set up a gem installation directory for user's account.  
   Adding environment variable to `~/.bashrc` file in order to configure the gem installation path.  

   ```
   echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
   echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
   echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
   source ~/.bashrc
   ```

## Install Jekyll by RubyGems
Installation of Jekyll is conducted by RubyGems  
`gem install jekyll'  
'gem install bundler -v 1.16.2`  
Takes a lots of time, so be patient

## Test
After install, test whether the jekyll has been correctly installed or not
1. Check version  
   `jekyll -v`  
2. Create ne Jekyll site at `./[SITE_NAME]`  
   `jekyll new [SITE_NAME]`  
   Replace `[SITE_NAME]` to appropriate name (e.g. test)  
   Then it will initiate a jekyll site on directory named `[SITE_NAME]`. (Path = `./[SITE_NAME]`)
3. Launch the demo site
   - change working directory where the site is located  
     `cd [SITE_NAME]`
   - Build the site and make it available though the local server  
     `bundle exec jekyll serve`
4. Now, you can see the jekyll page on http://localhost:4000  
   Note that this site only can be accessed from local host.
   (Check Error_While_Installing_Jekyll.md for more detail)
