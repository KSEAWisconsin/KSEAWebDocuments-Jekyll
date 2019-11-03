# Sass
[Official site](https://sass-lang.com/)  
[Reference](https://gomcine.tistory.com/entry/Sass-Scss-%EA%B3%B5%EB%B6%80-%EB%B0%A9%EB%B2%95)

## What is the difference between Sass and CSS?
- Sass stands for Syntactically Awesome Style Sheets
- Sass is kind of a tool for making CSS
  - Sass is a *Pre-compiler* of CSS
  - Usually compiling with **Node.js NPM**, **Ruby Gem** or **Livs Sass Compiler**

## Reason for Using Sass
- Higher productivity than CSS
- Easy to learn

## Syntax of Sass
- Original syntax, Sass
  - Filename extension: .sass
- New syntax, SCSS
  - Fully compatible with the CSS syntax
  - Filename extension: .scss
- To convert Sass to SCSS or SCSS to Sass, need to use sass-convert

## Style of Printing Sass
- Nested style: This is the **default output style**, indented according to the **degree of nesting**
- Expanded style: almost **identical** to existing CSS style
- Compact style: **Minimize space** in your code by displaying CSS rules on a **single line**
- Compressed style: Readability is not taken into account, just for minimize CSS file size as much as possible

Can determine the style by using `--style` flag on the command line

## Comment
- Inline comment: `//`
- Block comment: `/* */`

## Variable
- Using *dollar sign* (*$*)  
ex:
```
$button_color : #fff

.button1 {
    color : $button_color;
}

.button2 {
    color : $button_color;
}
```
- To make global variable, use `!global` in front of the local variables
- Can declare the default value by using `!default`
