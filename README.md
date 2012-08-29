jQuery List Builder
====================
By: Spencer Neese   
Version: 1.0   
Requires: jQuery UI 1.7+ and jQuery 1.3.2+   
Demo: [http://jsfiddle.net/th3uiguy/MRu67/](http://jsfiddle.net/th3uiguy/MRu67/embedded/result/)
Git: [https://github.com/th3uiguy/jquery-listbuilder.git](https://github.com/th3uiguy/jquery-listbuilder.git)   



Description
---------------------
jQuery List Builder uses the jQuery UI [autocomplete](http://jqueryui.com/demos/autocomplete/) to convert a basic input into an email client like "To" field with autocompletion.





Options
---------------------
#### showRemoveIcon ###
(Boolean) Flag to show the 'X' icon on each list item.


#### onlyAddFromSource ###
(Boolean) When set to true, the user is only able to add items from the autocomplete `source`.

#### items ###
(Array) An array of items to be added when listBuilder is being initialized. Items may have a `label`, `value` or `locked` attribute. 

*	The `label` should always be specified. 
*	When `value` is not specified the `label` attribute is used instead. 
*	The `locked` attribute will prevent a user from removing that element from the list and makes the list item appear like normal text in the field.

```js
	items: [
		{"label": "Apples"},
		{"label": "Pears", "value": 233},
		{"label": "Oranges", "locked": true}
	]
```

#### maxItems ###
(Integer) The maximum number of items that the list should accept. When this limit is reached the `onMaxReached` function is called.

#### onMaxReached ###
(Function) Triggered when the number of items entered is more than `maxItems`.

	onMaxReached: function(item, $list){
		alert(item.label + ' could not be added');
	}

#### onAddButtonClick ###
(Function) Places an add button to the right of the input and triggers this function when the add button is clicked.

	onAddButtonClick: function(){
		$('.listBuilder').listBuilder('add', {label:"Grapes"});
	}

#### onAddItem ###
(Function) Triggered after an item is added to the list.

	onAddItem: function(item){
		alert(item.label + " was added");
	}

#### beforeAddItem ###
(Function) Called before an item is added. This function should return `true` or `false` to the callback signifying if the item should be added or not.

	beforeAddItem: function(item, callback){
		var toAdd = (item.value !== 'peas');
		callback(toAdd);
	}

#### beforeRemoveItem ###
(Function) Triggered before an item is removed,  from the list.

	onRemoveItem: function(item, callback){
		var toRemove = (item.value === 'peas');
		callback(toRemove);
	}

#### autocompleteOptions ###
See [http://jqueryui.com/demos/autocomplete/#options](http://jqueryui.com/demos/autocomplete/#options) for a full description of these options.




	
Methods
---------------------
### Add ###
Add an item to the list. Pass the new item as an object with `label`, `value` and `locked`.
  
	$('input').listBuilder('add', {label:"Apples", value:"100", locked:false});

### Count ###
Get the current number of items in the list

	$('input').listBuilder('count');




<br /><br />
Copyright 2012, Spencer Neese   
Dual licensed under the 
[MIT](https://raw.github.com/th3uiguy/jquery-listbuilder/master/MIT-LICENSE.txt) or 
[GPL](https://raw.github.com/th3uiguy/jquery-listbuilder/master/GPL-LICENSE.txt) Version 2 licenses. 
