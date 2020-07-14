---
permalink: /style/
title: "Style Guide"
classes: wide
author_profile: true
---

# Buttons
Check out [Pure](https://purecss.io/buttons/) for explanations for buttons.
<button class="button">Green</button>

<a class="pure-button" href="#">A Pure Button</a>

`<a class="pure-button" href="#">A Pure Button</a>`

<a class="pure-button pure-button-primary" href="#">A Primary Button</a>

`<a class="pure-button pure-button-primary" href="#">A Primary Button</a>`

# Alert Notice
<div class="alert">Example here</div>
<div class="vermillion">Vermillion</div>
<div class="purple">Purple</div>
<div class="yellow">Yellow</div>


# Anchors
We will want to make anchors to cross link to specific places in notes. 

[Link to On-Mutation](https://listed.to/@joerodgers/16188/notes-on-the-viral-aspects-of-language#on-mutation).

Essentially you will place an anchor `<a name="on-mutation">On Mutation</a>` in the document, then you can navigate to that place in the document by adding `#on-mutation` to the end of the page URL. 

`https://listed.to/@joerodgers/16188/notes-on-the-viral-aspects-of-language#on-mutation`

```
<a name="on-mutation">On Mutation</a>
```

# Headings

# H1
## H2
### H3
#### H4
##### H5
###### H6

```
# H1
## H2
### H3
#### H4
##### H5
###### H6
```
# Linebreak
Line break is typed as \<br />\. There is a line break after this sentence.

<br />

```
<br />
```

# Text
*italic*
**bold**
***bold-italic***
[link](https://example.com)

```
*italic*
**bold**
***bold-italic***
[link](https://example.com)
```

## Strikethrough
~~deleted words~~

```
~~deleted words~~
```

## Highlights
==oooh fancy==

```
==oooh fancy==
```

## Type WYSIWYG
\*literally\*

```
\*literally\*
```

## Superscript
Oxygen is O<sup>2</sup>

```
Oxygen is O<sup>2</sup>
```

## Subscript
Plants need CO<sub>2</sub>

```
Plants need CO<sub>2</sub>
```

# Center Text
Use the \<center\> tag

<center>example centered</center>

```
<center>example centered</center>
```

# Small Text
Use the \<small\> tag if you want to make text small. I like to use this with center for image notes

<small>small text</small>

```
<small>small text</small>
```


## Text colors and fonts
In his beard lived three <span style="color:red">cardinals</span>.

I am in <span style="font-family:Papyrus; font-size:4em;">LOVE!</span>


```
In his beard lived three <span style="color:red">cardinals</span>.

I am in <span style="font-family:Papyrus; font-size:4em;">LOVE!</span>
```

# Lists
* Milk
* Bread
    * Wholegrain
* Butter

1. Tidy the kitchen
2. Prepare ingredients
3. Cook delicious things

```
* Milk
* Bread
    * Wholegrain
* Butter

1. Tidy the kitchen
2. Prepare ingredients
3. Cook delicious things
```

***

# Links
[I'm an inline-style link](https://www.google.com)

```
[I'm an inline-style link](https://www.google.com)
```

[I'm an inline-style link with title](https://www.google.com "Google's Homepage")

```
[I'm an inline-style link with title](https://www.google.com "Google's Homepage")
```

[I'm a reference-style link][Arbitrary case-insensitive reference text]

```
[I'm a reference-style link][Arbitrary case-insensitive reference text]
```

[I'm a relative reference to a repository file](../blob/master/LICENSE)

```
[I'm a relative reference to a repository file](../blob/master/LICENSE)
```

[You can use numbers for reference-style link definitions][xxx]

```
[You can use numbers for reference-style link definitions][xxx]
```

Or leave it empty and use the [link text itself].

```
Or leave it empty and use the [link text itself].
```


URLs and URLs in angle brackets will automatically get turned into links.  http://www.example.com or <http://www.example.com> and sometimes  example.com (but not on Github, for example).

```
URLs and URLs in angle brackets will automatically get turned into links.  http://www.example.com or <http://www.example.com> and sometimes  example.com (but not on Github, for example).
```

Some text to show that the reference links can follow later.

[arbitrary case-insensitive reference text]: https://www.mozilla.org
[xxx]: http://slashdot.org
[link text itself]: http://www.reddit.com

The item below creates references links.

```
[arbitrary case-insensitive reference text]: https://www.mozilla.org
[xxx]: http://slashdot.org
[link text itself]: http://www.reddit.com
```

***

# Quotes

> To be or not to **be**, 
> > that is the [question]().

> Blockquotes are very handy in email to emulate reply text.
> This line is part of the same quote.

Quote break.

> This is a very long line that will still be quoted properly when it wraps. Oh boy let's keep writing to make sure this is long enough to actually wrap for everyone. Oh, you can *put* **Markdown** into a blockquote. 


```
> To be or not to **be**, 
> > that is the [question]().

> Blockquotes are very handy in email to emulate reply text.
> This line is part of the same quote.

Quote break.

> This is a very long line that will still be quoted properly when it wraps. Oh boy let's keep writing to make sure this is long enough to actually wrap for everyone. Oh, you can *put* **Markdown** into a blockquote. 

```
***

# Images

## Standard Image

![](https://joerodgers.keybase.pub/colorful.png)

```
![](https://joerodgers.keybase.pub/colorful.png)
```

## Float image and square it
<img src="https://joerodgers.keybase.pub/colorful.png" alt="Avatar" style="float: right; margin-right: 10px;" /> I am passionate about Bitcoin and its developments worldwide, particularly from a monetary policy and libertarian perspective. I strongly believe in education and onboarding via content curation and I enjoy the creative process of doing so.

<br />

<br />

<br />

<br />

```
<img src="https://joerodgers.keybase.pub/colorful.png" alt="Avatar" style="float: right; margin-right: 10px;" /> I am passionate about Bitcoin and its developments worldwide, particularly from a monetary policy and libertarian perspective. I strongly believe in education and onboarding via content curation and I enjoy the creative process of doing so.
```

## Center Image using class attribute from CSS with HTML

<div style="text-align:center"><a href="https://twitter.com/ClancyRodgers"><img src="https://i.imgur.com/LkxA4Zx.png" alt="Make Guns Not War" class="center"></a></div>

```
<div style="text-align:center"><a href="https://twitter.com/ClancyRodgers"><img src="https://i.imgur.com/LkxA4Zx.png" alt="Make Guns Not War" class="center"></a></div>
```


## Float image with html attributes
Image is floating right with a margin. 
<img src="https://i.imgur.com/NZLcX8V.png" alt="Sepia toned line drawing of Yggdrasill" style="float: right; margin-right: 10px;">

```
<img src="https://i.imgur.com/NZLcX8V.png" alt="Sepia toned line drawing of Yggdrasill" style="float: right; margin-right: 10px;">
```

# Logos

Here's our logo (hover to see the title text):

Inline-style: 
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

Reference-style: 
![alt text][logo]

[logo]: https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 2"

```
Here's our logo (hover to see the title text):

Inline-style: 
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

Reference-style: 
![alt text][logo]

[logo]: https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 2"
```

***

# Code

Some text with an inline `code` snippet


or here is an example of a code block:

```
.my-link {
        text-decoration: underline;
    }
```

```javascript
var s = "JavaScript syntax highlighting";
alert(s);
```
 
```python
s = "Python syntax highlighting"
print s
```
 
```
No language indicated, so no syntax highlighting. 
But let's throw in a <b>tag</b>.
```


***


# Tables

Colons can be used to align columns.

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

There must be at least 3 dashes separating each header cell.
The outer pipes (|) are optional, and you don't need to make the 
raw Markdown line up prettily. You can also use inline Markdown.

Markdown | Less | Pretty
:--- | :---: | ---:
*Left* | `center` | **right**
1 | 2 | 3

insert text here

| Syntax      | [Description](#) | Test Text     |
| :---        |    :----:   |          ---: |
| Header      | Title       | Here's this   |
| Paragraph   | Text        | And more      |

```
Colons can be used to align columns.

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

There must be at least 3 dashes separating each header cell.
The outer pipes (|) are optional, and you don't need to make the 
raw Markdown line up prettily. You can also use inline Markdown.

Markdown | Less | Pretty
:--- | :---: | ---:
*Left* | `center` | **right**
1 | 2 | 3

insert text here

| Syntax      | [Description](#) | Test Text     |
| :---        |    :----:   |          ---: |
| Header      | Title       | Here's this   |
| Paragraph   | Text        | And more      |
```

***

# Task Lists
- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media

```
- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media
```


# References

The quick brown fox[^1], jumped over the lazy dog[^2].

[^1]: ["Wikipedia: Fox"](https://en.wikipedia.org/wiki/Fox)
[^2]:  ["Wikipedia: Dog"](https://en.wikipedia.org/wiki/Dog)

# Definitions with link
The quick brown [fox][1], jumped over the lazy [dog][2].

[1]: https://en.wikipedia.org/wiki/Fox "Wikipedia: Fox"
[2]: https://en.wikipedia.org/wiki/Dog "Wikipedia: Dog"

```
The quick brown fox[^1], jumped over the lazy dog[^2].

[^1]: ["Wikipedia: Fox"](https://en.wikipedia.org/wiki/Fox)
[^2]:  ["Wikipedia: Dog"](https://en.wikipedia.org/wiki/Dog)

# Definitions with link
The quick brown [fox][1], jumped over the lazy [dog][2].

[1]: https://en.wikipedia.org/wiki/Fox "Wikipedia: Fox"
[2]: https://en.wikipedia.org/wiki/Dog "Wikipedia: Dog"
```