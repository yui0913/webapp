<script>
export default {
  name: 'HelloWorld',
  props: {
   
  }
}
</script>

<script type="text/javascript">
document.getElementById("view_time").innerHTML = getNow();

function getNow() {
	var now = new Date();
	var year = now.getFullYear();
	var mon = now.getMonth()+1; //１を足すこと
	var day = now.getDate();

	//出力用
	var s = year + "年" + mon + "月" + day + "日"; 
	return s;
}
</script>