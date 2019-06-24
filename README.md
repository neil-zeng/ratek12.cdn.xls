# ratek12.cdn.xls

为心理所提供免费CDN服务
## 实现原理

Github 做 CDN 存储，jsDelivr 做 CDN 服务器, TravisCI 做自动更新。

## 流程

1. 本地添加文件到 Git，推送到 Github，触发 TravisCI 执行构建；
1. TravisCI 拉取最新 Github 文件，打 Tag，发布到 Github Release, 将新版本文件推送回 Github；
1. 用户访问 jsDelivr 的 CDN 服务器，jsDelivr 到 Github Release 拉取对应版本或者最新版本文件，返回给用户；
1. 本地更新文件，如此往复触发第一步。

