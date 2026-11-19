# JiChuang Studio 授权配置

根目录 `config.json` 只管理旧版 1.2.6 的 GitHub 开关，当前为 `off`。
1.3.x 使用网站签名授权接口，不读取这个 GitHub 文件。

## 1.3.1

发布状态为 **off**。1.3.0 的旧授权路径也已关闭。

新版授权接口：`https://www.xrt666.top/jc-license-v2/authorize.php`

通过 FTP 编辑服务器文件 `/private/jc-license-v2/config.json`：

开启：

```json
{"status":"on","min_version":"1.3.1"}
```

关闭：

```json
{"status":"off","min_version":"1.3.1"}
```

修改这个 GitHub README 或下载配置模板不会改变线上状态，必须保存到上述服务器文件。
新版启动联网检查，运行中每 30 秒复查；失败或关闭时停止本地操作。
已经提交到即创云端的任务不因此取消。

1.3.0 的配置路径仍是 `/private/jc-license-v1/config.json`，与新版独立。

下载地址、文件大小和 SHA-256 见 [1.3.1 发布记录](releases/1.3.1.json)。
此仓库不保存应用源码、服务器签名私钥或 FTP 密码。
