# vue-dialog
A drag-able dialog for Vue.js

基于Vue.js V2的弹框组件

[查看jquery版本](https://github.com/mjixiang/ui.prompt)

## example
地址：https://mjixiang.github.io/vue-dialog


## props
```html
<dialog 
	v-model="dialog.show" 
	:title="dialog.title"
	:buttons="dialog.buttons"
	@cancel="onCancel"
	@onbtnclick="onDialogBtnClick">
	<!--窗体主体内容-->
</dialog>
```
>`title`:`Object | String` 弹框标题，需要，自定义弹框标题和样式

>`buttons`:`Array` 按钮，可选，自定义弹框下方按钮样式、文本、事件

## data
```javascript
data: {
	dialog:{
		show:false,
		title:{
			text:'这个是标题（可拖拽）',
			className:'xa-bg-red'	//标题样式类名，包含`background`、`color`即可
		},
		buttons:[
			/**
				`@text`：按钮文字
				`@className`：按钮样式类名，包含`background`、`color`即可（内置一部分）
				`@clickEvent`：按钮点击事件后监听的事件名
			*/
			{text:'关闭',className:'xa-bg-red-click',clickEvent:'cancel'},
			{text:'确定',className:'xa-bg-blue-click',clickEvent:'confirm'}
		]
	}
}
```

## methods
```javascript
methods:{
	//buttons中定义的所有的`clickEvent`
	//可单独监听每个 buttons[i].clickEvent  或 监听 @onbtnclick 统一处理，第一个参数buttons[i]
	cancel () {
  		this.dialog.show = false;
	},
	onDialogBtnClick(btn){
		//do something
	}
}
```
