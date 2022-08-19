A Short Guide to Markdown
======

* What is Markdown?
  * Plain text format
  * easy to read, write, learn
  * easy to parse/convert to other formats
  * lots of supports and extensions

Using Markdown Tools
-------    
Basic Span Elements
-------
* single underscore both sides _italics_

* double stars or double underscores on both sides are **bold** __bold here__

* to bold and italics simultaneously put 3 asterisks or underscores before and after a word or phrase. Like this:

>>>***I'm bold and italic at the same time***

Paragraphs and headers
-----
* tabs will cause blocks of writing like this:

  hello. This block was "tabbed". Hit tab on line to get this

> if you want blockquotes like this just add a ">" in front of line

>or if you want block quotes on multiple lines or paragraphs and dont want a break in your blockquotes like the one above, just continue with ">" at the front of each line.
>like this

>or if you want your blockquotes to be nested, add ">>" infront of the line that is going to be nested.
>>Like this one.   
>>then continue putting ">>" infront to remain on the same level

> ## You can add other elements like "##" after ">" to put headers within your blockquotes


* If you're writing a paragrah and you want to start a new one, just type double space after the last sentence of the paragraph then enter. Like this.  
The above paragraph was seperated with double space enter.

* Eqaul signs underneath the direct above line will render the direct above line as an h1 tag. Like this:

>>>Hello I'm a h1 header because I have eqaul sign directly below me.
>>>==========

* Dashes underneath the will render an h2 tag. Like this:

>>>Hello! I'm a h2 header because I have dashes under me.
>>>------

* atx notation is where you put hashtag at beginning of line to reduce headers. Up to 6 hashtags or 6 lower levels. Like this:

>>># I'm level 1 h1

>>>## I'm level 2 h2

>>>### I'm level 3 h3

>>>#### I'm level 4 h4

>>>##### I'm level 5 h5

>>>###### I'm level 6 h6

## Ordered Lists
* to have an ordered list, add numbers followed by periods. The numbers can be consecutive to render them in order.  
>> 1. hello  
>> 2. hello  
>> 3. hello
*  all the list items can start with "1" and it would still render consecutive numbers. Like this:  
>>> "1. hello"  
>>> "1. hello"  
>>> "1. hello"  
>>>The above would still render into this:  
>> "1. hello"  
>> "2. hello"  
>> "3. hello"  

## Unordered Lists  
* unordered lists can be created by adding dashes, asterisks, or plus signs followed by a space to. Like this:
>>> * I know the format of this document already uses
>>> * unordered lists. But I just had to create an example to
>>> * for continuity
* you can also indent before the unordered list to create a nested item. Like this:
>>> * this is level 1 item
>>>     * this is level 2 item  
* code blocks can be added to a list by adding 8 spaces or two tabs to line. Like this  

        <html>
            <head>
                <title>This is a code block</title>
            </head>
## Lists
1. you can render unordered lists within an ordered lists like this
    * unordered list within an ordered list
        1. an ordered list within an ordered lists
            * this can go on and on

## Images
* To add images add the following syntax:
* >>> \![Heisenberg]\(https://www.seekpng.com/png/small/777-7770676_walter-white-clipart-heisenberg-breaking-bad-no-background.png)
* you get this:
* ![Heisenberg](https://www.seekpng.com/png/small/777-7770676_walter-white-clipart-heisenberg-breaking-bad-no-background.png)
* also note that the URI between the parenthesis can also be file path to you image store on you device

## Code
* to denote a word or phrase as code, enclose it with backticks:
>>> \`backticks surround me\`
>>> gets you this:  

>>>`backticks surround me`
* you can't really tell that the above line is turned into a code but I can assure you it is. Just look closely

* ticks within ticks could cause a problem. No worries, just wrap the conaining ticks with double ticks. Like this:
>>>> \`\`Putting double ticks on the outside to allow the inside ticks \'tick\' to maintain its original syntax\`\`  

* The above code would render like this:  
>>>> ``Putting double ticks on the outside to allow the inside ticks `tick` to maintain its original syntax``

# Code Blocks & Fenced
* to create code blocks, put four spaces or an indent at the beginning of line. Like this:  

        <html>
            <head>
                <body>
                </body>
            </head>
        </html>
* fenced code blocks can be created by adding 3 back ticks (```) before and after your code. Like this:  
    ```
    {
        "Is markdown cool": "yes",
        "List your favorite feature": [
            "code blocks", 
            "fenced code blocks",
            "headers", 
            "image"
        ],
        "Do you love learning": "yes"
    }
    ```
## Horizontal rules
* horizontal rules allow you to artificially add lines between your paragraphs or content
* You can create an horizontal rule by use 3 asterisks, 3 dashes or 3 underscores to create this effect. Like this:

***

* make sure you add spaces above and below your horizontal rules. Not doing so may cause a different affect.

## Links 
* unlike the image feature, links doesn't lead with a exclaimation point "!". And takes two parameters. 
* first parameter takes a link description enclosed by square brackets
* second parameter takes the URI enclosed with parenthesis
* Like this  
>>> \[Breaking Bad\]\(https://www.imdb.com/title/tt0903747/\)

* Which renders this:  
>>>[Breaking Bad](https://www.imdb.com/title/tt0903747/)  

* You can also add a title upon mouse hover over link. Go ahead and hover over link:
>>>[Breaking Bad](https://www.imdb.com/title/tt0903747/ "Breaking Bad is the coolest show")

## URLs and Emails
* you can add links to your emails by simply enclosing them with brackets:
>>> \<`https://www.imdb.com/title/tt0903747/`\>
>>> \<`markdowniscool@markdowniscool.com`\>

* which renders like this:
>>> <https://www.imdb.com/title/tt0903747/>
>>> <markdowniscool@markdowniscool.com>




    
