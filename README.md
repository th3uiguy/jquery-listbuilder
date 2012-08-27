jQuery List Builder
====================
By: Spencer Neese   
Version: 1.0   
Requires: jQuery UI 1.7+ and jQuery 1.3.2+   
Demo: [http://jsfiddle.net/th3uiguy/MRu67/](http://jsfiddle.net/th3uiguy/MRu67/)



## Description ##

jQuery List Builder uses the jQuery UI [autocomplete](http://jqueryui.com/demos/autocomplete/) to convert a basic input into an email client like "To" field with autocompletion.




## Options ##
```
maxItems:
onAddButtonClick:
onlyAddFromSource:
beforeAddItem:
items:
onAddItem: 
onRemoveItem:
onMaxReached:
showRemoveIcon: 
autocompleteOptions: //see: http://jqueryui.com/demos/autocomplete/#options for these options
```

	
	
## Methods ##
### Add ###
Add an item to the list. Pass the new item as an object with `label`, `value` and `locked`.
  
	$('input').listBuilder('add', {label:"Apples", value:"100", locked:false});

### Count ###
Get the current number of items in the list

	$('input').listBuilder('count');





Copyright 2012, Spencer Neese   
Dual licensed under the MIT or GPL Version 2 licenses.   
https://raw.github.com/th3uiguy/jquery-listbuilder/master/GPL-LICENSE.txt   
https://raw.github.com/th3uiguy/jquery-listbuilder/master/MIT-LICENSE.txt
