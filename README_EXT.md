# 补充说明

## 构建说明
1. config目录：环境配置目录
2. build目录: 开发构建具体相关的脚本

### config目录
1. 入口index.js，将开发、生产环境变量包装成数组
2. dev.env.js 开发环境变量配置
3. prod.env.js 生产环境变量配置

### build目录
#### 一,开发配置
1. 入口dev-server.js
2. 依赖关系：dev-server --> webpack.dev.conf --> webpack.base.conf --> conf/dev.env.js
3. webpack.base.conf: webpack的基本配置——输入、输出、加载、解析配置
4. webpack.dev.conf: 开发环境的扩展配置——插件，热加载(依赖dev-client.js)
5. dev-server: 开发服务器程序，使用webpack的api编译js,使用express做为服务器框架启动服务

#### 二，生产构建配置
1. 入口build.js
2. 依赖关系：build --> webpack.prod.conf --> webpack.base.conf --> conf/prod.env.js
3. 其余文件对照上述开发配置说明

#### 三，check-version,utils,vue-loader.conf三个js文件
1. check-version: build和dev-server启动时执行版本检查
2. utils: css文件等加载的助手
3. vue-loader.conf: sourcemap配置