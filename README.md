# 飞书消息通知工作流

一键发送飞书消息卡片的 GitHub Actions 工作流。

## 快速开始

### 1. 配置 Secrets

在 `Settings` → `Secrets and variables` → `Actions` 添加：

| Secret 名称 | 说明 |
|-----------|------|
| `FEISHU_ID` | 飞书机器人 Webhook 的 hook_id |
| `FEISHU_SECRET` | 飞书机器人签名密钥 |

### 2. 发送消息

1. 进入仓库的 **Actions** 页面
2. 点击左侧的 **飞书消息通知**
3. 点击 **Run workflow**
4. 填写标题、内容、选择状态
5. 点击 **Run workflow** 即可发送

## 工作流文件

**[.github/workflows/feishu-notify.yml](.github/workflows/feishu-notify.yml)**

- 单一文件，无其他依赖
- 无需 checkout 代码
- 下拉框选择状态，操作简单

## 状态样式

| 状态 | 颜色 | 图标 |
|-----|------|------|
| `success` | 绿色 | ✅ |
| `failure` | 红色 | ❌ |
| `warning` | 黄色 | ⚠️ |
| `info` | 蓝色 | ℹ️ |

## 作者

**zentrix566** - IT运维工程师
