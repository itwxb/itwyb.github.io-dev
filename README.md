# aaron.blog

## 简介

- 使用vue.js开发
- 通过gihtub api读取issues和各个仓库的信息
- 代码部署成功后，无须类似hexo每次写新文章需要本地生成发布，直接放到issues里即可，自带评论功能
- 需要将我的名称和仓库地址改为你的 文件为 src/config.js deploy.sh 
- 如果没有yarn 需要安装a
## 开发部署

- 安装包

```
yarn install
```

- 启动

```
yarn serve
```

- 构建
 
```
yarn build
```

- 检查

```
yarn lint
```

- 部署到github上

```
yarn deploy
```
