<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <script type="text/JavaScript" src="js/jquery.js"></script>
</head>
<style>
    div section{ 
        width: 30px; 
        height: 30px; 
        margin: 10px; 
        display: inline-block; 
    }
    div section:nth-of-type(1){ 
        background-color: #177cb0; 
    }
    div section:nth-of-type(2){ 
        background-color: #db5a6b; 
    }
    div section:nth-of-type(3){ 
        background-color: #008000; 
    }
    div section:hover{ 
        cursor:pointer;
    }
</style>
<body>
    <div>
        <section onclick="blue()"></section>
        <section onclick="red()"></section>
        <section onclick="green()"></section>
    </div>
    
    <center>
        <h2 style="display:inline-block;">颜色主题jquery变换</h2>
        <form action="" id="simpleCalc">
            <span>input：</span><input type="text" required><br><br>
            <button id="calc">确认</button>
        </form>
        <span id="result"></span>
    </center>

    <script>
      //设置默认颜色主题
        $(document).ready(function(){
            blue();
        });
        // 点击单个换色
        function blue(){
            change("#177cb0");
        }

        function red(){
            change("#db5a6b");
        }

        function green(){
            change("#008000");
        }
        //设置需要改变颜色的元素及其样式
        function change(colo){
            $("#calc").css("background-color", colo);
            $("h2, span").css("color", colo);
            $("input").css("color", colo);
            $("input[type=text]").focus(function(){$(this).css("outline", "none")});
            $("input[type=text]").focus(function(){$(this).css("border", "2px solid " + colo)});
            $("input[type=text]").blur(function(){$(this).css("border", "1px solid gray")});
        }
    </script>
</body>
</html>    
