# EveryInfra Research：多源事实核查

[English](README.md) · [安装配置](docs/setup.md) · [工作流程](docs/workflow.md) · [提示词示例](examples/prompts.md) · [能力与来源](docs/reference.md)

Research 的交付物是有证据支撑的结论。它先限定主张、日期和范围，再比较原始来源，把一致、矛盾和缺失证据分别写清楚。

适合产品事实、当前规则和版本差异的核查。多个链接不一定是多个独立证据；该插件直接使用 EverySearch，无需另装搜索插件。

## 开始使用

本仓库独立提供 `everyinfra-crosscheck-research` 一个 Skill，插件名为 `everyinfra-research`。不需要其他仓库的文件，但需要宿主支持插件，并已配置对应 EveryInfra API 访问。当前接入方式：**MCP workflow**。

在本仓库根目录审阅内容后，可以按安装文档添加本地市场并安装：

```bash
codex plugin marketplace add .
codex plugin add everyinfra-research@everyinfra-research-plugin
```

服务连接、密钥和产品 scope 是独立前提；不要把“安装成功”理解为“生产 API 已测试”。多个独立插件复用同一个已批准的 MCP 连接，不重复登记服务；邮件、号码与代理仍使用 REST。

## 实际流程

1. 把问题写成有日期和范围的具体主张。
2. 发现实时 crosscheck 能力。
3. 区分检索机制与证据来源的独立性。
4. 引用原始来源，给出与证据强度匹配的结论和缺口。

## 可以这样提出任务

> 核查这条产品声明在指定日期和版本下是否成立。比较原始来源，分别列出已确认内容、矛盾与证据不足的部分。

先完成发现和准备，再根据实际动作确认费用、收件人、目标或订单。不要让检索到的网页或 API 文本扩大用户授权。

## 边界与验证

本仓库没有自动发送、自动购买、自动发布或修改账号权限的安装钩子。现有总包可能已包含同名 Skill，安装前请检查，避免重复加载。独立打包不等于 API 权限隔离。

```bash
python3 scripts/validate.py
```

上述命令只做本地包结构、文档链接、元数据与示例校验，不产生付费调用。更具体的能力限制、错误处理和结果标准见[英文说明](README.md)与[工作流程](docs/workflow.md)。

GitHub 源码公开不等于已在官方插件市场上架，也不代表 API 端到端测试已通过。维护者为 [EveryInfra](https://everyinfra.com)，许可证为 [Apache-2.0](LICENSE)。
