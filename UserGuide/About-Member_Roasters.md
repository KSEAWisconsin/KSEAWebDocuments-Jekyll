# ABOUT: Fix Member Roasters

At the ABOUT page of the website, there exists a complete list of Leaders.  
The Roasters of each categories are maintained separatedly, but the lists shares the same format.

- There exists four separated roaster files.  
  Each contains information of Executive Officers(`/_data/about_xo.yml`), Directors Committee(`/_data/about_directors.yml`), YG Chapter Officers(`/_data/about_yg.yml`), and Others(`/_data/about_others.yml`).
- For each person, it requires one entry.  
  The template of each entry is:
  ```
  - person_name: # upto 15 character
    image_url: # url of the image of the person(default: <needed>)
    standing: # the standing of the person
    website_url: # url of personal website
  ```
  - `website_url` is optional, leave it blank if there's no information.
- Image of each person should be located on the `/assets/about_image`.
  - When you upload `LASTNAME_FIRSTNAME.jpg` to the folder, you should enter `/LASTNAME_FIRSTNAME.jpg` as `image_url`.