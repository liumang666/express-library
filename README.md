# MDN 文档

https://developer.mozilla.org/zh-CN/docs/Learn/Server-side/Express_Nodejs/skeleton_website

# 使用 express 生成器

npm install express-generator -g

# 新建文件夹 express-library

cd express-library

# 使用 Pug 模板库

express --view=pug

# 安装依赖

pnpm i

# 启动服务(修改文件需要手动启动服务器 --- 下面的方法可以自动启动服务器)

DEBUG=express-library:\* & pnpm start

## 一个 Express 应用就配置成功了，它托管于 localhost:3000。

# 文件改动时重启服务器

只有重启服务器才能看到 Express 网站所做的改动。每次改动后手动启停服务器实在太烦人了，有必要花点时间让这项工作自动化。
[nodemon](https://github.com/remy/nodemon) 是最简便的自动化工具之一

pnpm add --save-dev nodemon

# 找到 package.json 的 scripts 部分。在 "start" 一行的末尾添加逗号，并在新的一行中添加 "devstart"，如下所示：

```javascript
"scripts": {
    "start": "node ./bin/www",
    "devstart": "nodemon ./bin/www"
  },
```

# 现在可以用新建的 devstart 命令启动服务器：

DEBUG=express-library:\* pnpm devstart
