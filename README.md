# 自定义表单设计器

这并非是一个插件，而是我实现的表单设计器的一个框架，为开发人员提供一种表单设计器的思路供大家参考。
用到的主要技术和插件为：vite,vue3,element-plus

此框架生成表单的设计数据（不生成.vue文件），需要后台将设计数据保存下来。显示页面可以将设计数据展示出来。<br>

## 安装和运行

```
npm i
npm run dev
```

## 说明

1. 此表单设计器的灵感来源于小幺鸡表单设计器，所以样子跟小幺鸡很相似，但此框架的代码结构比较清晰，可以自己按照规则添加想要的控件。
2. 核心功能跟组件库无关，添加自己的控件时可以使用html来自定义。

![设计页面](https://github.com/fengqingtian/custom-form/blob/master/public/design.png?raw=true)
![预览页面](https://github.com/fengqingtian/custom-form/blob/master/public/display.png?raw=true)

## 代码解析

1. 一个表单(Form)是由多个控件(Widget)组成的。表单分为设计视图(design view)和展示视图(display view)
2. 一个控件就是一个目录，位于widgets目录下，由以下几个文件组成

* Display.vue 控件显示视图，表单显示时用到。可以通过widget.isEditable属性来区分是可以编辑的还是只读的。
* Design\.vue 控件设计视图，在表单设计时用到
* index\.ts 控件的清单文件（不需要修改）。
* Widget\.ts 控件的数据对象（包含属性配置和值数据），继承自Widget基类
* Property\.vue 控件属性视图，在表单设计时用到。

<br>
widgets/_Demo目录是一个控件模板目录，可以复制后在它的基础上做修改

3. 如何添加一个控件<br>
  a. 添加一个控件目录，完成上面的5个文件<br>
  b. 到DesignView/WidgetTempalteList.vue文件中添加控件模板的图标和名称<br>
