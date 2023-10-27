# carbon 文档主站
## 新增仓库流程
### 创建 github 仓库
在 github 上新建文档仓库，然后将项目 clone 到本地。
### 配置仓库
新建 .gitignore，加入下面的内容
```
node_modules/
dist/
package-lock.json
```
新建package.json，加入下面的内容
```json
{
  "scripts": {
    "build": "loppo --site \"[xxx] 脚本教程\" --id [xxx] --theme wangdoc",
    "chapter": "loppo chapter",
    "commit": "gh-pages --dist dist --dest dist/[xxx] --branch master --repo https://github.com/welltan/carbon-doc-website.git",
    "server": "loppo server"
  },
  "devDependencies": {
    "loppo": "^0.6.25",
    "loppo-theme-wangdoc": "^0.6.4",
    "gh-pages": "^3.2.3"
  }
}
```
gh-pages 库的主要作用是将项目文件 push 到目标仓库。可以使用 npx gh-pages --help 来查看 gh-pages 命令的用法。
npm run chapter 可以生成目录文件 chapters.yml，生成后可以手动修改此文件。

 