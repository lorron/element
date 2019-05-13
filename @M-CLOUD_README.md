## 定制 @m-cloud/element-ui
- 注意：修改版本号有 package.json 和 src/index.js 
- 修改 build/config.js 添加 alias '@m-cloud/element-ui': path.resolve(__dirname, '../')
- 修改 build/config.js 替换 externals 路径 [@m-cloud/element-ui/lib]
- 修改 src/** 目录所有引用路径 [@m-cloud/element-ui/lib]
- 打包 yarn dist
- 登录 npmjs 官网，创建 m-cloud 组织，让依赖库自动归类
- 发布 npm publish --access public 发布带@符号的公共包
- 发包文件白名单设置package.json中的files属性。如：
```
"files": [
    "lib",
    "src",
    "packages",
    "types"
  ],
```

* TODO: element-ui 精简整理未使用的组件
