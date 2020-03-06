# es-vue

> vue+es

# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev


# 配置VSCode保存格式化
1. 安装插件 eslint、prettier、vetur
2. 创建 .eslintrc.json 或者 .eslintrc.js
3. vscode setting.json
```json
// "eslint.autoFixOnSave": true, //注：已经废弃
// 下面两项一般配合使用，也就是没有eslint规则时，使用自定义的格式化
"editor.formatOnSave": true, // 每次保存的时候自动格式化
"editor.defaultFormatter": "esbenp.prettier-vscode",// 自动格式化以prettier为准
// 保存时按照 .eslintrc.json 或者 .eslintrc.js 格式化；
// 与上面 editor.formatOnSave 互斥，使用下面的时最好关掉编辑器保存格式化
"editor.codeActionsOnSave": {
    "source.fixAll": true,
    "source.fixAll.eslint": true
}
```
 

## Pre-commit
pre-commit钩子可以在 git commits 之前运行一段脚本
比如在commit代码之前运行eslint，校验失败则代码提交失败，校验成功则允许提交代码
npm install --save-dev pre-commit
package.json
"scripts": {
  "precommit-msg": "echo 'Pre-commit checks.........' && exit 0",
  "lint": "eslint --ext .js --ext .jsx src"
},
"pre-commit": ["precommit-msg", "lint"]

用pre-commit定义commit之前，执行两条命令
precommit-msg：输出一些信息避免信息混淆
lint：使用eslint校验代码