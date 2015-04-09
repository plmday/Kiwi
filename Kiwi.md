#Kiwi

Kiwi is a [wiki markup](https://en.wikipedia.org/wiki/Wiki_markup) language.
It aims to be *simple*, *intuitive* and *elegant*.  These three criteria,
abbreviated as *SIE*, guides the whole design of Kiwi's syntax.

##1. Motivation

Every wiki markup language in use today sucks to some degree!  Part of their
syntax is *not* simple, *nor* intuitive, *nor* elegant.  Kiwi means to remedy
this.

##2. Syntax

Kiwi's syntax is designed from scratch.  For some parts, it may borrow the
syntax directly from other [lightweight markup
languages](https://en.wikipedia.org/wiki/Lightweight_markup_language), if the
syntax indeed meets the *SIE* criteria and no better choice seems available.
Otherwise, it does not hesitate to propose new syntax.  The choice for each
syntax is justified according to the *SIE* criteria.

###2.1. Headings

Headings can go as deep as to six levels.  Structuring documents to deeper
than six levels are considered a bad style.  The examples below only
demonstrate headings to the third level.

For a heading to be recognized, it must be surrounded by (at least) two empty
lines unless it appears in the first line, in which case, only one empty line
(or more) following it is required.

####2.1.1. Unordered Headings

```
*Unordered Heading 1
```

effects

#Unordered Heading 1

```
**Unordered Heading 2
```

effects

##Unordered Heading 2

```
***Unordered Heading 3
```

effects

###Unordered Heading 3

####2.1.2. Ordered Headings

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

###2.2. Lists 

The markup symbols for unordered and ordered lists match those for unordered
and ordered headings respectively.  Lists define smaller block structure, so
`-` and `+` are used; sections define *larger* document structure, so `*` and
`#` are used.  However, notice that nesting levels of sub-lists are indicated
by indentation, whereas those of sub-sections are indicated by repeating the
markup symbols, because the latter usually are not indented in the rendered
output.

As with headings, lists can be nested up to six levels.  At each level, to
enter the next level, simply preceeding the markup symbol with two spaces.
The examples below only demonstrate lists to the third level.

####2.2.1. Unordered Lists

```
- Red
  - Green
    - Blue
```

effects

* Red
    * Green
        * Blue

####2.2.2. Ordered Lists

```
+ Red
  + Green
    + Blue
```

effects

1. Red
    1. Green
        1. blue

####2.2.3. Definition Lists

```
= Red
  a color
  = Green
    a color
    = Blue
      a color
```

effects

<dl>
 <dt>Red</dt>
 <dd>a color</dd>
 <dd>
  <dl>
   <dt>Green</dt>
   <dd>a color</dd>
   <dd>
    <dl>
     <dt>Blue</dt>
     <dd>a color</dd>
    </dl>
   </dd>
  </dl>
 </dd>
</dl>

###2.3. Paragraphs

```
A paragraph consists of one or more lines.

A blank line ends a paragraph.
```

effects

A paragraph consists of one or more lines.

A blank line ends a paragraph.

###2.4. Quotations

```
:
Life itself is a quotation.  --- Jorge Luis Borges
:
```

effects

<blockquote>
Life itself is a quotation.  --- Jorge Luis Borges
</blockquote>

Quotation marks like `'` or `"` are not chosen as in most monospaced fonts
they sit too high above the baseline, which makes it hard for the eyes to
separate them from adjacent lines.

###2.5. Formula

Depending on the target format, formula are supposed to be typeset in either
LaTeX or MathML.

```
<
E = mc^2
>
```

###2.6. Code Block

The simple requirement is that the markup symbol chosen should remind of code.
Braces, `{` and `}`, are probably the most-used symbols for code blocks.

```
{
code block
}
```

effects

```
code block
```

Symbols like <tt>`</tt> are not chosen for the same reason of being too much
above the baseline in most monospaced fonts.  Compare the following syntax
chosen by Markdown with Kiwi's syntax:

    ```
    code block
    ```

###2.7. Raw Block

The `@` symbol means *raw as is*.

```
@
This text will be displayed |raw|, namely,
/as/ it is,         being _not_ formatted.
@
```

###2.8. Target Block

A target block should *alert* someone!

```
!
<p style="color:blue">
This target will only be handled when the file is converted to HTML.
</p>
!
```

###2.9. Indentation

By default, *no* Kiwi block is indented in the formatted output, including
those that are typically so, like lists.  To indent a Kiwi block, insert
multiple spaces of two before the whole block, including the markup symbols.
Except the target block, any Kiwi block can be indented this way.  As usual,
indentation can go as deep as to six levels.

###2.10. Text

Most of the markup syntax for text use *linear* symbols.  These symbols are
chosen to suggest as much as possible the look of the text they marked up
after being formatted.

####2.10.1. Bold Text

```
|bold text|
```

effects

**bold text**

####2.10.2. Emphasized Text

```
/emphasized text/
```

effects

*emphasized text*

####2.10.3. Underlined Text

```
_underlined text_
```

effects

<u>underlined text</u>

####2.10.4. Strikeout Text

```
-strikeout text-
```

effects

~~strikeout text~~

When using strikeouts, it is required to leave at least one space at both
ends, because a hyphen `-` is usually used to form a compound word.  Text like
the following should not be formatted as strikeout.

```
A compound-word is not a pseudo-word.
```

But text as follows should.

```
A compound -word is not a pseudo- word.
```

In case of uncertainty, escape the hyphen.

####2.10.5. Superscript

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

####2.10.6. Subscript

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

####2.10.7. Inline Formula

```
[E = mc^2]
```

####2.10.8. Inline Code

```
{code piece} in text
```

effects

`code piece` in text

####2.10.9. Inline Raw

```
@/unformatted/ |raw| _text_@
```

effects

/unformatted/ |raw| \_text\_

####2.10.10. Inline Target

```
!<u>This text will only be handled when the file is converted to HTML</u>!
```

###2.10.11. Escape Symbols

To escape a symbol, precede it with a single backslash ` \ `.  For example,
`\-` gives a hyphen -.  In particular, ` \ ` followed by a <kbd>CR</kbd>
(Carrige Return) forces a line break.

###2.11. Horizontal Rules

The number of `-` is required to be greater than three, to distinguish it from
em-dash `---`.

```
----
```

----

###2.12. References

####2.12.1. Cross-References

#####2.12.1.1. Labels

The `label` is attached to the closest HTML element preceeding it.

```
[# label]
```

#####2.12.1.2. Links

```
[linked text # label]
```

####2.12.2. Hyper-References

`@` for *at*:

```
[@ URL]
```

or

```
[linked text @ URL]
```

####2.12.3. Citation

`$`, for *credit*, plus the citation identifier from a database.

```
$id
```
or

```
[$id]
```

Author name can be suppressed by preceeding `$` with a minus sign `-`.  The
syntax is inspired by [pandoc](http://johnmacfarlane.net/pandoc)
[citations](http://johnmacfarlane.net/pandoc/README.html#citations).

###2.13. Images

`&` for *with*:

```
[& image URL]
```

or

```
[caption & image URL]
```

###2.14. Alignment

Except the target block, any Kiwi block can be aligned to the left, to the
right or to the center.

####2.14.1. Align to the Left

This is the default alignment, so the beginning and ending `<` can be and are
usually omitted.

```
<
This text is aligned to the left.
<
```

effects

<div align=left>
This text is aligned to the left.
</div>

####2.14.2. Align to the Right

```
>
This text is aligned to the right.
>
```

effects

<div align=right>
This text is aligned to the right.
</div>

####2.14.3. Align to the Right

```
>
This text is aligned to the center.
<
```

effects

<div align=center>
This text is aligned to the center.
</div>

###2.15. Meta-Data Block

Put a definition list inside `%`:

```
%
= author
  Hong-Yi Dai
= title
  Kiwi
= date
  2015-04-07
= abstract
  A simple, intuitive and elegent wiki
%
```

