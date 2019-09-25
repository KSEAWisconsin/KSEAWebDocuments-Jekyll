# Comparing Languages

## Ruby
#### Basic Description
- A dynamic, open source programming language
- Focused on simplicity and productivity.
- Affected by Perl
- Use with Rubu on Rails, the open source web application framework
- [Official site](https://www.ruby-lang.org/en/)

#### Pros
- Easy to learn ([Ruby in 20 minutes](https://www.ruby-lang.org/en/documentation/quickstart/))
  - Natural to read
  - Easy to write
- Open source
- High productivity

#### Cons
- Slow processing time
- Not enough documentation
- Known issues with version compatibility
  + Found out that some old technical documents are not working properly on the latest version of Ruby


## Go
- When you find in google, type *Golang*

#### Basic Description
- Open source programming language
- [Official site](https://golang.org/)
- [Official Reference](https://golang.org/ref/spec)
- [GoLand, the Go Langauge IDE](https://www.jetbrains.com/go/)
- [Previous Developers Comment about Go, *Korean*](http://www.bloter.net/archives/245951)

#### Pros
- **Faster compiling speed** than C++
- Supports **Asynchronous Mechanism** like GoRoutine
- only have 25 keywords
  > break default func interface select  
  > case defer go map struct  
  > chan else goto package switch  
  > const fallthrough if range type  
  > continue for import return var  
  + Easy to learn and use
- Google tries to make applications on Android with Go language [Github site](https://github.com/golang/go/wiki/Mobile)
- Many companies are using
  - Dropbox, SoundCloud, Netflix, Docker, and so on.
- static type language
  + Checking variables type when compiled
  + Reduce possibility of making mistakes
  
#### Cons
- Does not produce Bytecode unlike Java
  - Need to compile separately like C/C++ (**Machine Dependent**)
  - As we will plan to deploy our source code, this is not a big deal for us
- Significantly slower for complicated operation than C/C++
  - Can't substitute C/C++
- Don't catch Exceptions or bugs like C (it released in the 20th century), unlike other languages.
  - C language was released in the 20th cetury, but Go was in the 21st.
  - the next version of Go will contains exception handling

## JavaScript
> The statement "Java and Javascript are similar" is same as "Car and Carpet are similar" and "Ham and Hamster are similar".

#### Basic Description
- Script Language
- Using with HTML and CSS
- All Web Browsers contain interpreter
- [Official site](https://www.javascript.com/)

#### Pros
- Low barriers to enter
  - Easy and flexible syntax and coding (Similar with Java)
- Can't substitute this language
  - The only language that browsers can understand
  
#### Cons
- Hoisting ruins codes and makes bugs.
- Very unusual language when you go deeper
> '11' + 1 -> '111'  
> '11' - 1 -> '10'

### Node.JS
#### Basic Description
- JavaScript runtime built on Chrome's V8 JavaScript engine
- [Official site](https://nodejs.org/en/)

#### Pros

#### Cons
- Need error handling
  - If not, the program will shut down
