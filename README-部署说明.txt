健康记录 healthlog —— 静态部署包
====================================

目录内容（全部是静态文件，不需要服务器脚本）：
  index.html              主程序（单文件，含全部逻辑与样式）
  manifest.webmanifest    安装信息（App 名称、图标、启动方式）
  sw.js                   离线缓存（Service Worker）
  icon-192.png            图标 192
  icon-512.png            图标 512
  icon-maskable-512.png   自适应图标

怎么发布成永久地址（三选一，都免费）：

【A】GitHub Pages（推荐，无需命令行）
 1. 注册 github.com（邮箱 + 密码，几分钟）
 2. 新建仓库，名字填 healthlog，选 Public，创建
 3. 进入仓库 → Add file → Upload files → 把本目录所有文件拖进去 → Commit
 4. Settings → Pages → Source 选 Deploy from a branch，
    Branch 选 main、目录选 / (root) → Save
 5. 等 1 分钟，地址就是：
    https://<你的用户名>.github.io/healthlog/
 6. 手机打开该地址 → 「数据 → 安装到桌面」

【B】Cloudflare Pages
 1. 注册 dash.cloudflare.com（可用邮箱一键登录）
 2. Workers & Pages → Create → Pages → Upload assets
 3. 把本目录所有文件拖进去 → Deploy
 4. 得到 https://healthlog.pages.dev（可自定义项目名）

【C】Netlify Drop
 打开 app.netlify.com/drop，把整个目录拖进去，立刻得到一个 *.netlify.app 地址。
 无需注册即可测试；长期使用建议注册认领，否则站点可能被回收。

注意事项：
 1. 一定要用 https 地址打开，浏览器才允许把页面缓存到手机本地。
 2. 换地址 = 换 origin = 手机上是全新的空 App，
    旧数据要先在旧 App 里「数据 → 备份 JSON」导出，再在新地址「从 JSON 备份恢复」。
 3. 更新版本时，保持同一个域名，只替换文件即可，数据不会丢。
