## TODO: element-ui 精简整理未使用的组件


## 修改记录
- 2019.05.14 修改 Dialog，添加 transitionName 属性变量，支持自定义窗体组件的载入动画
- 2019.04.27 基于element-ui 2.8.2 定制 @m-cloud/element-ui 并发布至 npmjs


## Fork 项目与原作者同步
1. git clone fork的项目到本地
2. 进入项目目录，增加源分支地址项目远程分支列表中
   - git remote -v 查看
   - git remote add [myName] [Source URL]
3. fetch 源分支到本地
   - git fetch [myName]
4. 合并两个版本的代码
   - git merge [myName]/master 或 git rebase [myName]/master
5. 解决冲突，提交代码
   - git push origin master


## 修改方法

### 定制 @m-cloud/element-ui
- 注意：修改版本号有 package.json 和 src/index.js 
- 修改 build/config.js 添加 alias '@m-cloud/element-ui': path.resolve(__dirname, '../')
- 修改 build/config.js 替换 externals 路径 [@m-cloud/element-ui/lib]
- 修改 src/** 目录所有引用路径 [@m-cloud/element-ui/lib]
- 打包 yarn dist
- 登录 npmjs 官网，创建 m-cloud 组织，让依赖库自动归类，详见：npm 发布 package
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

### 修改 Dialog，添加 transitionName 属性变量
```
:name="transitionName"

transitionName: {
  type: String,
  default: 'dialog-fade'
}

```
