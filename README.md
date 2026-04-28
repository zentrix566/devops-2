# 飞书自建应用消息通知

使用飞书自建应用发送消息卡片的 GitHub Actions 工作流。

## 快速开始

### 1. 创建飞书自建应用

1. 访问 [飞书开放平台](https://open.feishu.cn/) 创建企业自建应用
2. 应用凭证中获取 **App ID** 和 **App Secret**
3. 开通权限：`im:message`、`im:message:send_as_bot`
4. 发布版本并企业审核通过

### 2. 获取群聊 chat_id

在群聊设置 → 群机器人 → 添加机器人，复制群聊的 `chat_id`

### 3. 配置 GitHub Secrets

在 `Settings` → `Secrets and variables` → `Actions` 添加：

| Secret 名称 | 说明 |
|-----------|------|
| `FEISHU_ID` | 飞书自建应用的 **App ID** |
| `FEISHU_SECRET` | 飞书自建应用的 **App Secret** |
| `FEISHU_CHAT_ID` | 飞书群聊 **chat_id** |

### 4. 触发方式

**自动触发：**
- 🚀 **代码提交**：推送代码到 main/master/develop 分支时自动发送
- 📅 **每周定时**：每周一 8:00 自动发送提醒

**手动触发：**
1. 进入仓库的 **Actions** 页面
2. 点击左侧的 **飞书自建应用消息通知**
3. 点击 **Run workflow**
4. 填写标题、内容、选择状态
5. 点击 **Run workflow** 即可发送

## 文件结构

| 文件 | 说明 |
|-----|------|
| **[.github/workflows/feishu-notify.yml](.github/workflows/feishu-notify.yml)** | 工作流主文件 |
| **[.github/config/message-templates.json](.github/config/message-templates.json)** | 样式和消息模板配置 |

### 架构特点

- ✅ **样式与逻辑解耦**：颜色、图标全部在配置文件中
- ✅ **易于维护**：修改样式无需改动工作流代码
- ✅ **可扩展**：轻松添加新的消息类型和样式

### 自定义样式

编辑 `message-templates.json` 即可修改：
- 各状态的颜色和图标
- 不同触发方式的消息标题
- 卡片配置参数

## 状态样式

| 状态 | 颜色 | 图标 |
|-----|------|------|
| `success` | 绿色 | ✅ |
| `failure` | 红色 | ❌ |
| `warning` | 黄色 | ⚠️ |
| `info` | 蓝色 | ℹ️ |

## 常见错误

| 错误 | 原因 | 解决方案 |
|-----|------|---------|
| 获取 token 失败 | App ID/Secret 错误 | 检查 FEISHU_ID 和 FEISHU_SECRET |
| 权限不足 | 应用未开通消息权限 | 在开放平台开通 `im:message` 权限 |
| chat_id 无效 | 群聊 ID 错误 | 确认群聊 chat_id，机器人需在群内 |

## 作者

**zentrix566** - IT运维工程师
