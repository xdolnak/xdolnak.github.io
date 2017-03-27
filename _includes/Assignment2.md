### Second assignment

#### Important notes

* I rewrote my whole bachelor thesis from Word to Docbook.
* I overlooked the fact we should only write from 10 to 15 pages.
* I did not want to delete my extra work, so I send the whole document.
* The document would not make sense if I deleted these pages.

#### Our task was to write a document using Docbook

#### We had to use
* standard text classification to chapters, sections and generated content
* emphasis and lists
* internal and external links
* footnote
* list of referenced literature
* generated list of used images and tables
* indexes

#### My implementation
###### Standard text classification to chapters, sections and generated content
I used following tags to complete this part of the task
{% highlight xml %}
    <chapter> - tag describing main chapters of the document
    <section> - tag describing sections and subsections of the document(can be nested)
    <para> - tag describing block of text
    <programlisting> tag describing  block of code
{% endhighlight %}
###### Emphasis and lists
I used following tags to complete this part of the task
{% highlight xml %}
    <emphasis> - tag which put the ephasis on the nested text
    <itemizedlist> - tag describing a list
    <listitem> - tag describing an item in a list
{% endhighlight %}
I did not have an ordered list in my thesis, so I used only unordered lists.
I did not find a way how to customize "the list mark", so I used only full-bullets.
###### internal and external links
I used following tags to complete this part of the task
{% highlight xml %}
    <xref linkend=''/> - tag which behaves as <a href=''> tag in html, I mostly used it for internal links
    <ulink url='' /> - tag in bibliography part, I used it for external links
{% endhighlight %}
###### footnote
I used following tags to complete this part of the task
{% highlight xml %}
    <footnote> - tag which creates a footnote with a link
{% endhighlight %}
###### list of referenced literature
I used following tags to complete this part of the task
{% highlight xml %}
    <bibliography> - tag which defines the beginning of bibliography
    <bibliomixed> - tag which defines a bibliography entry
    <bibliomisc> - tag which defines a bibliography source
    <xref linkend=''/> - I used this tag for referencing, because it was the only one which created a clickable link
{% endhighlight %}
I found a biblioentry tag, which also defines an entry.
###### generated list of used images and tables
I used following tags to complete this part of the task
{% highlight xml %}
    <figure> - tag which describes a graphical object
    <mediaobject>, <imageobject>, <imagedata> - supporting tags for image
    <table> - tag which defines a table
    <tgroup>, <colspec>, <thead>, <row>, <tbody>, <entry> - supporting tags for table
{% endhighlight %}
I did not have a list of pictures and tables in my thesis, so I let it to autogenerate.
###### indexes
I used following tags to complete this part of the task
{% highlight xml %}
   </indexterm> - tag which describes a term to be indexed
   <primary>, <secondary>, <tertiary> - tags describing a level of indexation
   <index> - tag which describes a place to generate the index
{% endhighlight %}
##### Extra
I used glossary tag in order to create my glossary of terms, which was a prat of my thesis.
I changed my xslt themes a bit.
{% highlight xml %}
xsl:template name="book.titlepage.recto">
  <xsl:apply-templates mode="book.titlepage.recto.auto.mode" select="bookinfo/author"/>
  <xsl:apply-templates mode="book.titlepage.recto.auto.mode" select="info/author"/>
  <xsl:choose>
    <xsl:when test="bookinfo/title">
      <xsl:apply-templates mode="book.titlepage.recto.auto.mode" select="bookinfo/title"/>
    </xsl:when>
   <!-- I moved the order of titles in the middle of title page. -->

   <xsl:template name="book.titlepage.before.recto">
     <fo:block xmlns:fo="http://www.w3.org/1999/XSL/Format" text-align="center" font-size="12pt" font-family="sans-serif">
         <xsl:value-of select="/book/bookinfo//affiliation/orgname"/>
       </fo:block><fo:block xmlns:fo="http://www.w3.org/1999/XSL/Format" space-after="8cm" space-before="6pt" border-bottom-width="0.5pt" border-bottom-style="solid" text-align="center" font-size="14pt" font-family="sans-serif"  text-transform="uppercase">
         <xsl:value-of select="/book/bookinfo//affiliation/orgdiv[@role='fakulta']"/>
       </fo:block>
   </xsl:template>

   <xsl:template name="book.titlepage.before.verso"><fo:block-container xmlns:fo="http://www.w3.org/1999/XSL/Format" absolute-position="absolute" left="0pt" top="22.5cm">
         <fo:block text-align="left" font-family="sans-serif" padding-bottom="3pt">
   	Vedúci práce: <xsl:value-of select="/book/bookinfo/othername[@role='vedúci']"/>
          </fo:block>
          <fo:block text-align="left" font-family="sans-serif" space-before="3pt">
   	       <xsl:value-of select="/book/bookinfo/pubdate"/>
          </fo:block>
       </fo:block-container>
   </xsl:template>

   <!-- I also adjusted some font-sizes, bottom borders and alignments in order to docbook's title page more resemble my bachelor's title page. -->
{% endhighlight %}

I also applied the change, which adjusted the chapter title.
