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

#===============================================================
# Go-to-top
#html
<div>
    <button type="button" class="btn btn-info" id="gototop" title="Go to top"><i class="fa fa-angle-up" aria-hidden="true"></i>
    </button>
</div>
 #javascript
<script>
	// Go to top
	window.onscroll = function() {scrollFunction()};
 	function scrollFunction() {
	    if (document.body.scrollTop > 20 || document.documentElement.scrollTop > 20) {
	        document.getElementById("gototop").style.display = "block";
	    } else {
	        document.getElementById("gototop").style.display = "none";
	    }
	}
	
	$("#gototop").click(function() {
	     $("html, body").animate({ scrollTop: 0 }, "slow");
	     return false;
	});
	//  -/- Go to top
 </script>
 #css
/*Go to top symbol*/
#gototop {
  display: none;
  position: fixed;
  bottom: 20px;
  right: 30px;
  z-index: 99; 
  border: none;
  outline: none;  
  cursor: pointer;  
  border-radius: 50%;
}
 #gototop:hover {
  background-color: lightgrey;
}
/* /Go to top symbol*/
#===============================================================
# Function selects using pathname in alias or origin
function href($type,$item,$seo=0)
{
	if($seo)
	{
		switch($type)
		{
			case 'sanpham':
				return DOMAIN.$item->alias.'-'.$item->ma;
		}	
	}else
	{
		switch($type)
		{
			case 'sanpham':
				return 'index.php?v=chitiet&ma='.$item->ma;
		}	
	}
}
#===============================================================
#prevent refresh matter
<script>
if ( window.history.replaceState ) {
  window.history.replaceState( null, null, window.location.href );
}
</script>
#===============================================================
