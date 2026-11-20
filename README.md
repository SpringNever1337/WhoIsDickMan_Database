# WhoIsDickMan_Database

运动助手客户端的版本信息与访问数据仓库。

- `version.json`：客户端检查更新使用
- `index.html`：GitHub Pages 首页，客户端可用性检测使用
- `blacklist.json`：账号指纹黑名单，格式为 `{"ids":["<fingerprint>", ...]}`，命中后客户端直接关闭

Pages 地址：https://springnever1337.github.io/WhoIsDickMan_Database/

## 黑名单维护

`ids` 里存放的是「学号 + uid」经 HMAC-SHA256（2000 轮）派生的 64 位十六进制指纹，不包含任何明文账号。
需要封禁某个账号时，把对应指纹加入 `ids` 数组并提交即可；客户端启动后会拉取并校验。