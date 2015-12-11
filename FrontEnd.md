#Front End

##HTML Knowledge
####DOCTYPE: 
* Document type declaration, is an instruction that associates a particular SGML or XML document (webpage) with a document type definition (DTD) (e.g. HTML).
* Why is it important? It defines the version of (X)HTML used. It will trigger the "standard" mode for browsers. 

####Browser Modes:
* Standard Mode: For the web page strictly complies with W3C and IETF standards.
* Quirks Mode: For maintaining the backward compatibility with the web page designed for IE 5 or earlier.

##JS Knowledge
##Strict Mode:
* Triggered by following line at the top of the js code or on the top of a function:
```javascript
  "use strict;"
```
* Strict Mode eliminates some js silence errors by change them to throwing errors
 * Make it impossible to create globle varible by mistake.
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
 * "eval" method can't intorduce new variable.
 * Forbids delete plain name.
* Support: IE > 9 others 
 
#References:
* https://en.wikipedia.org/wiki/Document_type_declaration
* http://www.w3.org/QA/Tips/Doctype
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode

