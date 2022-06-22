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

## ( 3 )
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
			},
			buttons: [
				{
					text: "キャンセル",
					click: function() {
						$( this ).dialog( "close" );
					}
				}
			]
		});
	});

});
</script>


<button id="opener">ダイアログを開く</button>
<div id="dialog" title="Dialog Title" style="display:none;">アップロードしますか?</div>
```

## ( 4 )
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
			},
			buttons: [
				{
					text: "OK",
					click: function() {
						$( this ).dialog( "close" );
					}
				},
				{
					text: "キャンセル",
					click: function() {
						$( this ).dialog( "close" );
					}
				}
			]
		});
	});

});
</script>


<button id="opener">ダイアログを開く</button>
<div id="dialog" title="Dialog Title" style="display:none;">アップロードしますか?</div>
```

### toastr.js 
```javascript
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/toastr.js/2.1.4/toastr.min.js"></script>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/toastr.js/2.1.4/toastr.css">

<script>
jQuery.isMobile = (/android|webos|iphone|ipad|ipod|blackberry|iemobile|opera mini/i.test(navigator.userAgent.toLowerCase()));
toastr.options={"closeButton":false,"debug":false,"newestOnTop":false,"progressBar":false,"positionClass":"toast-bottom-center","preventDuplicates":false,"onclick":null,"showDuration":"300","hideDuration":"1000","timeOut":"3000","extendedTimeOut":"1000","showEasing":"swing","hideEasing":"linear","showMethod":"fadeIn","hideMethod":"fadeOut"};
if ( !$.isMobile ) {
    toastr.options.positionClass = "toast-top-center";
}


$(function(){
	$("#btn").on( "click", function(){

		toastr.error("エラーです");

	});
});



</script>
<input id="btn" name="btn" type="button" value="実行">
```

### アンカーを右端に移動( float:right )
```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/5.0.1/css/bootstrap.min.css">

<h3 class="alert alert-primary">
    <a href="control.php" style="text-decoration:none;">掲示板</a>
    <a href=".." style="float:right;text-decoration:none;">🧲</a>
</h3>
```


### jQuery を使わない FORM 送信
```javascript

<script>
function send_data(){

	if ( confirm("OK") ) {

		// 現在の日付データ
	        var dateNow = new Date();
		console.log( dateNow );
		console.log( dateNow.getFullYear() );
		console.log(dateNow.getMonth());
		console.log( "0" + (dateNow.getMonth()+1) );
		console.log( ("000000" + (dateNow.getMonth()+1)).slice(-2)  );
		console.log(dateNow.getDate());

	        var dateString = 
	            dateNow.getFullYear() + "/" + 
	            ("0"+(dateNow.getMonth()+1)).slice(-2)+ "/" + 
	            ("0"+(dateNow.getDate())).slice(-2);
	        var timeString = 
	            ("0"+(dateNow.getHours())).slice(-2) + ":" + 
	            ("0"+(dateNow.getMinutes())).slice(-2) + ":" + 
	            ("0"+(dateNow.getSeconds())).slice(-2);

		document.getElementById("datetime").value = dateString + " " + timeString;

		return true;
	}

	return false;

}
</script>

<form id="frm" onsubmit="return send_data();">
<input type="hidden" name="datetime" id="datetime">
<input id="send" name="send" type="submit" value="送信">
</form>
```
