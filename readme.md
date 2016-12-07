# LiycBeUI
 LiycBeUI是一个基于vue.js构建的组件库，用于快速地创建出后台管理界面(不含表单逻辑),当前版本0.0.1 beta。

## 使用说明
首先需要引入vue.js，然后再引入LiycBeUI.js。

### 遵循vue语法
只需要在你需要的Vue对象实例添加你所需要的LiycBeUI中的某个模块，并按对应模块的编写规则，填写你所需要的数据即可。目前仅有目录结构模块:LiycBeUI_Catalog


#### 目录结构模块(LiycBeUI_Catalog)
只需要向vue实例中的data添加一个items属性，这个属性是一个数组，它的元素为一个目录对象。目录对象代码示例如下:

``` js

	{
		title:'目录B',\\目录名称
		citems:['B1','B2','B3'],\\目录中的叶子目录
		flag:true\\必须为true，否则会出现问题
	}

```

B目录与A目录是同级关系则如下:
``` js

	{
		title:'目录B',
		citems:['B1','B2','B3'],
		flag:true
	}，
	{
		title:'目录A',
		citems:['A1','A2','A3'],
		flag:true
	}

```
B、C目录是A目录的子目录
``` js

	{
		title:'目录A',
		citems:[	
			{
				title:'目录B',
				citems:['B1','B2','B3'],
				flag:true
			}，
			{
				title:'目录C',
				citems:['B1','B2','B3'],
				flag:true
			}，
		],
		flag:true
	}

```


###  完整代码示例

``` js

	var test=new Vue({
		el:"#app",
		data:{
			items:[
				{
					title:'目录A',
					citems:[
						{	title:'A1',
							citems:['A1-1','A1-2','A1-3'],
							flag:true
						},
						{	title:'A2',
							citems:['A2-1','A2-2','A2-3'],
							flag:true
						},
						{	title:'A3',
							citems:[
								{	
									title:'A3-1',
									citems:['A3-1-1','A3-2-1','A3-3-1'],
									flag:true
								}
							],
							flag:true
						}
					],
					flag:true
				},
				{
					title:'目录B',
					citems:['B1','B2','B3'],
					flag:true
				},
				{
					title:'目录C',
					citems:['C1','C2'],
					flag:true
				}
			]
		},
		 components: {
	    	'lb-nav':LiycBeUI_nav
	  	}
	});


```

## 版本更新

0.0.1

- 增加后台管理界面常见的目录结构