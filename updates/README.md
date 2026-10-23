# 发布 GPU 任务台客户端更新

更新窗口读取此目录的 `gpu-queue-widget.json`。只发布 Mac 客户端安装包，任务和队列数据继续保存在个人服务器。

1. 在客户端项目的 `launchers/macos/widget/release.json` 中提高三段版本号，并写好更新说明。
2. 运行 `python3 scripts/package-widget.py`，生成安装包、版本信息和 SHA-256。
3. 将产物目录下的 `downloads/GPU-Queue-Widget-<版本>-macOS.zip`、`downloads/GPU-Queue-Widget-macOS.zip`、`downloads/SHA256SUMS` 和 `updates/gpu-queue-widget.json` 在同一次提交中推送到本仓库 main；同步更新主页版本和下载入口。
4. 已发布的版本文件保持不变；修改代码后发布新版本，不覆盖同一版本的内容。

客户端启动时和每隔 6 小时检查，用户也可点击“检查更新”。发现新版后，用户点击“下载并安装”才下载、校验和安装。更新源限定为本仓库的 HTTPS 版本文件；更新信息中的大小、SHA-256 和安装包内版本必须一致。
