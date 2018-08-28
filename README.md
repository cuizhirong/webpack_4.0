# webpack_4.0

`webpack`作为一个模块打包器，主要用于前端工程中的依赖梳理和模块打包。在webpack中一切皆是模块。
Plugins：拓展插件，在`webpack`构建流程中的特定时机注入扩展逻辑来改变构建结果或者做你想做的事情。

# webpack打包流程
1. 根据传入的参数模式(`development` | `production`)来加载对应的默认配置
2. 在`entry`中配置`module`开始递归解析`entry`所依赖的所有`module`
3. 每一个`module`都会根据`rules`的配置项去寻找用到的`loader`, 接受所配置的`loader`的处理
4. 以`entry`中的配置对象分组，每一个配置入口和其对应的依赖文件最后组成一个代码块文件(chunk)并输出
5. 整个流程中webpack会在恰当的时机执行`plugin`的逻辑，来完成自定义的插件逻辑

```
function name() {}
```
