#Knockout JS

* Knockout is usually used to build a Model-View-ViewModel (MVVM) pattern web UI.

* **_data-bind_** attributes are how Knockout lets you declaratively associate viewmodel properties with DOM elements. You can use multiple types of binding to bind data to dom elements. E.g. text, value, click, foreach, even for visible.
  ```html
     <!-- format -->
     <tbody data-bind="foreach: opts">
  ```
  * Bindings notice __viewmodel changes__ and correspondingly update the __view's DOM__
  * Bindings catch __DOM events__ and correspondingly update __viewmodel properties__
  * **_with_** binding creates a binding context that will be used when binding any elements inside it.

  * Node 1: you can do multiple data-bind for one dom element:
  ```html
    <!-- $root refers to the ViewModel -->
    <!-- we can use $parent to refer to parent DOM element -->
    <select data-bind="options: $root.availableOpts, value: optValue, optionsText: 'optName'"></select>
  ```
  * Node 2: you can even data-bind css.
  ```html
      <li data-bind="text: $data, 
               css: { selected: $data == $root.chosenId() },
               click: $root.goToId"></li>
  ```
  * You can make custom bindings
    * use **_ko.bindingHandlers_**
    * define this **_before_** ViewModel 
  ```javascript
      ko.bindingHandlers.customBinding = {
        /*
        * function called when seting the init status of the element
        * params element: the dom element for this data bind. $(element) for using jQuery function to massage the dom element
        * params valueAccessor: data-bind="customBinding: valueAccessor". valueAccessor() to get the value.
        */
        init: function(element, valueAccessor) {
          ...
        },
        /*
        * function called when the status of element updated.
        */
        update: function(element, valueAccessor) {
          ...
        } 
      };
  ```
  * **_IMPORTANT_** - Do __NOT__ call **_ko.applyBindings_** after loading the data. It will rebuild the ViewModel everytime you load the data from backend, which is very inefficient.
* **_observables_**, a knockout concept - properties that automatically will issue notifications whenever their value changes. __ko.observable__ is used to make the properties of viewmodel observable.
  * Note 1: After make a property observable and binding it to a input, the dom tree won't update after you finish the input, i.e. tab out from the input.
  * Note 2: After make a property observable, the property become a function of the ViewModel.
  ```javascript
     function ViewModel() {
      this.name = ko.observable("ko");
      var curName = this.name(); // name() works as getter, return 'ko'
      this.setName = function(){
       this.name(curName + " js"); // name(newName) works as setter, set the name to 'ko js' 
      }
     }
  ```
  * Note 3: __ko.observableArray__ is used as the observable equivalent of a regular array, which means it can automatically trigger UI updates whenever items are added or removed.
* **_computed properties_**, a knockout concept - these are observable (i.e., they notify on change) and they are computed based on the values of other observables. Usually used to create combine proerrties base on observables. __ko.computed__ is used for computed, we will need to pass a call back function for generating the computed properties. 




#Reference
* http://learn.knockoutjs.com/
