#Front End

##HTML
####DOCTYPE: 
* Document type declaration, is an instruction that associates a particular SGML or XML document (webpage) with a document type definition (DTD) (e.g. HTML).
* Why is it important? It defines the version of (X)HTML used. It will trigger the "standard" mode for browsers. 

####Browser Modes:
* Standard Mode: For the web page strictly complies with W3C and IETF standards.
* Quirks Mode: For maintaining the backward compatibility with the web page designed for IE 5 or earlier.

####HTML vs XHTML:
* XHTML stands for EXtensible HyperText Markup Language
* XHTML is almost the same but more strict than HTML
* XHTML is HTML that defined as an XML application.
* Important
  * "XHTML DOCTYPE" is mandatory
  * The xmlns attribute in \<html\> is mandatory
  * \<html\>, \<head\>, \<title\>, and \<body\> are mandatory
  * XHTML elements must be properly nested
  * XHTML elements must always be closed
  * XHTML elements must be in lowercase
  * XHTML documents must have one root element
  * Attribute names must be in lower case
  * Attribute values must be quoted
  * Attribute minimization is forbidden 

##CSS
####inline and inline-block
* Elements with display:inline-block elements are like display:inline elements, but they can have a width and height. So you can use an inline-block element as a block while flowing it within text.

####Difference between classes and ID
* CSS uses the prefix # for IDs and . for Classes.
* A class could be used by multiple elements and an element can have multiple classes.
* An element could only have one ID and ID should be unique among all elements.

####z-index
* Represents the position of the element along the z-axis
* The layer with larger z-index is above the others.
* Only has an effect if an element is positioned.

####Stacking context
* Positioning and assigning a z-index value to an HTML element creates a stacking context, (as does assigning non-full opacity).
* Stacking contexts can be contained in other stacking contexts, and together create a hierarchy of stacking contexts.
* Each stacking context is completely independent from its siblings: only descendant elements are considered when stacking is processed.
* Each stacking context is self-contained: after the element's contents are stacked, the whole element is considered in the stacking order of the parent stacking context.
* Example: <br />
  ![alt tag](https://developer.mozilla.org/@api/deki/files/913/=Understanding_zindex_04.png)

##JS
####Strict Mode:
* Triggered by following line at the top of the js code or on the top of a function:
```javascript
  "use strict;"
```
* Strict Mode eliminates some js silence errors by change them to throwing errors
 * Make it impossible to create global varible by mistake.
 * Make assignments that will fail silencely throw an error. e.g.
  ```javascript
    NaN = 12;
  ```
 * Throw error when trying to delete undeletable properties. E.g. Object.prototype
 * Throw error when have duplicate property names in an object when defined.
  ```javascript
    var obj = { p : 1, p : 2};
    //in standard mode , obj will be {p : 2} by default. By in strict mode, it will throw a error.
  ```
 * Throw error when there is duplicate parameter name in a function.
 * Forbids Octal Numbers
  ```javascript
    var abc = 014; // syntax error in strict mode.
  ```
 * Forbids 'with' method
 * "eval" method can't introduce new variable.
 ```javascript
    eval('var x; x = 123;');
    console.log(x); // undecleared in strict mode.
 ```
 * Forbids delete plain name.
 ```javascript
    var abc;
    delete abc; // not allowed in strict mode.
 ```
* Support: IE > 9
 
#References:
* https://en.wikipedia.org/wiki/Document_type_declaration
* http://www.w3.org/QA/Tips/Doctype
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode
* http://www.w3schools.com/html/html_xhtml.asp
* http://stackoverflow.com/questions/8969381/what-is-the-difference-between-display-inline-and-display-inline-block
* https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/Adding_z-index
* https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context

