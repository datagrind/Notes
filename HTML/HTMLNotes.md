# Basic HTML Notes

## HTML

HyperText Markup Language
Used to give structure and meaning to and define webpage content

* text, images, audio, video, forms, etc

First language of the web

Most basic building block of a web pages

<br>
<center>~*~*~*~*~*~*~*~</center>

### Elements

All content in a HTML file is contained within different elements

This is a paragraph element:
```html
<p>Lorem ipsum kitten doughnut french press suspenders lolcat</p>
```
<br>
<center>~*~*~*~*~*~*~*~</center>

### Tags

#### Opening and Closing Tags

```html
<p>Lorem ipsum kitten doughnut french press suspenders lolcat</p>
```

In this example, ```<p>``` is the opening tag and ```</p>``` is the closing tag.

An element's tags have ```< >``` angle brackets to signify to the browser that this is HTML to be read. 

The proper syntax is in the example above.

Closing tags in HTML are always signified by a slash ```/```

<br>
<center>~*~*~*~*~*~*~*~</center>

### Attributes

```html
<p id="welcome" class="placeholder" hidden>Lorem ipsum kitten doughnut french press suspenders lolcat</p>
```

**Attributes** can be added to the opening tags of HTML elements. 

An attribute typically has a name and a value. 

Above, the attribute name is ```id```, the attribute value is the string ```"welcome"```, and they are separated by an ```=``` equals sign.

<br>

#### Boolean Attributes
```html
<p hidden>Lorem ipsum kitten doughnut french press suspenders lolcat</p>
```

Some attributes will not have values, as they have their "true" state implied by existing in the tag. 

```hidden``` is one such attribute - by being present in the tag, the element is hidden.

<br>

#### id
```id```'s attribute value must be a single string with no spaces.

The value of ```id``` must:
* Start with a letter
* use ```-``` hyphen or ```_``` underscore to connext multiple words in the string

####


<br>
<center>~*~*~*~*~*~*~*~</center>