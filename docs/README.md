# 🦞 OpenClaw 系统档案

**系统名称**: 瑞贝卡 (Rebecca) - 张总的技术分身  
**创建日期**: 2026-03-09  
**系统版本**: OpenClaw 2026.3.7  
**负责人**: 张振中 (张总)  
**代理**: 瑞贝卡 (Rebecca)

---

## 📋 目录

1. [设备环境](#设备环境)
2. [开发环境](#开发环境)
3. [软件环境](#软件环境)
4. [技能配置](#技能配置)
5. [系统架构](#系统架构)
6. [快速开始](#快速开始)
7. [维护手册](#维护手册)

---

## 设备环境

### 硬件配置
| 项目 | 规格 |
|------|------|
| **主机名** | zhangvm |
| **架构** | x86_64 (虚拟机) |
| **CPU** | 8 核心 |
| **内存** | 16GB (可用 13GB) |
| **存储** | 100GB (已用 34GB, 剩余 60GB) |
| **主机** | 张总物理机 |

### 网络配置
| 项目 | 值 |
|------|-----|
| **IP 地址** | 192.168.36.133/24 |
| **网络接口** | ens33 |
| **DNS** | 127.0.0.53 (systemd-resolved) |
| **Gateway 端口** | 18789 (HTTPS) |
| **访问地址** | https://192.168.36.133:18789 |

### 操作系统
```
系统：Ubuntu 24.04.4 LTS (Noble Numbat)
内核：Linux 6.17.0-14-generic
发行版：Ubuntu 24.04
```

---

## 开发环境

### 运行时
| 工具 | 版本 | 用途 |
|------|------|------|
| **Node.js** | v22.22.1 | JavaScript 运行时 |
| **npm** | 10.9.4 | Node 包管理器 |
| **pnpm** | 10.31.0 | 快速 Node 包管理器 |
| **Git** | 2.43.0 | 版本控制 |
| **GitHub CLI** | 2.45.0 | GitHub 命令行 |

### OpenClaw 配置
| 项目 | 值 |
|------|-----|
| **版本** | 2026.3.7 |
| **配置路径** | `~/.openclaw/openclaw.json` |
| **工作区** | `~/.openclaw/workspace/` |
| **技能库** | `~/.agents/skills/` |
| **默认模型** | dashscope/qwen3.5-plus |
| **Gateway** | systemd 服务 (PID 4426) |

### 模型配置
| 提供商 | 模型 | 用途 |
|--------|------|------|
| **Dashscope** | qwen3.5-plus | 主模型 (1M 上下文) |
| **Dashscope** | qwen3-coder-plus | 编码专用 |
| **Dashscope** | qwen3-coder-next | 快速编码 |
| **Dashscope** | glm-5 | 备用模型 |
| **MiniMax** | MiniMax-M2.5 | 备用模型 (200K 上下文) |

---

## 软件环境

### 核心服务
| 服务 | 状态 | 说明 |
|------|------|------|
| **Gateway** | ✅ 运行中 | HTTPS + Token 认证 |
| **Feishu** | ✅ 已连接 | WebSocket 通道 |
| **Cron** | ✅ 已启用 | 定时任务调度 |
| **Hooks** | ✅ 5 个激活 | 自动化扩展 |

### 外部服务集成
| 服务 | 状态 | 用途 |
|------|------|------|
| **GitHub** | ✅ 已登录 (apple3z) | 代码仓库、备份 |
| **Feishu** | ✅ 已配置 | 消息通道 |
| **Dashscope** | ✅ 已配置 | AI 模型服务 |
| **MiniMax** | ✅ 已配置 | AI 模型服务 |

### 定时任务
| 名称 | 计划 | 说明 |
|------|------|------|
| **Daily Auto-Update** | 每天 14:00 | 自动更新 OpenClaw 和技能 |

### Hooks
| 名称 | 状态 | 说明 |
|------|------|------|
| 🚀 boot-md | ✅ ready | Gateway 启动引导 |
| 📎 bootstrap-extra-files | ✅ ready | 工作区引导文件注入 |
| 📝 command-logger | ✅ ready | 命令审计日志 |
| 💾 session-memory | ✅ ready | 会话记忆保存 |
| 🧠 self-improvement | ✅ ready | 自我改进提醒 |

---

## 技能配置

### 技能总数：21 个

#### 🔄 核心技能 (4 个)
| 技能 | 版本 | 功能 |
|------|------|------|
| **auto-updater** | 1.0.0 | 每日自动更新系统 |
| **self-improving-agent** | 1.0.11 | 自我学习与改进 |
| **proactive-agent** | 3.1.0 | 主动式代理 (Hal Stack) |
| **find-skills** | 0.1.0 | 技能发现助手 |

#### 💻 开发工具 (7 个)
| 技能 | 版本 | 功能 |
|------|------|------|
| **github** | 1.0.0 | GitHub CLI 交互 |
| **agent-browser** | 0.2.0 | 无头浏览器自动化 |
| **webapp-testing** | - | Playwright Web 测试 |
| **test-driven-development** | - | 测试驱动开发 |
| **subagent-driven-development** | - | 子代理开发 |
| **python-mcp-server-generator** | - | MCP 服务器生成 |
| **copilot-coding-agent** | - | GitHub Copilot 集成 |

#### 🤖 AI 与内容 (5 个)
| 技能 | 版本 | 功能 |
|------|------|------|
| **nano-banana-pro** | 1.0.1 | Gemini 图像生成 |
| **summarize** | 1.0.0 | 内容摘要 (URL/PDF/视频) |
| **tavily-search** | 1.0.0 | AI 优化网络搜索 |
| **imagegen** | - | OpenAI 图像 API |
| **spotify** | - | Spotify 播放控制 |

#### 📊 产品与管理 (2 个)
| 技能 | 版本 | 功能 |
|------|------|------|
| **product-management** | - | 产品管理框架 |
| **project-manager** | - | 项目管理专家 |

#### 🔌 集成工具 (3 个)
| 技能 | 版本 | 功能 |
|------|------|------|
| **notion** | 1.0.0 | Notion API 集成 |
| **blogwatcher** | - | 博客监控 |
| **goplaces** | - | 地点服务 |

---

## 系统架构

### 目录结构
```
~/.openclaw/
├── openclaw.json          # 主配置文件
├── backup/                # 系统备份 (已上传 GitHub)
│   ├── config/            # 配置文件备份
│   ├── workspace/         # 工作区备份
│   ├── skills/            # 技能清单
│   └── docs/              # 文档
├── hooks/                 # Hooks 扩展
│   └── self-improvement/  # 自我改进 Hook
└── workspace/             # 工作区
    ├── AGENTS.md          # 多代理工作流
    ├── SOUL.md            # 行为指南
    ├── TOOLS.md           # 工具配置
    ├── USER.md            # 用户资料
    ├── IDENTITY.md        # 代理身份 (瑞贝卡)
    ├── HEARTBEAT.md       # 心跳配置
    ├── MEMORY.md          # 长期记忆
    ├── memory/            # 每日记忆文件
    └── .learnings/        # 学习记录
```

### 网络架构
```
┌─────────────────────────────────────────────────────────┐
│                    张总物理机 (Host)                     │
│  ┌───────────────────────────────────────────────────┐  │
│  │              zhangvm (VM) - 192.168.36.133        │  │
│  │                                                   │  │
│  │  ┌─────────────┐    ┌─────────────┐              │  │
│  │  │   Gateway   │───▶│   OpenClaw  │              │  │
│  │  │  :18789     │    │   Agent     │              │  │
│  │  └─────────────┘    └─────────────┘              │  │
│  │         │                    │                    │  │
│  │         ▼                    ▼                    │  │
│  │  ┌─────────────┐    ┌─────────────┐              │  │
│  │  │   Feishu    │    │   Skills    │              │  │
│  │  │  WebSocket  │    │   (21 个)    │              │  │
│  │  └─────────────┘    └─────────────┘              │  │
│  └───────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────┘
                    │
                    ▼
         ┌─────────────────────┐
         │   外部服务           │
         │  - GitHub           │
         │  - Dashscope        │
         │  - MiniMax          │
         │  - Feishu API       │
         └─────────────────────┘
```

### 数据流
```
用户 (Feishu) 
    ▼
Gateway (:18789, HTTPS + Token)
    ▼
OpenClaw Agent (qwen3.5-plus)
    ▼
Skills (21 个)
    ▼
外部服务 (GitHub, Dashscope, etc.)
    ▼
响应 → 用户 (Feishu)
```

---

## 快速开始

### 系统状态检查
```bash
# 查看系统状态
openclaw status

# 查看 Gateway 状态
openclaw gateway status

# 查看日志
openclaw logs --follow
```

### 常用命令
```bash
# 重启 Gateway
openclaw gateway restart

# 停止 Gateway
openclaw gateway stop

# 启动 Gateway
openclaw gateway start

# 查看 Cron 任务
openclaw cron list

# 查看 Hooks
openclaw hooks list

# 安全审计
openclaw security audit
```

### 技能管理
```bash
# 列出已安装技能
ls ~/.agents/skills/

# 安装新技能
clawdhub install <skill-name>

# 更新所有技能
clawdhub update --all

# 查看技能版本
clawdhub list
```

### 备份管理
```bash
# 本地备份位置
~/.openclaw/backup/

# GitHub 备份仓库
https://github.com/apple3z/backup

# 从备份恢复
cp ~/.openclaw/backup/config/openclaw.json.* ~/.openclaw/openclaw.json
openclaw gateway restart
```

---

## 维护手册

### 日常检查清单
- [ ] Gateway 服务运行正常
- [ ] Feishu 通道连接正常
- [ ] Cron 任务执行正常
- [ ] 磁盘空间充足 (>20%)
- [ ] 内存使用正常 (<80%)

### 每周检查清单
- [ ] 技能更新检查 (`clawdhub update --all --dry-run`)
- [ ] OpenClaw 版本检查 (`openclaw status`)
- [ ] 备份验证 (GitHub 仓库)
- [ ] 日志审查 (错误/警告)

### 每月检查清单
- [ ] 安全审计 (`openclaw security audit --deep`)
- [ ] 配置审查 (openclaw.json)
- [ ] 技能清理 (删除未使用技能)
- [ ] 文档更新 (本 README)

### 故障排除

#### Gateway 无法启动
```bash
# 检查端口占用
lsof -i :18789

# 查看日志
openclaw logs --follow

# 重启服务
openclaw gateway restart
```

#### Feishu 通道断开
```bash
# 检查配置
cat ~/.openclaw/openclaw.json | grep -A5 feishu

# 重启 Gateway
openclaw gateway restart

# 检查状态
openclaw status --all
```

#### 技能加载失败
```bash
# 检查技能目录
ls -la ~/.agents/skills/

# 重新安装技能
cd ~/.agents/skills/<skill-name>
# 或从 ClawHub 重新安装
clawdhub install <skill-name> --force
```

### 敏感信息管理

**以下信息已脱敏，不包含在备份中：**
- ❌ API Keys (模型服务、飞书等)
- ❌ Token (Gateway 认证)
- ❌ 个人凭据

**恢复后需要手动配置：**
1. ✅ 更新 `openclaw.json` 中的 API Keys
2. ✅ 更新飞书应用凭据 (appId, appSecret)
3. ✅ 验证 GitHub 认证 (`gh auth status`)
4. ✅ 检查 Gateway Token

---

## 联系与支持

### 系统管理员
- **负责人**: 张振中 (张总)
- **代理**: 瑞贝卡 (Rebecca)
- **时区**: Asia/Shanghai (UTC+8)

### 文档资源
- **OpenClaw 官方文档**: https://docs.openclaw.ai
- **故障排除**: https://docs.openclaw.ai/troubleshooting
- **技能市场**: https://clawhub.com
- **GitHub 仓库**: https://github.com/openclaw/openclaw

### 社区
- **Discord**: https://discord.com/invite/clawd
- **GitHub Issues**: https://github.com/openclaw/openclaw/issues

---

## 版本历史

| 日期 | 版本 | 说明 |
|------|------|------|
| 2026-03-09 | 2026.3.7 | 初始系统安装完成 |
| 2026-03-09 | 2026.3.7 | 21 个技能安装完成 |
| 2026-03-09 | 2026.3.7 | 系统备份上传 GitHub |
| 2026-03-09 | 2026.3.7 | 文档完善 |

---

**档案结束**

*最后更新：2026-03-09 14:45*  
*维护人：瑞贝卡 (Rebecca)*
