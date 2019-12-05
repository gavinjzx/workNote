# 1.js命名规范
## 1.1 变量
命名方法: 小驼峰式命名法  
命名规范：前缀为形容词 （函数前缀为动词, 以此来区分函数和变量）
>### 好的命名方式  
```
let maxCount = 10;  
let tableTitle = '啦啦啦';  
```
>### 不好的命名方式 
``` 
let setConut = 10;  
let getTitle = '啦啦啦';  
```

## 1.2 常量
命名方法：名词全部大写  
命名规范：使用大写字母和下划线来组合命名，下划线用来分割单词。
```
 const MAX_COUNT = 10;  
 const URL = '//www.huifenqi.com';  
```

## 1.3 函数 & 方法
命名方法： 小驼峰式命名法  
命名规范： 前缀应该为动词  
命名建议：常用动词约定   

 | 动词 | 含义 | 
 | -- | -- | 
 | can | 判断是否可执行某个动作 | 
 | has | 判断是否含义某个值 | 
 | is | 判断是否为某个值 | 
 | get | 获取某个值 | 
 | set | 设置某个值 | 
 | load | 加载某些数据 | 
 | handle | 处理某些事件 | 

```
 // 是否可阅读  
  function canRead() {}  
 // 获取名称  
 function getName() {}  
 ```
## 1.4 类 & 构造函数
命名方法：大写驼峰式命名法，首字母大写。  
命名规范：前缀为名称。
```
class Persion {
  constructor(name) {
   ...
  }
}
let person = new Person('啦啦啦');
```
## 1.5 类的成员
类的成员包括：  
> a.公共属性和方法： 跟变量和函数命名一样。  
> b.私有属性和方法：前缀为下划线_, 后面跟公共属性和方法一样的命名方式。
```
class Person {
  // 私有属性 
  _name: string;
  constructor() { }

  // 公共方法
  getName() {
    return this._name;
  }
  // 公共方法
  setName(name) {
    this._name = name;
  }
}
```
## 1.6 注释规范
格式化插件推荐：prettier  
注释插件推荐：korofileheader  
[korofileheader 使用参考网址](https://www.cnblogs.com/zouzhongxing/p/10785363.html)   
### 1.6.1 单行注释
```
// 设置标题
setTitle()
```
### 1.6.2 多行注释
```
/*
 * 代码执行到这里后会调用setTitle()函数
 * setTitle()：设置title的值
 */
setTitle();
```
### 1.6.3 函数 & 方法注释
```
/**
 * 函数说明
 * @关键字
 **/
```
常用关键字注释  

 | 注释名 | 语法 | 含义 | 示例 | 
 | :------: | :------: | :------: | :------: | 
 | @param | @param {参数类型} 描述信息 | 描述参数 | @param {String} name 传入名称 | 
 | @return | @return {参数类型} 描述信息 | 描述返回值 | @retun {Boolean} true: 可执行; false: 不可执行 | 
 | @author | @author 描述信息 | 描述作者 | @author 某某某 2018/04/24 | 
 | @example | @example 示例代码 | 演示函数的使用 | @example setTitle('啦啦啦'); | 

标准示范：
```
/**
* @description: listData控件载入数据后执行的回调函数
* @param res { string }
* @param page { number }
* @author  邹中兴
* @创建日期  2019 / 11 / 12
* @return: 无
*/
loadedData(res, page) {}
```
### 1.6.4 文件头部注释
```
/*
 * @Author: 作者
 * @Date: 2019-11-05 10:01:13
 * @LastEditors: 最后的编辑
 * @LastEditTime: 2019-11-15 09:07:34
 * @Description: 我的苗圃首页
 */
```

# 2. vue项目规范
## 2.1 目录结构
参考以下目录结构
```
src
├─assets 静态资源目录
│  ├─fonts 字体目录 
│  ├─img 图片
│  │  ├─...
│  │  └─status
│  └─scss 公用样式表
│      ├─layout 公用布局
│      ├─mintui mintui的一些重载
│      ├─mixin 
│      └─widget 小器件
├─components 公用级件，置于src目录下，组件目录采用Pasal帕斯卡命名方式
│  ├─BaiduMap 百度地图
│  ├─Common 公用控件
│  ├─Footer 底部
│  ├─Form 表单
│  ├─Listone 单个列表元素
│  └─Selector 公用选择器
├─config 公用配置
├─store  vuex store目录 
│  └─modules
│      ├─chat 会话
│      └─form 表单状态
├─utils 有用的小工具函数
└─views 业务逻辑目录，目录统一小写单词。如果单一单词描述不清，用小写单词连接
    ├─account 用户中心
    │  ├─authcation 用户认证
    │  ├─components 用户中心的公用组件
    │  │  ├─Form
    │  │  ├─Listone
    │  │  └─Selector
    │  ├─home 用户中心首页
    │  │  ├─……
    │  │  └─components
    │  └─wallet 钱包
    ├─…… 其他业务逻辑目录
    ├─supply 其他业务逻辑目录
    └─icon 图标示例
```
## 2.2 风格参考
[参考官网风格指南](https://cn.vuejs.org/v2/style-guide/)
## 2.3 性能优化
### 2.3.1 尽量少使用watch,而使用事件监听
### 2.3.2 为防止首页文件过大导致首屏加载过慢，引用插件时需要按需引入。
举个栗子：  
[vue+elementui按需引入](https://www.cnblogs.com/zouzhongxing/p/10168912.html)
