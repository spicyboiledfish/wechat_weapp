# wechat_weapp
微信小程序开发，目前会记录每次学习过程中的重点...

## 8.2 基本微信小程序独有的写法规则：
* #### 微信小程序中flex的属性
    1. flex-grow 放大比例
    2. flex-shrink 缩小比例
    3. flex-basis  占据的空间
* #### rpx单位，是微信小程序独有的单位
* #### 在微信小程序中，flex布局的默认是横向布局 row.(而在React Native中是默认为纵向column)
* #### wxss文件目前无法支持通配符 * 的使用
* #### 微信小程序中的所有属性及方法基本上都是小写字母，也没有出现驼峰命名法则，都是以-替代

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
* #### 表单组件：button, checkbox, input, label, picker, radio, slider,switch,form
* #### 基础组件：progress, icon, text, swiper, scroll-view, view
* #### 操作反馈小工具：action-sheet, modal,toast, loading
* #### navigator跳转的两种方式：
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
* #### 渐变色样式写法：
```
background: -webkit-linear-gradient(bottom, rgba(0,0,0,0.8), rgba(0,0,0,0));
```
* #### 循环遍历的结构写法：
```
<view wx:for="{{content-items}}">
    ....		
</view>
```
* #### 如何让一个盒子内两个子元素在横向布局中一个靠左一个靠右：
```
div{
   display: flex;
   justify-content: space-between;
}
```
* #### image组件：主要有两个属性
     1. src：图片路径属性
     2. mode：图片展示模式属性（scaleToFill 充满容器，会变形；aspectFit  保持原图比例，会有空白；3. aspectFill  保持原图比例，充满容器，只保证         图片的短边会完全显示）
* #### audio音频组件：主要的两个属性
     1. action：控制音频的播放、暂停、播放速率
     2. src：音频资源的播放地址
     ```
     this.setData({
	action: {
		method:’play’     //播放（暂停是pause）
	     }
	})
     ```
## 8.8 微信小程序API：
* #### wx.playBackgroundAudio(object) 播放音频  
* #### wx.pauseBackgroundAudio(object) 暂停音频
* #### wx.removeStorage 删除key所对应的本地存储
* #### wx.getStorage 获取key所对应的本地存储数据
* #### wx.setStorage 设置key所对应的本地存储数据
