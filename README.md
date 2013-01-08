#Kiwi Wiki#

Kiwi is a light-weight Wiki markup language.  It is *elegant* and *intuitive*.

##1. Motivation##

Every [Wiki markup language](http://c2.com/cgi/wiki?WikiMarkupLanguage) in use
today sucks!  Their syntax is inelegant and unintuitive.  Kiwi is meant to
remedy this.

##2. Kiwi Syntax##

The syntax is inspired by both the [Creole
1.0](http://www.wikicreole.org/wiki/Creole1.0) Wiki standard and the [txt2tag
source format](http://txt2tags.org/manpage.html#markup).  It is not fixed yet.
Here is part of it.

###2.1. Kiwi Headings (Till Level 6)###

####2.1.1. Kiwi Unnumbered Headings####

    =Unnumbered Heading 1=
#Unnumbered Heading 1#

    ==Unnumbered Heading 2==
##Unnumbered Heading 2##

    ===Unnumbered Heading 3===
###Unnumbered Heading 3###

####2.1.2. Kiwi Numbered Headings####

    #Numbered Heading 1#
#1. Numbered Heading 1#

    ##Numbered Heading 2##
##1.1. Numbered Heading 2##

    ###Numbered Heading 3###
###1.1.1. Numbered Heading 3###

###2.2. Kiwi Lists###

####2.2.1. Kiwi Unordered Lists####

    - Red
      - Green
        - Blue

* Red
   * Green
      * Blue

####2.2.2. Kiwi Ordered Lists####

    + Red
      + Green
        + Blue

1. Red
   1. Green
      1. blue

###2.3. Kiwi Paragraph###

    A paragraph is made by one or more lines.

    A blank line separates them.

A paragraph is made by one or more lines.

A blank line separates them.

###2.4. Kiwi Texts###

    ||strong||
**strong**

    //emphasized//
*emphasized*

    __underlined__
<u>underlined</u>

    --strikeout--
<strike>strikeout</strike>

###2.5. Kiwi Horizontal Rules###

    ----
----

