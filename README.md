## 简介

通过v-model绑定当前激活tab对应的索引值，默认情况下启用第一个tab。
当tabs长度超过屏幕宽度，则支持在水平方向上滚动。切换时，选中tab自动居中。

## 用法
*详见示例项目：https://github.com/yapeee/uni-components*

#### 基本用法

```
<ms-tabs :list="list" v-model="active"></ms-tabs>

<script>
  export default {
    data() {
      return {
        type: [{
        	title: 'test1'
			}, {
        	title: 'test2'
			}],
		active: 0
      }
    },
	watch:{
		active() {
			console.log(this.active)  // 0
		}
	}
  }
</script>
```

#### 下划线滑动效果

```
<!-- 下划线不设置滑动效果 -->
<ms-tabs :list="list2" v-model="active2" :lineAnimated="false"></ms-tabs>

<script>
  export default {
    data() {
      return {
        list2: [{
        		title: 'test1'
        	}, {
        		title: 'test2'
        	},{
        		title: 'test3'
        	}, {
        		title: 'test4'
        	},{
        		title: 'test5'
        	}, {
        		title: 'test6'
        	},{
        		title: 'test7'
        	}, {
        		title: 'test8'
        	}
        ],
		active2: 0
      }
    },
	watch:{
		active2() {
			console.log(this.active2)  // 0
		}
	}
  }
</script>
```

#### 动态渲染数据
```
<ms-tabs :list="list3" v-model="active3" ></ms-tabs>
<view class="btn" @click="setTabsValue">获取数据</view>

<script>
  export default {
    data() {
      return {
        list2: [{
        		title: 'test1'
        	}, {
        		title: 'test2'
        	},{
        		title: 'test3'
        	}, {
        		title: 'test4'
        	},{
        		title: 'test5'
        	}, {
        		title: 'test6'
        	},{
        		title: 'test7'
        	}, {
        		title: 'test8'
        	}
        ],
		list3: [],
		active3: 0
      }
    },
	methods: {
		setTabsValue() {
			this.list3 = this.list2
			this.active3 = 4
		}
	}
  }
</script>
```

## 属性说明

| 参数         | 说明                    | 类型    | 默认值             |
| ------------ | ----------------------- | ------- | ------------------ |
| value      | 当前选中项对应的下标值，可以通过v-model双向绑定 | number \| String | 0               |
| list         | 绑定tabs栏数据          | Array   | []                 |
| itemColor    | tab选中颜色             | String  | $uni-color-primary |
| lineColor    | 下划线颜色              | String  | $uni-color-primary |
| lineAnimated | 是否展示下划线滑动效果  | Boolean | true              |

