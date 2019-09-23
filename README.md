# 基于EarthSDK、webpack和vue创建的极简App

## 简介

基于EarthSDK、webpack和vue创建的极简App，可以调试和打包。  
其中Vue以独立的js文件从外部引入，而不是以.vue文件引入。  

![预览](tools/images/preview.jpg)

注意：小项目可以使用这种方式，比较省事，大型项目最好用Earth-webapck-vue-App或者Earth-vue-cli-App这两个项目来构建。  

这个项目的缺点是，vue组件的创建，不能直接写xxx.vue文件，需要用js方式书写，类似下面这种形式：  

```
// 1 创建Earth的vue组件
var EarthComp = {
    template: `
        <div style="width: 100%; height: 100%">
            <div ref="earthContainer" style="width: 100%; height: 100%">
            </div>
            <div style="position: absolute; left: 18px; top: 18px">
                <button>{{ message }}</button>
            </div>
        </div>
    `,
    data() { 
        return {
            message: '页面加载于 ' + new Date().toLocaleString(),
            _earth: undefined, // 注意：Earth和Cesium的相关变量放在vue中，必须使用下划线作为前缀！
            _bgImagery: undefined,
        };
    },
    // ...
}

export default EarthComp;
```

## 使用方法

0. 安装
npm install

1. 调试
npm run dev

2. 打包
npm run build


