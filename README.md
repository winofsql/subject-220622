# subject-220622

- ### [jQuery UI](https://jqueryui.com/)
  - [Dialog](https://api.jqueryui.com/dialog/)


## jQuery UI のダイアログの基本サンプル( 1 )
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

## ( 2 )
```javascript
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
<link id="link" rel="stylesheet" href="https://ajax.googleapis.com/ajax/libs/jqueryui/1.12.1/themes/base/jquery-ui.css">
<script src="https://ajax.googleapis.com/ajax/libs/jqueryui/1.12.1/jquery-ui.min.js"></script>

<script>
$(function(){

	$( "#opener" ).click(function() {
		$( "#dialog" ).dialog({
			modal: true,
			title: "ダイアログのタイトルです",
			close: function() {
				$( this ).dialog( "close" );
			}
		});
	});

});
</script>


<button id="opener">ダイアログを開く</button>
<div id="dialog" title="Dialog Title" style="display:none;">アップロードしますか?</div>
```
