#Knockout JS

* Knockout is usually used to build a Model-View-ViewModel (MVVM) pattern web UI.

* **_data-bind_** attributes are how Knockout lets you declaratively associate viewmodel properties with DOM elements. You can use multiple types of binding to bind data to dom elements. E.g. text, value, click, foreach, even for visible.
  ```html
     <!-- format -->
     <tbody data-bind="foreach: opts">
  ```
  * Node 1: you can do multiple data-bind for one dom element:
  ```html
    <!-- $root refers to the AppViewModel -->
    <select data-bind="options: $root.availableOpts, value: optValue, optionsText: 'optName'"></select>
  ```
* **_observables_**, a knockout concept - properties that automatically will issue notifications whenever their value changes. __ko.observable__ is used to make the properties of viewmodel observable.
  * Note 1: After make a property observable and binding it to a input, the dom tree won't update after you finish the input, i.e. tab out from the input.
  * Note 2: After make a property observable, the property become a function of the AppViewModel.
  ```javascript
     function AppViewModel() {
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
