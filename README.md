# XiaoYuBotX SDK
### 筱雨机器人的插件SDK， 用于开发插件
## 使用方法
### 1. 下载SDK包
请在 [Release页面](https://github.com/xiaozhou233/XiaoYuBotX/releases/latest) 下载 sdk.jar (或有sdk关键字的jar文件)，放入 sdk目录中
### 2. 导入SDK包
#### IDEA
1. 打开项目
2. 打开`sdk`目录，右键点击`sdk.jar`，选择`Add as Library (添加为库)`

#### gradle
1. 编辑 `build.gradle`文件
2. 在 `dependencies`中添加 `implementation fileTree(dir: 'sdk', include: ['*.jar'])`或者
`implementation files('sdk/sdk(SDK文件名).jar')`

### 3. 编辑配置文件
1. 在 `src/resources`目录下有plugin.toml文件，编辑该文件，添加插件信息
- `PluginName` 插件名称
- `PluginVersion` 插件版本
- `MainClass' 插件主类 (继承plugin接口的类)

### 4. 编写插件
示例代码
```java
package org.example.plugin;

import cn.xiaozhou233.xiaoyubot.plugin;

//继承plugin接口
public class Main implements plugin {

    @Override
    public void onEnable() {
        // 插件加载时执行
    }

    @Override
    public void onDisable() {
        // 插件卸载时执行
    }
    
    @Override
    public void onMessage(String message) {
        // 收到消息时执行
    }
    
    // 处理事件
    @Override
    public void on<事件名称>(<事件参数>) {
        // 事件处理
    }
}
```
事件以及API在项目Wiki/文档中

### 5. 构建
### 注意: 构建时需要JDK11版本以上
运行 `./gradlew build`
插件将在/build/libs目录下生成


