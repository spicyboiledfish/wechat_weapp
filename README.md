# wechat_weapp
微信小程序开发，目前会记录每次学习过程中的重点...

## 8.2 基本微信小程序独有的写法规则：
* 微信小程序中flex的属性
    1. flex-grow 放大比例
    2. flex-shrink 缩小比例
    3. flex-basis  占据的空间
* rpx单位，是微信小程序独有的单位
* 在微信小程序中，flex布局的默认是横向布局 row.(而在React Native中是默认为纵向column)
* wxss文件目前无法支持通配符 * 的使用

## 8.6 如何动态改变状态值：
```
Page({
  //页面初始化数据：  
  data: {
    userInfo: {},
    hasUserInfo: false,
  }
  ...
});
```
```
this.setData({
    userInfo: res.userInfo,
    hasUserInfo: true
})
```
## 8.7 常用的微信小程序组件使用：
* 表单组件：button, checkbox, input, label, picker, radio, slider,switch,form
* 基础组件：progress, icon, text, swiper, scroll-view, view
* 操作反馈小工具：action-sheet, modal,toast, loading
* navigator跳转的两种方式：
    1. 在wxml文件中的view中绑定事件，js文件中添加事件：
    ```
    bindViewTap:function(){
	    wx.navigateTo({
		    url:”../logs/logs”
	    })
    }
    ```
    2. 直接在wxml文件中直接在view外层用<navigator></navigator>进行包裹:
    ```
    <navigator url=“../logs/logs” redirect>
	    <view>
		    <text>按钮</text>
	    </view>
    </navigator>
    ```
    ```
    1. 属性用url：（用于页面跳转）
    2. 属性redirect：是否替换到当前的页面（将路由栈清除，新添加了路由首页面）; 界面上就是左上角没有返回按钮了
    ```
* 渐变色样式写法：
```
background: -webkit-linear-gradient(bottom, rgba(0,0,0,0.8), rgba(0,0,0,0));
```
