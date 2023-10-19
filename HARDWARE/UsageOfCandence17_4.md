# Cadence17.4 使用学习手记

## 元器件库部分

1. Capture软件绘制元器件库
2. 调用Capture软件自带库
3. 元器件与PCB封装对应关系解析

### Capture软件操作界面及常用设置介绍

1. Capture CIS Product Chiose -> OrCAD Capture CIS
2. Optiano->preferences 可以进行颜色设置、格点设置和文件选择。
3. Pioneer Snap to grid ： 格点吸附

### Capture 软件自带元器件库介绍

1. 自带库的位置：Cadence -> tools -> capture -> library -> ...
2. IC封装库、嘉立创EDA

### Capture 软件创建元器件库

1. File -> New -> Library
2. 右键STM32.OLB -> New Part -> Name -> Part Reference
3. ZOOM In (I) / ZOOM OUT (U)
4. 放置Pin的时候： properties -> shape -> Dot (低电平有效)
5. Pin Array ：防止一排Pin
6. Edit Pins ：批量改动Pins

### Capture 软件元器件库的管理与调用

1. 通过新建元器件库，保存在本地，积少成多，作为常用的本地库
2. 添加平时网上收集的库以及系统自带的库，作为常用的本地库
3. 通过原理图来获取元器件库，作为常用的本地库
4. 双击原理图元器件可以查看属性

### 元器件库与PCB封装库关联介绍

1. 以STM32为例

>PCB Footprint -> VFQN36-N
>
>Reference -> U5
>
>Value -> STM32

## 原理图绘制部分

### Capture 软件原理图新建、添加命令介绍

1. .DSN 原理图文件

### Capture 软件原理图添加元器件

1. Schematic Page Properties 编辑原理图属性
2. 对齐： 选中 -> Edit.Align

### Capture 软件原理图信号联通

1. 连接

>1、导线连接
>
>2、网表标号连接（网络标号）
>
>3、分页符连接

2. Place net alias （N）：放置网络标号

### Capture 软件原理图电源、地联通

1. 系统自带电源/地连接符的库，不用添加。直接点击放置电源/地的按钮放置。
2. 电源/地是全局变量，不同的页面也可以进行连接，不用添加分页符
3. 自定义电源/地连接符的Name名称，即可将原理图上电源/地全部联通

### Capture 软件原理图添加Bus总线

1. 点击键盘的B键放置总线，或者菜单栏中的Place -> Bus 功能添加总线
2. 总线命名与网络标号的命名命令类似，通过点击N键或者点击菜单栏的Place -> Net Alias 。命令可放置网络标号。放置总线时需要注意：
   >1、总线的名字不能是以数字结尾的
   >
   >2、符号[]前后不能有空格
   >
   >3、命名必须是名字加[]，如BUS[0:15],BUS[0-15].BUS[0...15]注意要有这三点。三种中的一种。

3. 信号线与总线的连接采用的是总线入口的方式，通过点击键盘的E键或者点击菜单栏中的Place  ->  Bus Entry命令

### Capture 软件原理图添加差分属性

1. Tools -> Create Differential Pair ...

### Capture 软件原理图DRC检查工具介绍
1. DRC ： design rule check 

### Capture 软件原理图PDF与BOM清单输出
1. 输出原理图PDF

>File->Export PDF  或者 File->Print （虚拟打印机）

2. 输出BOM清单

    BOM： BILL OF MATERIALS 
3. 修改BOM清单
   Header & Combined property string

### Capture 软件原理图输出各类PCB网表介绍
1. 输出网表  ->  Create netlist
2. 第一方网表   allegro
3. 第三方网表   Formatters -> or Telesis64.dll （或者 Part Value： {PCB Footptinr}）
4. pads网表    Formatters -> orpads2k64.dll
5. AD网表      Fornatters -> orprotel264.dll
6. 文件名：  xxx. NET

### Capture 软件原理图输出网表常见错误解析
1. ERROR(ORCAP-32042):  找到netlist.log文件在输出网表的那个文件下.用写字本打开，一一解决，就可以输出网表了

## 使用Cadence17.4过程中遇到的问题

### PCB封装库的管理与调用
1. 焊盘文件： .PAD
2. 封装文件： .DRA          可编程的封装源文件
3. 封装文件： .PSM          allegro软件调用封装
4. 封装文件： .FSM          allegro软件调用封装
5. FLASH文件： .FSM         allegro软件调用封装
6. 3D封装文件： .STED/.STP
7. 导出封装：  File --> Export -->  Libraries


   

