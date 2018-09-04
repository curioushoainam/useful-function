# useful-function

# function for converting string to alias
<script>
	// Hàm biến đổi string to alias	
	function str2alias(id_src, id_des){
		var str = ($('#' + id_src).val()).trim();
	    str = str.toLowerCase();
	    str = str.replace(/à|á|ạ|ả|ã|ằ|ắ|ặ|ẳ|ẵ|ă|â|ấ|ầ|ậ|ẩ|ẫ/g,"a");
	    str = str.replace(/è|é|ẹ|ẻ|ẽ|ê|ề|ế|ệ|ể|ễ/g,"e");
	    str = str.replace(/í|ì|ị|ỉ|ĩ/g,"i");
	    str = str.replace(/ó|ò|ọ|ỏ|õ|ơ|ớ|ờ|ợ|ở|ỡ|ô|ố|ồ|ộ|ổ|ỗ/g,"o");
	    str = str.replace(/ú|ù|ụ|ủ|ũ|ư|ừ|ứ|ự|ử|ữ/g,"u");
	    str = str.replace(/ý|ỳ|ỵ|ỷ|ỹ/g,"y");
	    str = str.replace(/đ/g,"d");
	    str = str.replace(/[^a-z0-9]+/g, "-")
	              .replace(/^-+|-+$/g, "-")
	              .replace(/^-+|-+$/g, '');
	    var des = document.getElementById(id_des);
	    des.value = str;
	}

</script>
