# NEWS & EVENT: Add New Posts  

For the detailed information page of each event, you can either choose to write new posts (like blogs) or link other website's link.  
Here, we are going to look how to make new posts.


## Markdown Syntax  

This website is based on Jekyll, which automatically generates HTML files from markdown(md) files.  
As the posts should be written in markdown, you need to be familiar with the basic syntaxes.
It is easy, more than LaTeX.  

Here, I provide some basic syntaxes that I frequently use, but for more guideline, please visit [GitHub's Guide](https://guides.github.com/features/mastering-markdown/).  

### Basic Syntax

#### Headers / Titles
```
# Main Title
## Second-level Title
### Third-level Title
...
###### Way up to Sixth-level Title
```

#### General Texts
```
You can just type in what you want, without using any syntax.  
Bold: Wrap the phrases with **.  
Italic: Wrap the phrases with *.  
Link: [Link To Here](URL).
Line Break: Type "  " (Two spaces) at the end of the sentence.

Example:
Isn't it so ***Simple***?? Welcome to *Markdown*.  
[**Link** to Editor's GitHub Profile](https://github.com/hyecheol123).
```
Isn't it so ***Simple***?? Welcome to *Markdown*.  
[**Link** to Editor's GitHub Profile](https://github.com/hyecheol123).  

#### Lists
```
Numbered List Example

1. One
2. Two
3. Three
5. Four (Markdown Ignores the Number, only ORDER matters)
4. Five (Markdown Ignores the Number, only ORDER matters)


Bullet Points Example

- President
- Vice President
- Cheif Technology Officer


Alternative Example for Bullet Point

- Executive Officers
  - President
  - Vice President
  - Secretary General
  - Chief Technology Officer
- Directors Committee
  - Basic Science
  - Pharmacy
```

Numbered List Example

1. One
2. Two
3. Three
5. Four (Markdown Ignores the Number, only ORDER matters)
4. Five (Markdown Ignores the Number, only ORDER matters)


Bullet Points Example

- President
- Vice President
- Cheif Technology Officer


Alternative Example for Bullet Point

- Executive Officers
  - President
  - Vice President
  - Secretary General
  - Chief Technology Officer
- Directors Committee
  - Basic Science
  - Pharmacy

#### Quote
```
Start Sentence by >

> We the People of the United States
>> All legislative Powers herein granted shall be vested in a Congress of the United States, which shall consist of a Senate and House of Representatives.
```

> We the People of the United States
>> All legislative Powers herein granted shall be vested in a Congress of the United States, which shall consist of a Senate and House of Representatives.

#### Image
```
![Alt Message](Image Link "Image Title")

Example: ![KSEA Wisconsin](https://raw.githubusercontent.com/hyecheol123/KSEAWeb-Jekyll/master/assets/KSEA_group_image.jpg "KSEA Wisconsin")
```

![KSEA Wisconsin](https://raw.githubusercontent.com/hyecheol123/KSEAWeb-Jekyll/master/assets/KSEA_group_image.jpg "KSEA Wisconsin")


## Writing Post
- Post file located in `/_posts/`
- Post files' name must follow this naming convention  
  `YYYY-MM-DD-Title_Text.md`
- At the beginning of the post, it needs to include specific header starts and ends with `---` for basic information of the post.
  ```
  ---
  layout: post
  title: "Title"
  location: "Where the events happens"
  timestamp: "Jun. 18. 2020 (Thu)"
  author: "Author's Name"
  ---
  ```
  - You can Modify `title`, `location`, `timestamp`, and `author`, but **`layout` should be `post`**.
  - More Examples of the Post could be found on [_posts directory of Code Repository](https://github.com/hyecheol123/KSEAWeb-Jekyll/tree/master/_posts).  
    Click `Raw` after you navigate to the file you want to see.  
    GitHub Automatically synthesize markdown file to HTML.
- After the header, start write the contents (body) of the post using Markdown Syntax.