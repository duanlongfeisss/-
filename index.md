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
  </body>
</html>
  

三、误差放大器
  误差放大器的作用是为了保证输出恒流或者恒压，对反馈电压进行采样处理。从而来调节驱动MOS管的PWM，
四、驱动电路
  最后的驱动部分结构很简单，就是很大面积的MOS管，电流能力强。
五、其他模块电路
  这里的其他模块电路是为了保证芯片能够正常和可靠的工作，虽然不是原理的核心，却实实在在的在芯片的设计中占据重要位置。具体说来有几种功能。
1、启动模块
  启动模块的作用自然是来启动芯片工作的，因为上电瞬间有可能所有晶体管电流为0并维持不变，这样没法工作。启动电路的作用就是相当于“点个火”，然后再关闭。上电瞬间，S3自然是打开的，然后S2打开可以打开M4 Q1等，就打开了M1 M2，右边恒流源电路正常工作，S1也打开了，就把S2给关闭了，完成启动。如果没有S1 S2 S3，瞬间所有晶体管电流为0。
2、过压保护模块OVP
  很好理解，输入电压太高时，通过开关管来关断输出，避免损坏，通过比较器可以设置一个保护点
3、过温保护模块OTP
  温度保护是为了防止芯片异常高温损坏，原理比较简单，利用晶体管的温度特性然后通过比较器设置保护点来关断输出。
4、过流保护模块OCP
  在譬如输出短路的情况下，通过检测输出电流来反馈控制输出管的状态，可以关断或者限流。如图的电流采样，利用晶体管的电流和面积成正比来采样，一般采样管Q2的面积会是输出管面积的千分之一，然后通过电压比较器来控制MOS管的驱动。
还有一些其他辅助模块设计。
六、恒流源和电流镜
  在IC内部，如何来设置每一个晶体管的工作状态，就是通过偏置电流，恒流源电路可以说是所有电路的基石，带隙基准也是因此产生的，然后通过电流镜来为每一个功能模块提供电流，电流镜就是通过晶体管的面积来设置。
  以上即为DC芯片的浅略了解。
