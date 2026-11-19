# JiChuang Studio 授权与版本

当前版本：**1.3.2**，新增启动卡密登录。发布时总开关保持 **off**。

## 在哪里修改卡密

**在服务器修改，不在 GitHub 修改。** 服务器私有文件：

`/private/jc-license-v2/config.json`

- 修改 `card_key` 为新卡密，保留其他字段。
- 修改 `status` 为 `on` 开启、`off` 关闭，保留卡密字段。
- `min_version` 保持 `1.3.2`。
- 不要用旧版只有 status/min_version 的配置模板覆盖整个文件。

管理员工具 `python manage_switch.py set-card` 会交互询问新卡密和 FTP 密码，
只更新卡密，保持开关状态。`on`、`off`、`show` 分别用于开启、关闭和查看状态。
工具不回显卡密或 FTP 密码。

卡密每次启动都要输入，不在本机保存，也不内置在 EXE 中。
服务器更换卡密无需重新发包；运行中的客户端在下次复查时拒绝旧卡密并关闭工作台。
每 30 秒复查，新任务前刷新超过 5 秒的授权。正确卡密也不能绕过 off 开关。
已经提交到即创云端的任务不因此取消。

授权接口：`https://www.xrt666.top/jc-license-v2/authorize.php`。
客户端只通过 HTTPS 校验卡密与签名，不读取 GitHub 中的卡密。

## 旧版与发布记录

- 根目录 `config.json` 只管理旧版 1.2.6 的 GitHub 开关，保持 off。
- 1.3.0 的 `/private/jc-license-v1/config.json` 保持 off。
- 1.3.1 不满足新卡密授权协议，使用 1.3.2 登录。
- [1.3.2 发布记录](releases/1.3.2.json)
- [1.3.1 历史记录](releases/1.3.1.json)

此仓库只保存公开的版本信息，不保存应用源码、卡密、签名私钥或 FTP 密码。
