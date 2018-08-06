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
 ....
});
this.setData({
    userInfo: res.userInfo,
    hasUserInfo: true
})
```
    
