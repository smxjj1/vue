vue on 指令

 change value 
 <button @keydown='change'>change value </button> 简写形式
 阻止默认行为

 <form @sumit.prevent action = "http://itcast.cn">
 <input type="submit" /> 阻止表单的默认行为
 </form>

 var vm = new Vue({
	el:'#app', //表示当前vue对象接管app的div区域
	data: {
		name:'相当于是MVVM中的Model这个角色'  // 相当于是MVVM中的Model这个角色
	},
	methods:{
	    change:function(){
	        this.name+="1";
	    }
	}
});

v-text,v-html,v-cloak;解决在vue.js 文件加载较慢的时候,先显示{{变量}} 而不是解析成相应值得问题;
v-text 将标签变成文本输出
v-html 将标签变成html文档输出

<div v-text = "name"> </div>

将name 的值输入到div标签里面

v-bind 给某一个标签属性动态添加值
完整写法：
<input type="text" v-bind:value="name"/>
简写方法：
<input type="text" :value="name"/>
动态生成href的值：
跳转

n-model的双向数据绑定：
使用的对象：
1、在表单控件或者组件上创建双向绑定
  2、v-model仅能在如下元素中使用：
     input
     select
     textarea
     components（Vue中的组件）
  4、修饰符（了解）：
      .lazy - 取代 input 监听 change 事件
      .number - 自动将输入的字符串转为数字(input标签输入的值默认为string
      加上number 之后变为 number)
      .trim - 自动将输入的内容首尾空格去掉
<input type="text" v-model.trim="uname" />

<script>
new Vue =( {
     el:"#app",
    data:{
        msg:'hahaha'
    }
})
v-for 遍历数组 跟 ng-repeat 一样的作用
<li v-for="(index,item) in arr">{{item}}--{{index}}</li>
1.0版本 索引在前  2.0 索引在后面且没有$index 这个值；



v-if 和 v-show 的指令系统指令
v-if 和 v-show 都能显示和隐藏的操作，v-if的操作在DOM上添加和移除操作的，v-show是在样式上添加display：none 来显示隐藏的；

//实现品牌列表数据展示
设计思路：
v-for 遍历数据
设计数据
list：[{
        id:
      name:
      time：
            }]
v-for在tr上执行：
实现思路：
1、将表格的静态结构样式
2、vue填充数据 

删除所用的新函数:
提醒用户if(!confirm('是否要删除数据？')){
    retrun;
}
list.findindex(function(item){retrun item.id==要删除数据的id})
删除list.splice(删除的索引,删除的元素个数)
