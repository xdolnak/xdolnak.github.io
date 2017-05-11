# Assignment 3

#### Our task was to write an XML document describing presentation, than its generate pdf and HTML version

#### We had to do
* Describe the document using XML Schema, DTD or Relax NG
* Create an XML document as a sample presentation
* Basic XSLT, trasformations and their parametrization
* XSLT conversion from XML to XHTML
* XSLT conversion from XML to PDF

#### My implementation
##### Sample presentation can be found in presentation.xml
###### Used tags
{% highlight xml %}
    <presentation> - root element
    <slide> - slide of a presentation, description of a page
    <universtity> - university heading of a title page
    <faculty> - faculty heading of a title page
    <subject> - subject heading of a title page
    <author> - author heading of a title page
    <title> tag describing  title of a title page or other types of pages
    attribute "type" - describes type of this slide, supported values are title, two-part, one-part, references
    attribute "color" - describes background-color of a slide
    <text> - text as a block of text (heading style text)
    <p> - text as a paragraph
    <list> - base of an unordered list (ul)
    <item> - item of an unordered list (li)
    <image> - imported image
     attribute "src" - relative URL to image
     attribute "color" - description of an image
    <left> - left part of a two-part slide
    <right> - right part of a two-part slide
{% endhighlight %}
###### Paramtrization in common.xml
{% highlight xml %}
    <universtity> - size of university pt/px
    <faculty> - size of faculty pt/px
    <subject> - size of subject pt/px
    <author> - size of author pt/px
    <title> size of title pt/px
    <main-title> size of main-title on a title page pt/px
    <text> - size of text pt/px
    <p> - size of p pt/px
    <item> - size of item pt/px
    <font-color> - color of all fonts
    <enabled-page-numbers> - enables/disables page counting
{% endhighlight %}
###### Other files
{% highlight xml %}
    <pdf.xsl> - XSL to generate pdf file
    <html.xsl> - XSL to generate HTML files
    <presentation.dtd> - description of presentation.DTD
    <generate_pdf_html.bat> - generates output on windows
{% endhighlight %}


I also applied the change, which adjusted the chapter title.