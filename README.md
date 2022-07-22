# Simple-MVVM-frame-based-on-TS
## 简介
这是一个使用Typescript编写的简易MVVM框架，目前仅支持文本插值和在input，select，textarea元素上的双向数据绑定功能，因为训练营开始前对Vue框架基本没有了解，对于node的一些组件比如Jest也是第一次接触，加上代码开发过程中经常会遇到出乎意料的bug还有学校安排的一些任务，没有实现更多的指令功能，Jest测试也仅包括了utils文件里的一些函数，现有的代码结构设计的也有很多可以改进的地方，尤其是相对比较复杂的编译部分。
------ 

## 使用方法
下载全部代码后，进入项目根目录，运行`npm run serve`命令，打开浏览器输入`localhost:9000`会显示出运用该框架的一个示例网页，其中包含了绝大多数框架实现的特性。
------

## 功能介绍
框架支持 .操作符，e.g `name.first`，[ ]操作符，e.g `vehicle['bicycle']`，可以识别对象的多层嵌套引用，e.g`title[titleIndex.type]`，目前不支持Javascript表达式
1. 文本插值
框架支持`{{name.first}}`文本插值格式，被双{}包围的文本部分被认为是绑定的数据，一个文本节点内使用文本插值的次数不限，e.g `<span>{{vehicle['bicycle']}}{{vehicle['car']}}{{vehicle['yacht']}}{{vehicle['plane']}}</span>`
2. mvvm-model双向绑定指令
框架目前仅支持`mvvm-model`一种内建指令，可以将该指令运用在type类型为text | radio | checkbox的input元素，textarea元素和select元素上，将该属性放到其他元素上会导致无效。
------

## 实现原理和程序运行流程图
- 1. 使用`new MVVM(data)`创建一个MVVM应用，在构造函数中，框架会执行一些对数据的初始化工作，包括将传入的数据扩展为程序需要的格式
- 2. 创建MVVM应用实例后，调用`mount(selector)`将应用挂载到一个DOM节点上，这一步会把MVVM应用实例的数据和该DOM节点中符合格式的数据格式绑定起来
    1. 


