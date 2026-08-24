> [!CAUTION]
> 请勿以任何形式转载或发布至中国大陆地区
##
### 💡 特别提示
>本规则集域名以V5为主，IP V3为辅,建议Sing-box内核更新至sing-box 1.14.0-alpha.46以上版本

### 🚀 效果对比

* **1.14-a46前**：由于多个不同上游仓库路径与名称等差异，必须手写大量重复的 `rule_set` 结构（每个标签占用一个 JSON 对象）。
* **1.14-a46后**：直接利用内核对**多标签数组**及 `{tag}` 变量的支持，使用一行配置即可批量导入、减少 sing-box 客户端重复配置和手搓工作量。

##

### ⚙️ 配置示例
```json
  "http_clients":[{"tag":"direct_download"}],
  "route":{
    "default_http_client":"direct_download",
    "rule_set":[
    {"tag": ["Google-Site","Local-IP","xx1","xx2"],"type": "remote","format": "binary",
    "url": "https://cdn.jsdelivr.net/gh/your_username/singbox@main/singbox/{tag}.srs"}],
```
### 📄 开源许可
数据来源于网络抓取，本项目遵循 [MIT License](LICENSE) 协议开源。
