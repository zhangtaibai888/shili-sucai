# 素材拍摄示例页（给客户看的短视频素材教学链接）

一个零成本的静态网页：客户打开链接就能看到"拍摄建议 + 示例视频"，你自己在网页管理后台上传视频、改文字、管分类。

## 文件结构

```
示例素材教学页/
├── index.html      主页面（访客端 + 管理后台，单文件）
├── content.json    页面文字 + 分类 + 管理密码
├── videos.json     视频清单（分类/标题/说明）
├── videos/         示例视频放这里（或后台直接上传）
└── images/         预留，暂不需要
```

## 部署步骤（约 10 分钟，免费）

1. 打开 https://github.com ，登录后点右上角 **+ → New repository**
   - Repository name 随便填英文，例如 `shili-sucai`；**Public** 即可（选 Private 也没关系）
   - 创建完成后，把本文件夹里的 `index.html`、`content.json`、`videos.json`、`videos/` 都上传进仓库（仓库页 → Add file → Upload files，拖进去即可）
2. 开启网页：仓库页 → **Settings → Pages** → Source 选 **Deploy from a branch**，Branch 选 `main` 和 `/ (root)` → Save
3. 等 1 分钟，页面显示绿色链接，打开就是你的分享链接：
   `https://你的用户名.github.io/shili-sucai/`
4. 把这个链接发给客户即可。

## 管理后台怎么用

1. 管理入口不会显示在客户页面上。打开**管理地址**：在页面网址末尾加 `#admin`
   例如 `https://你的用户名.github.io/shili-sucai/#admin`，输入密码（默认 `admin`）
2. 第一次进后台先做 **连接配置**：
   - 仓库地址填 `你的用户名/仓库名`（例如 `zhangsan/shili-sucai`）
   - GitHub Token 获取方式：GitHub → 右上头像 → Settings → Developer settings → Personal access tokens → Generate new token（选 Fine-grained 或 classic 都行，权限勾选该仓库 Contents 的 **Read and write**）→ 生成后复制粘贴
   - Token 只存在你自己浏览器的本地存储里，不经过任何服务器
3. 之后就可以：
   - **上传视频**：拖拽或点击选择 → 填标题、选分类 → 上传（有进度条）
   - **视频列表**：改名、换分类、删除
   - **分类管理**：新增、改名、删除
   - **页面文字**：拍摄建议、页脚、管理密码
   - 改完刷新分享链接即可看到最新内容

## 注意事项

- 视频建议 mp4（H.264）格式，单个不超过 50MB（GitHub 单文件上限 100MB）
- 客户打开页面无需登录，只能看，不能改；页面上没有任何管理入口
- 管理地址（`#admin`）只在你自己手里，不要发给客户
- 管理后台里"分享给客户"一栏可以一键复制客户链接和管理地址
- "管理密码"只是界面的一道门，真正的保护是 GitHub Token——Token 永远不要发给别人
- 管理功能需要网页跑在 GitHub Pages（https）环境下；本地双击打开 html 只能预览访客端效果
- 换电脑/换浏览器后管理后台需要重新填一次 Token（配置存在浏览器本地）
