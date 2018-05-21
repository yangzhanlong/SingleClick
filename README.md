# SingleClick
## 安卓点击事件防重库

依赖本库，不用写任何代码，所有点击事件自动防重复点击；

对 butterKnife 自动生成的点击事件同样有效

默认防重复点击间隔 500ms

如果想自定义点击事件间隔，加上注解（参数单位ms）：
```
@SingleClick(1000)
public void onClick(View v) {
   ...
}
```

注解参数为0 表示取消防重 不写参数 默认500ms

ps：直接在布局里指定的点击事件无法做到自动防重，请打上注解

### 依赖方法:
#### To get a Git project into your build:
#### Step 1. Add the JitPack repository to your build file
1.在全局build里面添加下面github仓库地址

Add it in your root build.gradle at the end of repositories:
```
buildscript {
    ...
    dependencies {
	...
        classpath 'cn.leo.plugin:magic-plugin:1.0.0'
    }
}
allprojects {
	repositories {
		...
		maven { url 'https://jitpack.io' }
	}
}
```
google()和jcenter()这两个仓库一般是默认的，如果没有请加上

#### Step 2. Add the dependency
2.在app的build里面添加插件和依赖
```
...
apply plugin: 'cn.leo.plugin.magic' 

...
dependencies {
	implementation 'com.github.jarryleo:SingleClick:v1.0'
}
```
