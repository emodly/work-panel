# 📋 个人工作计划面板

支持多用户、多设备的每日计划与工作总结管理工具，面板可视化呈现，数据云端同步。

## 功能特性

### 🔐 多用户账号
- 邮箱 + 密码注册/登录（Supabase Auth）
- 每人数据完全隔离（PostgreSQL 行级安全 RLS）
- 同一账号多设备同步

### 📊 仪表盘
- 今日计划面板：按上午/下午/晚上管理任务，优先级标识和分类标签
- 完成进度面板：环形进度图 + 统计数据 + 各时段进度条
- 工作总结面板：每日总结编辑器 + 一键生成总结模板

### 📅 周视图（TickTick 风格）
- 时间网格日历，7天 × 15小时
- 任务按时间段定位，优先级颜色区分
- 当前时间指示线

### 📆 月视图（TickTick 风格）
- 传统月历网格，彩色圆点标识任务
- 点击任意日期跳转仪表盘

### 📈 统计分析
- 本周完成趋势折线图（Chart.js）
- 任务分类饼图
- 月度热力图

### ⌨️ 快捷键
| 快捷键 | 功能 |
|--------|------|
| `←` `→` | 切换日期 |
| `T` | 回到今天 |
| `Ctrl+S` | 保存工作总结 |
| `Esc` | 关闭弹窗 |

## 部署步骤

### 1. 创建 Supabase 项目（免费）

1. 打开 [app.supabase.com](https://app.supabase.com) 注册/登录
2. 点击 **New Project** 创建项目
3. 记下项目密码，选择最近的区域
4. 等待数据库创建完成（约 1 分钟）

### 2. 配置数据库

1. 在 Supabase 项目中进入 **SQL Editor**
2. 复制 [supabase-setup.sql](supabase-setup.sql) 的全部内容
3. 粘贴并点击 **Run** 执行

### 3. 启用邮箱登录

1. 进入 **Authentication → Providers**
2. 确保 **Email** 已启用
3. （可选）关闭 **Confirm email** 以跳过邮箱验证

### 4. 配置前端连接

1. 进入 **Project Settings → API**
2. 复制 `Project URL` 和 `anon public key`
3. 打开 [supabase-config.js](supabase-config.js)
4. 替换 `YOUR_PROJECT_ID` 和 `YOUR_ANON_KEY`

```js
const SUPABASE_URL = 'https://xxxxx.supabase.co';
const SUPABASE_ANON_KEY = 'eyJhbGci...';
```

### 5. 使用

1. 浏览器打开 `login.html`
2. 注册账号 → 自动进入工作面板
3. 在任何设备浏览器打开同一地址登录即可同步数据

## 技术栈

- 前端：HTML/CSS/JavaScript（零构建）
- 后端：Supabase（PostgreSQL + Auth + REST API）
- 图表：Chart.js（CDN）
