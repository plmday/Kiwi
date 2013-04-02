#Kiwi Wiki

Kiwi is a light-weight [Wiki markup
language](http://c2.com/cgi/wiki?WikiMarkupLanguage).  It is intended to be
*simple*, *elegant* and *intuitive*.

##1. Motivation

Every Wiki markup language in use today sucks!  Their syntax is *neither*
elegant *nor* intuitive.  Kiwi means to remedy this.

##2. Kiwi Syntax

The syntax is inspired by both the [Creole
1.0](http://www.wikicreole.org/wiki/Creole1.0) Wiki standard and the [txt2tag
markup](http://txt2tags.org/markup.html).  It is still in evolution.

###2.1. Kiwi Headings

The supported level is up to 6.

####2.1.1. Kiwi Unordered Headings

```
=Unordered Heading 1
```

effects

#Unordered Heading 1

```
==Unordered Heading 2
```

effects

##Unordered Heading 2

```
===Unordered Heading 3
```

effects

###Unordered Heading 3

####2.1.2. Kiwi Ordered Headings

```
#Ordered Heading 1
```

effects

#1. Ordered Heading 1

```
##Ordered Heading 2
```

effects

##1.1. Ordered Heading 2

```
###Ordered Heading 3
```

effects

###1.1.1. Ordered Heading 3

For a heading to be recognized, it must be surrounded by (at least) two empty
lines unless it appears in the first line, in which case, only one empty line
(or more) following it is required.

###2.2. Kiwi Lists

The supported level is up to 6.

The syntax for unordered and ordered lists matches that for unordered and
ordered headings.  The former defines smaller block structures, so `-` and `+`
are used; the latter defines *larger* document structures, so `=` and `#` are
used. 

####2.2.1. Kiwi Unordered Lists

```
- Red
-- Green
--- Blue
```

effects

* Red
    * Green
        * Blue

####2.2.2. Kiwi Ordered Lists

```
+ Red
++ Green
+++ Blue
```

effects

1. Red
    1. Green
        1. blue

####2.2.3. Kiwi Definition Lists

```
Red
: a color
Green
: a color
Blue
: a color
```

effects

<dl>
 <dt>Red</dt>
 <dd>a color</dd>
 <dt>Green</dt>
 <dd>a color</dd>
 <dt>Blue</dt>
 <dd>a color</dd>
</dl>

###2.3. Kiwi Paragraph

```
A paragraph consists of one or more lines.

A blank line ends a paragraph.
```

effects

A paragraph consists of one or more lines.

A blank line ends a paragraph.

###2.4. Kiwi Code Block

The simple requirement is that the symbols chosen should remind of code.
Braces are probably the most-used symbols for code blocks.

```
{
code block
}
```

effects

```
code block
```

Symbols like <tt>```</tt> or <tt>'''</tt> are not chosen as they sit too much
high above the baseline, which makes it hard for the eyes to isolate them from
adjacent lines.  Compare the following syntax chosen by Markdown with the
above syntax:

    ```
    code block
    ```

By default, a code block is indented one level to the right.  To indent more
levels, use more braces.  For example, `{{` and `}}` will indent the code
block two levels to the right.

###2.5. Kiwi Math Formula Block

```
[
E = mc^2
]
```

###2.6. Kiwi Quotation Block

```
|
Life itself is a quotation.  --- Jorge Luis Borges
|
```

effects

<blockquote>
Life itself is a quotation.  --- Jorge Luis Borges
</blockquote>

###2.7. Kiwi Indented Text Block

```
>
This text is indented.
>
```

###2.8. Kiwi Text

The markup syntax for font faces all use *linear* symbols.  These symbols
should as much as possible suggest the look the surrounded text will be after
being formatted.

####2.8.1. Kiwi Bold Text

```
|bold text|
```

effects

**bold text**

####2.8.2. Kiwi Emphasized Text

```
/emphasized text/
```

effects

*emphasized text*

####2.8.3. Kiwi Underlined Text

```
_underlined text_
```

effects

<u>underlined text</u>

####2.8.4. Kiwi Strikeout Text

```
-strikeout text-
```

effects

<strike>strikeout text</strike>

When using strikeouts, it is recommended leaving at least one space at both
the begining and the end, because a hyphen `-` is usually used to form a
compound word.  Text like the following should not be formatted as strikeout.

```
A compound-word is not a pseudo-word.
```

But text as follows should.

```
A compound -word is not a pseudo- word.
```

####2.8.5. Kiwi Inline Code

```
{code piece} in text
```

effects

`code piece` in text

####2.8.6. Kiwi Inline Math Formula

```
[E = mc^2]
```

####2.8.7. Kiwi Superscript

```
Super^script
```

effects

Super<sup>script</sup>

####2.8.8. Kiwi Subscript

```
Sub_script
```

effects

Sub<sub>script</sub>

###2.9. Kiwi Horizontal Rules

The number of `-` is required to be greater than 6, to distinguish it from
nested bullets for unordered lists.

```
-------
```

-------

###2.10. Kiwi Cross-References

####2.10.1. Kiwi Labels

```
Here < : label>
```

####2.10.2. Kiwi References

```
<_ : label>
```

```
<There : label>
```

###2.11. Kiwi Hyper-References

```
<_ | README.md>
```

```
<README | README.md>
```

or

```
<README | ./README.md>
```

or

```
<README | ../Kiwi/README.md>
```

or

```
<README | file:///home/day/Kiwi/README.md>
```

or


```
<README | file://dreams.oz/home/day/Kiwi/README.md>
```

or

```
<README | ftp://dreams.oz/home/day/Kiwi/README.md>
```

or

```
<Kiwi | http://github.com/plmday/Kiwi>
```

or

```
<Email me | day@dreams.oz>
```

###2.12. Kiwi File Inclusion

####2.12.1. Kiwi Text File Inclusion

```
<_ ! README.md>
```

####2.12.2. Kiwi Image File Inclusion

```
<Caption ! image.ext>
```

