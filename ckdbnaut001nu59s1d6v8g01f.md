## Trick to write CSS & HTML 100x Faster

### Hello and Welcome

>  What if I told you there is a way to write CSS & HTML 100x Faster !    
 trust me this is wizardry.

Web-designers are constantly on the hunt for tools to help reduce the time . One of the most time-consuming aspects of writing clean web interface has always been writing CSS & HTML.
While pre-coded templates can save time during the development process, how can web-designers code more efficiently from scratch?

>  If you're an SEO or a Front End Web Developer or even a Full Stack Developer, or someone who wants to learn HTML, CSS and implement it quick...     
here I present to you the art of  [Emmet](https://emmet.io/) 

### So what is Emmet ?
Emmet is a free add-on for your text editor that allows you to type shortcuts that are then expanded into full pieces of code. By using Emmet, web-designers type less, saving both keystrokes and time when  [building a websites](https://bhagesh-codebeast.github.io/Data_Cyclopes/) . Also, relying on Emmet’s autocompletion means fewer typos and missing tags, leading to more robust websites.

Emmet is available for a variety of  text editors and is built right into  [Visual Studio Code](https://code.visualstudio.com/)  & Vim, and can be downloaded as a plugin for Atom, Sublime, Eclipse e.t.c.

### Let’s stop the litany and learn in practice.

**Note :** For this tutorial, we’re going to be using VS Code, since Emmet is already built right in. If you want to follow along in another supported IDE, check out the Emmet  [downloads page](https://emmet.io/download/)  to install it.

1. Boilerplate HTML structure (!)
---
Just write an exclamation (!) in your file and hit **ENTER**.

```
!
```
Output : 

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
``` 
> oh.... no need to thank me.

2. Building Elements (>)
---
Simply type in the tag name or tag names seperated by greater-than (>) sign.

```
#Single tag
div

#Nested tags
div>ul>li

```
Output : 
```
#Single tag
<div> </div>

#Nested tags
<div>
    <ul>
        <li></li>
    </ul>
</div>
``` 
 > I have a feeling you've **mastered** it already just by looking at this code snippet.

3. Siblings (+)
---
To add tags one followed by the other use plus (+) sign.
```
div+p+bq
```
Output :  
```
<div></div>
<p></p>
<blockquote></blockquote>
```

4. Climb Up (^)
---
Enables climbing of tags above tags, use caret (^) symbol.
```
div+div>p>span+em^bq
```
Output :  
```
<div></div>
<div>
    <p><span></span><em></em></p>
    <blockquote></blockquote>
</div>
```
> fun fact caret (not carrot ) is also known as circumflex symbol.

5. Multiplication (*)
---
> Let's get your skills multiplied.

Multiply any element / tag by using asterisk (*) followed by the number of times you want to replicate it.
```
ul>li*5
```
Output :  

```
<ul>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
</ul>
``` 

6. Grouping (`()`)
---
Group specific tags using braces ( ) .
```
div>(header>ul>li*2)
```
Output :  

```
<div>
    <header>
        <ul>
            <li></li>
            <li></li>
        </ul>
    </header>
</div>
``` 

7. ID (#) & Classes (.)
---
Period ( . ) sign indicates `class` while Pound ( # ) represents `id`.
```
div#header+div.page
```
Output :  

```
<div id="header"></div>
<div class="page"></div>
``` 

8. Custom attributes ([ ])
---
Place an attribute within square braces (`[attribute = ]`) to build custom attributes.
```
td[title="You're Awesome"]
```
Output :  

```
<td title="You're Awesome"></td>
``` 

9. Item Numbering ($)
---
Item name followed by a dollar sign ($) represents a single item.
```
ul>li.someitem$*5
```
Output :  
```
<ul>
    <li class="someitem1"></li>
    <li class="someitem2"></li>
    <li class="someitem3"></li>
    <li class="someitem4"></li>
    <li class="someitem5"></li>
</ul>
``` 

10. Generating a “Lorem Ipsum”
---
> For times when you are lost.

To generate random text use `lorem` followed by the number of words you wish to add.
```
div>p>h4>lorem10
```
Output :  

```
<div>
    <p>
        <h4>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Soluta, fugiat?</h4>
    </p>
</div>
``` 
## Let's mix & match :
Example:

```
article.fun>img.fun-img+h3.fun-title{title text}+h4.fun-quote>lorem8
``` 
Output :

```
<article class="fun">
    <img src="" alt="" class="fun-img">
    <h3 class="fun-title">title text</h3>
    <h4 class="fun-quote">Lorem ipsum, dolor sit amet consectetur adipisicing elit.</h4>
</article>
``` 

# BONUS
- for all the CSS beasts

```
m10 → margin:10px;
p10 → padding:10px;
d:f → display:flex;
ai:c → align-items:center;
jc:c → justify-content:center;
w:a → width:auto;
h:a → height:auto;
``` 
If you have made it so far, you're **Awesome**; 
hope this helps you in your **coding journey**.

> Support me by hitting the **subscribe** button on my **YouTube** channel  [CodeBeast](https://www.youtube.com/channel/UCHPrekRJR20NV4RxFRe6vBw)

## Keep Coding , Keep Slaying.

For some cool Digital portraits & art checkout my  [IG](https://www.instagram.com/bhagesh_artbeast/) .


%[https://www.instagram.com/p/CCdru2kDgF_/?utm_source=ig_web_copy_link]









