# es-vue

> vue+es

# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev


## 配置保存格式化按照eslint.json
1、vscode setting.json
"editor.codeActionsOnSave": {
    "source.fixAll": true,
    "source.fixAll.eslint": true
}
注： "eslint.autoFixOnSave": true, //废弃

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