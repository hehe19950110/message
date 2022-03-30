message消息信息组件

1、:hover CSS伪类适用于用户使用指示设备虚指一个元素（没有激活它）的情况。:hover伪类可以任何伪元素上使用。
这个样式会被任何与链接相关的伪类重写，为了确保生效，:hover规则需要放在:link和:visited规则之后，但是在:active规则之前.

按照LVHA的循顺序声明:link－:visited－:hover－:active。

2、 在script里创建一个render，用来显示message跳出的div盒子（弹窗及内容）。
```
render(){
let $div = document.createElement('div')
this.$message = $div
$div.classList.add('message')
document.body.appendChild($div)
   }
```


3、 在script里创建一个绑定事件bind，用来展示div盒子及消失div盒子。
```
bind() {
    setTimeout(()=> this.show(),0)
    setTimeout(() => this.destory(), 3000) /*3000表示3000毫秒;从0到3秒，产出页面滑动的效果*/
  }

show() {
    this.$message.classList.add('show')
  }

destory() {
    this.$message.classList.remove('show')
    setTimeout(() => this.$message.parentNode.removeChild(this.$message), 3000)
  }
```

4、opacity属性指定了一个元素的不透明度,，opacity属性指定了一个元素后面的背景的被覆盖程度。
```
/* 完全不透明 */
opacity: 1;
opacity: 1.0;

/* 半透明 */
opacity: 0.6;

/* 完全透明 */
opacity: 0.0;
opacity: 0;
```
