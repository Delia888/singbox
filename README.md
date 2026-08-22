> [!CAUTION]
> 请勿以任何形式转载或发布至中国大陆地区

# Sing-box 规则集管理

> Automatic Synchronization and Management of Sing-box Rule Sets

本项目专为自用分流规则维护管理而设计。通过 Python 自动化脚本与 GitHub Actions，统一拉取、校验、重组并托管分散在各第三方仓库的规则集，减少 sing-box 客户端重复配置和手动维护的工作量。

### 🚀 优化效果对比

**对比条件**：SING-BOX 内核 `>= v1.14.0-alpha.46`

* **优化前**：由于多个不同上游路径与名称差异，须手写大量重复的 `rule_set` 结构（每个标签占用一个 JSON 对象）。
* **优化后**：经本项目自动化整理并输出统一路径后，直接利用内核对**多标签数组**及 `{tag}` 变量的支持，使用一行配置即可批量导入。

##
### ⚙️ 配置示例
```json
  "http_clients":[{"tag":"direct_download"}],
  "route":{
    "default_http_client":"direct_download",
    "rule_set":[
    {"tag": ["Google-Site","Local-IP","xx1","xx2"],"type": "remote","format": "binary",
    "url": "https://cdn.jsdelivr.net/gh/your_username/singbox-rules@main/singbox/{tag}.srs"}],
```
### 📄 开源许可
本项目遵循 [MIT License](LICENSE) 协议开源。
