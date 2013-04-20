#Kiwi Wiki

Kiwi is a light-weight [Wiki markup
language](http://c2.com/cgi/wiki?WikiMarkupLanguage).  It is intended to be
*simple*, *elegant* and *intuitive*.

##1. Motivation

Every Wiki markup language in use today sucks!  Their syntax is *not* simple,
*nor* elegant, *nor* intuitive.  Kiwi means to remedy this.

##2. Kiwi Syntax

The syntax is inspired by both the [Creole
1.0](http://www.wikicreole.org/wiki/Creole1.0) Wiki standard and the [txt2tag
markup](http://txt2tags.org/markup.html).  It is still in evolution.

###2.1. Kiwi Headings

Up to six levels are supported.

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

###2.2. Kiwi List Block

The markup symbols for unordered and ordered lists match those for unordered
and ordered headings.  The former defines smaller block structures, so `-` and
`+` are used; the latter defines *larger* document structures, so `=` and `#`
are used.  However, notice the difference that sub-lists are indented to
indicate its nesting levels.  One-level indentation is made by inserting two
spaces before the markup symbol.  To indent further, simply increment the
leading spaces by two.  Up to six indentation levels (including no
indentation) are supported.  As we will see, *intuitive* indentation is a
general feature of Kiwi.

####2.2.1. Kiwi Unordered List Block

```
- Red
  - Green
    - Blue
```

effects

* Red
    * Green
        * Blue

####2.2.2. Kiwi Ordered List Block

```
+ Red
  + Green
    + Blue
```

effects

1. Red
    1. Green
        1. blue

####2.2.3. Kiwi Definition List Block

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

###2.3. Kiwi Paragraph Block

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

By default, a code block *not* indented.  To indent one level to the right,
insert one space before each line of the whole block, including the markup
symbols.

###2.5. Kiwi Formula Block

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

###2.7. Kiwi Raw Block

```
@
This text will be displayed |raw|, namely,
/as/ it is,         being _not_ formatted.
@
```

###2.8. Kiwi Target Block

```
!html
<p style="color:blue">
This target will only be handled when the file is converted to HTML.
</p>
!
```

###2.9. Kiwi Indented Block

Except the target block, any Kiwi block can be indented by simply inserting
multiple spaces of two before the whole block, including the markup symbols.
Up to six indentation levels (including no indentation) are supported.

###2.10. Kiwi Text

The markup syntax for font faces all use *linear* symbols.  These symbols
should as much as possible suggest the look the text they surround will be
after being formatted.

####2.10.1. Kiwi Bold Text

```
|bold text|
```

effects

**bold text**

####2.10.2. Kiwi Emphasized Text

```
/emphasized text/
```

effects

*emphasized text*

####2.10.3. Kiwi Underlined Text

```
_underlined text_
```

effects

<u>underlined text</u>

####2.10.4. Kiwi Strikeout Text

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

####2.10.5. Kiwi Inline Code

```
{code piece} in text
```

effects

`code piece` in text

####2.10.6. Kiwi Inline Formula

```
[E = mc^2]
```

####2.10.7. Kiwi Inline Raw Text

```
@/unformatted/ |raw| _text_@
```

effects

/unformatted/ |raw| \_text\_

####2.10.8. Kiwi Inline Target

```
!html <u>This text will only be handled when the file is converted to HTML</u>!
```

####2.10.9. Kiwi Superscript

```
Super^multiple script^
```

effects

Super<sup>multiple script</sup>

and

```
^multiple super^script
```

effects

<sup>multiple super</sup>script

####2.10.10. Kiwi Subscript

```
Sub_multiple script_
```

effects

Sub<sub>multiple script</sub>

and

```
_multiple sub_script
```

effects

<sub>multiple sub</sub>script

###2.11. Kiwi Escape Symbols

To escape a symbol, precede it with a single backslash ` \ `.  For example,
`\-` gives a hyphen -.  In particular, ` \ ` followed by a Carrige Return
forces a line break.

###2.12. Kiwi Horizontal Rules

The number of `-` is required to be greater than 4, to distinguish it from
em-dash `---`.

```
----
```

----

###2.13. Kiwi Cross-References

####2.13.1. Kiwi Labels

```
Here < : label>
```

####2.13.2. Kiwi References

```
<_ : label>
```

```
<There : label>
```

###2.14. Kiwi Hyper-References

```
<_ | README.md>
```

or

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

###2.15. Kiwi File Inclusion

####2.15.1. Kiwi Text File Inclusion

```
<_ ! README.md>
```

####2.15.2. Kiwi Image File Inclusion

```
<Caption ! image.ext>
```

