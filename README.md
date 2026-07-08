# 格物通 (Gewutong)

> 网格员工单管理系统 — 工单创建、派发、办结、统计全流程管理
> Grid-based Ticket Management System — Create, dispatch, resolve & report tickets

[![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)](https://python.org)
[![Flask](https://img.shields.io/badge/Flask-3.0-black?logo=flask)](https://flask.palletsprojects.com)
[![Android](https://img.shields.io/badge/Android-24+-green?logo=android)](https://developer.android.com)
[![SQLite](https://img.shields.io/badge/SQLite-3-003b57?logo=sqlite)](https://sqlite.org)
[![License](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)

---

## 📋 项目简介 | Overview

**格物通** 是一个面向社区网格员的工单管理双端项目：

- 🧩 **Flask 后端**（`gewutong.test/`）— 提供 Web 管理端，支持工单全生命周期管理
- 📱 **Android 客户端**（`GewutongApp/`）— WebView 套壳 App，直连后端

Gewutong is a dual-platform ticket management system for community grid workers, built with a Flask backend and an Android WebView client.

---

## 🚀 快速开始 | Quick Start

### 后端启动 | Backend

```powershell
cd D:\gitee\gewutong.test

# 创建虚拟环境（首次）
python -m venv .venv
.\.venv\Scripts\pip install -r requirements.txt

# 启动
.\.venv\Scripts\python app.py
```

启动后访问：
- 本机：`http://127.0.0.1:5000/login`
- 局域网：`http://你的电脑IP:5000/login`

### Android 客户端启动 | Android Client

1. 用 Android Studio 打开 `D:\gitee\GewutongApp`
2. 修改 `MainActivity.kt` 中的 `appUrl` 为你电脑的局域网 IP
3. 连接手机，运行

---

## 🔑 默认账号 | Default Accounts

| 角色 | 账号 | 密码 |
|------|------|------|
| 管理员 | `admin` | `admin123` |
| 网格员 1 | `demo` | `demo123` |
| 网格员 2 | `chenyu` | `123456` |

管理员注册邀请码：`GW2026ADMIN`

---

## ✨ 功能特性 | Features

### 工单管理 | Ticket Management
- ✅ 创建 / 派发 / 改派 / 办结 / 备注
- ✅ 批量派发、批量改状态、批量删除
- ✅ 工单详情 + 操作日志 🔍
- ✅ 回收站（恢复 & 彻底删除）🗑️

### 系统管理 | System Management
- ✅ 角色权限（管理员 / 网格员）
- ✅ 账号管理（启停、重置密码、删除）
- ✅ 全局日志中心 📜
- ✅ 数据备份与恢复 💾
- ✅ CSV 导入导出 📊

### 统计报表 | Reports
- ✅ 多维度统计报表 📈
- ✅ 超时工单高亮 ⏰

---

## 🏗️ 技术栈 | Tech Stack

### 后端 | Backend
| 技术 | 用途 |
|------|------|
| Python + Flask 3.0 | Web 框架 |
| SQLite | 数据库 |
| Werkzeug | 密码哈希 / 文件上传 |
| Jinja2 | 模板引擎 |
| HTML + CSS + JavaScript | 前端界面 |

### Android 客户端 | Android Client
| 技术 | 用途 |
|------|------|
| Kotlin + Android (minSdk 24) | 原生壳 |
| WebView | 加载后端 Web 页面 |
| AndroidX AppCompat + ConstraintLayout | UI 框架 |

---

## 📁 项目结构 | Project Structure

```
d:\gitee
├── gewutong.test/          # Flask 后端 + Web 管理端
│   ├── app.py               # 主入口
│   ├── requirements.txt     # Python 依赖
│   ├── templates/           # HTML 模板
│   │   ├── login.html
│   │   ├── register.html
│   │   ├── index.html
│   │   └── ticket_detail.html
│   ├── static/
│   │   ├── style.css
│   │   └── uploads/         # 图片上传
│   ├── tickets.db           # SQLite 数据库
│   └── demo_tickets.csv
│
├── GewutongApp/             # Android 客户端
│   ├── app/
│   │   └── src/main/java/.../MainActivity.kt
│   ├── build.gradle.kts
│   └── settings.gradle.kts
│
└── README.md
```

---

## ⚠️ 上传须知 | Before Pushing to GitHub

`.gitignore` 已配置，以下内容不会被提交：

- 虚拟环境 `.venv/`
- 本地数据库 `*.db`
- 上传图片 `static/uploads/`
- Android 构建产物 `build/` `.gradle/` `local.properties`
- IDE 配置 `.idea/`

---

## 📄 协议 | License

MIT License
