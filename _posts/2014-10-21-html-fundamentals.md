#### HTML Fundamentals

* HTML documents
  * HTML was created to share research documents
  * doctype declares which version of HTML standard you are using
  * leave out doctype and the browser has to guess
  * html
    * head
      * title
    * body
* The head element
  * metadata, not usually shown to the user
  * except for the title
  * meta includes metadata such as keywords, description, author
  * meta can also emulate http headers with 'http-equiv'
  * script
  * style inline styles
  * link directive indicating related documents, often linking in stylesheets
  * base base address for all relative links, not specified the browser will make assumptions
* The body element
  * bulk of the content
  * headings
  * text
  * lists
  * links
  * tables
  * images/objects
* Using id and class attributes
  * id is unique, class can be applied to a lot of elements 

#### HTML Text
 * Headings
   * H1 -> primary heading of document, H2-H6 sub- headings
 * Block vs. Inline Elements
  * block elements
    * container elements for grouping
    * may contain other block elements and line elements
  * inline elements
    * container for text and other inline elements
    * a span can't contain a div
 * Whitespace
   * whitespace generally ignored in block and inline
   * pre - whitespace is respected
   * br explicit line break
   * hr horizontal rule
   * character entities, nbsp indicates a space which cannot be used for line breaks. lt, gt for angle brackets
 * Additional Text Elements
  * sup and sub, superscript and subscript
  * cite, cite work by another
  * abbr and acronym, abbreviation or acronym
  * em, strong, typically you use styles for this
  * code, samp -> code block or program output
  * kbd, var -> keyboard input and code variables
  * blockquote, q --> block level or inline quotes

#### HTML Lists

* List Types
  * li = list item 
  * unordered, ul + li -> bullets
  * ordered, ol + li -> numeric or alpha labels
  * definition list. dl, dt: definition term, dd: definition definition -> term + definition
  * sublists by nesting a ul or ol inside an li

#### HTML Links
* Link Concepts
  * anchors (a tags) act as either source or target for linking
  * named anchors are targets
  * anchors with href attributes are sources
  * absolute provides the entire URI
  * relative is relative to the current document -> base element to change what it is relative to
* Understanding Targets
  * links can target anchors, within the same document or in a separate document
  * we use the # symbol to specify an anchor or the id of an element to link to
* Additional link attributes
  * language, relationship, content type, access key
  * not often used because they are dependent on the thing you are linking to which can change
   
#### HTML Tables
* Table Elements
  * table, can have a summary attribute
    * caption
    * thead -> headers for columns, single row tr, th, th, tr
    * tfoot -> summary etc., footer comes before tbody so they can render before reading all the data
    * tbody -> multiple rows presenting data
* Table Data
  * tr represents a row
    * used in header, body and footer
    * th table header data insied tr inside thead
    * td tabe data
* Spanning Columns and Rows
  * colspan/ rowspan 
  * attributes used on td (cell) to flow across rows or columns
* Formatting Tables
  * not tables for formatting, use divs or block elements + stylesheets for that
  * control width, border, cell padding (space around content inside cell), cell spacing (space between cells)

#### HTML Images and Objects
