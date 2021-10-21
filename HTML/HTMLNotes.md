# Basic HTML Notes

## HTML

HyperText Markup Language
Used to give structure and meaning to and define webpage content

* text, images, audio, video, forms, etc

First language of the web

Most basic building block of a web pages

<br>


### Elements

All content in a HTML file is contained within different elements

This is a paragraph element:
```html
<p>Lorem ipsum kitten doughnut french press suspenders lolcat</p>
```
<br>


### Tags

#### Opening and Closing Tags

```html
<p>Lorem ipsum kitten doughnut french press suspenders lolcat</p>
```

In this example, ```<p>``` is the opening tag and ```</p>``` is the closing tag.  
An element's tags have ```< >``` angle brackets to signify to the browser that this is HTML to be read.
  
Closing tags in HTML are always signified by a slash ```/```

<br>


### Void Elements
A void element does not have a start and end tag. 

```html
<meta charset="utf-8"/>
or
<meta charset="utf-8">
```
A void element is contained in a single tag. This kind of element may have an optional closing slash at the end of its tag.

```<meta>```, ```<img>```, and ```<br>``` are all examples of void elements

<br>

### Attributes

```html
<p id="welcome" class="placeholder" hidden>Lorem ipsum kitten doughnut french press suspenders lolcat</p>
```

**Attributes** can be added to the opening tags of HTML elements. 

An attribute typically has a name and a value. 

Above, the attribute name is ```id```, the attribute value is the string ```"welcome"```, and they are separated by an ```=``` equals sign.

Multiple atributes can be added to an HTML element by adding a space between attribute declarations. 

<br>

#### Boolean Attributes
```html
<p hidden>Lorem ipsum kitten doughnut french press suspenders lolcat</p>
```

Some attributes will not have values, as they have their "true" state implied by existing in the tag. 

```hidden``` is one such attribute - by being present in the tag, the element is hidden. This element's existence implies its function is active. 

<br>

#### Other Attributes

Most attributes in HTML follow the following format. here, the attribute we are using as an example is ```id```.

```html
<p id="welcome">Lorem ipsum kitten doughnut french press suspenders lolcat</p>
```

```id```'s attribute value must be a single string with no spaces.

The value of ```id``` must:
* Start with a letter
* use ```-``` hyphen or ```_``` underscore to connext multiple words in the string

<br>




<br>
