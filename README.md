# picker

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

# 代码中引用组件
import AwesomePicker from './components/Picker/vue-awesome-picker'

# 文件中使用组件方法
调用开源组件vue-awesome-picker，修改了部分样式
vue-awesome-picker的使用请查看：https://segmentfault.com/a/1190000013696869
原组件项目地址：https://github.com/Fyerl/vue-awesome-picker
在原组件上支持配置副标题
 <awesome-picker 
        ref="picker"
        :subTitle="picker.subTitle"     
        :data="picker.data"
        :anchor="picker.anchor"
        :textTitle="picker.textTitle"
        :textConfirm="picker.textConfirm"
        :textCancel="picker.textCancel"
        :colorTitle="picker.colorTitle"
        :colorConfirm="picker.colorConfirm"
        :colorCancel="picker.colorCancel"
        :swipeTime="picker.swipeTime"
        @cancel="handlePickerCancel"
        @confirm="handlePickerConfirm">
</awesome-picker>


# 组件参数
```javascript
picker{
    data //数组形式数据，支持单列，多列，级联，时间，日期选择，具体格式参考原组件使用
    anchor	//默认滚动的锚点位置 index标识	
    type	//内置 picker 类型
    textTitle	//主标题文案
    subTitle  	//副标题文案		
    textConfirm	//confirm文案，默认确定
    textCancel	//cancel文案，默认 取消
    colorTitle	//标题 颜色		
    colorConfirm //	confirm 颜色
    colorCancel	 //cancel 颜色
    swipeTime	//滚动速度(better-scroll swipeTime)
}

# 组件返回函数
//点击确认执行函数
//this.value:[{"index":0,"value":"a"},{"index":2,"value":"C"}]
//返回picker选择的数据
confirm (v){
      this.picker.anchor = v
      this.value = v ? JSON.stringify(v) : null
}


//点击取消调用函数
cancel(){
    
}
