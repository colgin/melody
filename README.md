# Melody

## 项目介绍

<img src="./imgs/melody.png" width="100" ></img>

大家好，我叫 Melody，是你的音乐精灵，旨在帮助你更好地管理音乐。目前的主要能力是帮助你将喜欢的歌曲或者音频上传到音乐平台的云盘。

为了避免不必要的纠纷和账号安全问题，本项目不会以任何形式提供在线 demo 服务，也请大家不要使用公共服务。本地部署很简单。

## Feature

- 支持在各大音乐和视频网站检索歌曲。目前支持 咪咕、网易云、QQ 音乐、酷狗、bilibili 等站点。详情可以在我的 [media-get](https://github.com/foamzou/media-get#%E6%94%AF%E6%8C%81%E7%9A%84%E7%BD%91%E7%AB%99) 项目中查看
- 用链接搜索歌曲
- 一键“解锁”无法播放的歌曲（实验性功能，目前仅支持网易云）

## 安装和启动

### 依赖

确保以下两个依赖是安装好的

1. node >= v14.19 ([官网下载](https://nodejs.org/zh-cn/download/))
2. FFmpeg ([windows 安装介绍](https://zhuanlan.zhihu.com/p/400952501))

### 下载源码及初始化服务

其中 init.js 会下载核心组件，初始化 node 依赖，尽可能不需要你关心安装细节

```
git clone https://github.com/foamzou/melody.git
cd melody
node init.js
```

### 配置你的账号

```
cp backend/.profile/accounts.sample.json backend/.profile/accounts.json
```

然后编辑 `backend/.profile/accounts.json` 。

1. 该 JSON 中的 key 是 `Melody Key`，是你在网页访问该服务的唯一凭证
2. 网易云账号信息： `account` 和 `password` 可以后续在网页修改
3. 该 JSON 是个数组，支持配置多个账号

### 启动服务

> 建议使用 pm2 将本服务常驻后台

```
node backend/src/index.js
```

最后，在浏览器访问 http://127.0.0.1:5566 就可以使用啦~

## 功能介绍

### 关键词搜索歌曲

如果试听后是你想要的，点击上传按钮会将该歌曲上传到你的网易云音乐云盘
<img src="./imgs/1-home-search-keyword.png" width="1000" ></img>

### 链接搜索

有时候我们在 b 站 听到好听的歌，也可以上传到云盘
<img src="./imgs/2-home-search-url.png" width="1000" ></img>

### 一键解锁歌单

点击 `解锁全部`（实验性功能） 后，服务会自动匹配每首歌，并把歌曲上传到云盘，最后做个 match，以保证你还能看到歌词、评论
<img src="./imgs/3-playlist.png" width="1000" ></img>

### 手动搜索匹配

当某首歌自动解锁失败后，还可以手动点击搜索按钮，找到符合的歌曲后，手动点击上传按钮
<img src="./imgs/4-playlist-search.png" width="1000" ></img>

## Roadmap

计划在后面支持以下功能

- [ ] 页面适配移动端
- [ ] 浏览器油猴脚本
- [ ] 云盘歌曲 match 手动纠错
- [ ] 支持播放列表
- [ ] 支持播放云盘的歌曲
- [ ] 支持 docker 部署
- [ ] 支持 youtube-dl,you-dl 等工具作为输入源
- [ ] 支持 酷狗、qq 音乐等音乐平台的云盘作为输出
- [ ] 偏好设置
- [ ] 版本更新提示

## Change log

- 2022/05/04: 发布 MVP 版本

## 致谢

- [NeteaseCloudMusicApi](https://github.com/Binaryify/NeteaseCloudMusicApi) 的网易云 API
- [MakeGirlsMoe](https://make.girls.moe/) 生成的 Melody 虚拟形象图片
- [Media Get](https://github.com/foamzou/media-get) 我的开源项目

## 赞赏

如果我的任何开源项目帮助到了你，都可以考虑请我喝杯奶茶呀~

<img src="./imgs/billing.jpeg" width="220" ></img>
