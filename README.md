## 技术

- node
- cookie-parser : "~1.4.3"
- crypto : "^1.0.1"
- express: "~4.16.0"
- express-session : "^1.15.6",
- http-errors : "~1.6.2",
- mongodb : "^3.1.8",
- mongoose : "^5.3.7",
- mongoose-auto-increment : "^5.0.1",
- yargs : "^12.0.2"

## 注意点

- 文章是分类型的：文章类型 => 1: 普通文章，2: 简历，3: 管理员介绍；而且简历和管理员介绍的文章只能是各自一篇（因为前台展示那里有个导航 关于我 ，就是请求管理员介绍这篇文章的，简历也是打算这样子用的），普通文章可以是无数篇。
- 点赞的用户 like_users 那里应该只保存用户 id 的，这个后面修改一下。
- 评论功能是实现了简单的三级评论的，第三者的评论（就是别人对一级评论进行再评论）放在 other_comments 里面。
- 评论是有状态的：状态 => 0 待审核 / 1 通过正常 / -1 已删除 / -2 垃圾评论。
- 管理一级和三级评论是设置前台能不能展示的，默认是展示，如果管理员看了，是条垃圾评论就 设置为 -1 或者 -2 ，进行隐藏，前台就不会展现了。

## Build Setup ( 构建安装 )

```
# install dependencies
npm install

# serve with hot reload at localhost: 3000
npm start

# build for production with minification
请使用 pm2 ，可以永久运行在服务器上，且不会一报错 node 程序就挂了。
```
