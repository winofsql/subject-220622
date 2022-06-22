# subject-220622

- ### [jQuery UI](https://jqueryui.com/)
  - [Dialog](https://api.jqueryui.com/dialog/)


## jQuery UI のダイアログの基本サンプル
```javascript
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
<link id="link" rel="stylesheet" href="https://ajax.googleapis.com/ajax/libs/jqueryui/1.12.1/themes/base/jquery-ui.css">
<script src="https://ajax.googleapis.com/ajax/libs/jqueryui/1.12.1/jquery-ui.min.js"></script>

<script>
$(function(){

	$( "#dialog" ).dialog({ autoOpen: false });
	$( "#opener" ).click(function() {
		$( "#dialog" ).dialog( "open" );
	});

});
</script>


<button id="opener">open the dialog</button>
<div id="dialog" title="Dialog Title">I'm a dialog</div>
```
