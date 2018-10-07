<html>
<head>
<style>
</style>
<script>
function load(){var test=document.getElementById("test");
document.body.style.backgroundColor=test.options[test.selectedIndex].value;//获得select的selectedIndex属性来获得option的value值，设置body的backgroundColor属性
  }
</script>
<meta charset="UTF-8">
</head>
<body>
<select id="test" onchange="load()"><!--在select selected的选项改变时触发事件-->
  <option value="white">白色</option>
  <option value="yellow">黄色</option>
  <option value="green">绿色</option>
  <option value="red">红色</option>
  </select>
段龙飞 
  </body>
</html>
  

