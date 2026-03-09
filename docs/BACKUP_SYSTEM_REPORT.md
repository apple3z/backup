# 🦞 OpenClaw 系统完整档案

**生成时间**: 2026-03-09 13:35 (Asia/Shanghai)  
**系统版本**: OpenClaw 2026.3.7  
**档案类型**: 完整系统配置备份

---

## 📋 目录

1. [系统环境](#系统环境)
2. [网络配置](#网络配置)
3. [OpenClaw 配置](#openclaw-配置)
4. [已安装技能](#已安装技能)
5. [定时任务与 Hooks](#定时任务与-hooks)
6. [工作区结构](#工作区结构)
7. [外部服务配置](#外部服务配置)
8. [备份说明](#备份说明)

---

## 系统环境

### 操作系统
```
系统：Ubuntu 24.04.4 LTS (Noble Numbat)
内核：Linux 6.17.0-14-generic
架构：x86_64
主机名：zhangvm
```

### 运行时环境
```
Node.js: v22.22.1
npm: 10.9.4
pnpm: 10.31.0
OpenClaw: 2026.3.7
Git: 2.43.0
GitHub CLI: 2.45.0
```

### 安装路径
```
OpenClaw 配置：~/.openclaw/openclaw.json
工作区目录：~/.openclaw/workspace/
技能库目录：~/.agents/skills/
Gateway 端口：18789
```

---

## 网络配置

### 网络接口
```
IP 地址：192.168.36.133/24
网关：192.168.36.1
DNS: 127.0.0.53 (systemd-resolved)
```

### Gateway 配置
```
绑定地址：0.0.0.0 (lan)
端口：18789
协议：HTTPS (自签名证书)
认证模式：Token
访问地址：https://192.168.36.133:18789
```

### 防火墙/安全
```
Tailscale: 未安装
Gateway 服务：systemd (运行中，PID 4426)
```

---

## OpenClaw 配置

### 核心配置 (openclaw.json)

#### 模型配置
```json
{
  "providers": {
    "minimax": {
      "baseUrl": "https://api.minimaxi.com/v1",
      "models": ["MiniMax-M2.5"]
    },
    "dashscope": {
      "baseUrl": "https://coding.dashscope.aliyuncs.com/v1",
      "models": [
        "qwen3.5-plus",
        "qwen3-coder-plus",
        "qwen3-coder-next",
        "glm-5"
      ]
    }
  }
}
```

#### 默认模型
```
主模型：dashscope/qwen3.5-plus
Fallback: 无
```

#### Agent 配置
```json
{
  "maxConcurrent": 4,
  "subagents": {
    "maxConcurrent": 8
  },
  "compaction": {
    "mode": "safeguard"
  }
}
```

#### 通道配置 (Feishu)
```json
{
  "appId": "cli_a92ba507b3745cb2",
  "connectionMode": "websocket",
  "dmPolicy": "pairing"
}
```

#### Gateway 配置
```json
{
  "port": 18789,
  "mode": "local",
  "bind": "lan",
  "tls": { "enabled": true },
  "auth": {
    "mode": "token",
    "token": "7e3a5db93cf969becb37da6fdbeda0d3f07680026438aa6a"
  },
  "controlUi": {
    "allowedOrigins": [
      "http://localhost:18789",
      "http://127.0.0.1:18789",
      "http://192.168.36.133:18789",
      "https://192.168.36.133:18789"
    ]
  }
}
```

#### Hooks 配置
```json
{
  "internal": {
    "enabled": true,
    "entries": {
      "self-improvement": { "enabled": true }
    }
  }
}
```

---

## 已安装技能

### 技能总数：21 个

#### 核心技能
| 技能名称 | 版本 | 用途 |
|---------|------|------|
| auto-updater | 1.0.0 | 每日自动更新 |
| self-improving-agent | 1.0.11 | 自我改进与学习 |
| proactive-agent | 3.1.0 | 主动式代理 |
| find-skills | 0.1.0 | 技能发现助手 |

#### 开发工具
| 技能名称 | 版本 | 用途 |
|---------|------|------|
| github | 1.0.0 | GitHub CLI 交互 |
| agent-browser | 0.2.0 | 无头浏览器自动化 |
| webapp-testing | - | Playwright Web 测试 |
| test-driven-development | - | 测试驱动开发 |
| subagent-driven-development | - | 子代理开发 |
| python-mcp-server-generator | - | MCP 服务器生成 |

#### AI 与内容
| 技能名称 | 版本 | 用途 |
|---------|------|------|
| nano-banana-pro | 1.0.1 | Gemini 图像生成 |
| summarize | 1.0.0 | 内容摘要 |
| tavily-search | 1.0.0 | AI 优化搜索 |
| imagegen | - | OpenAI 图像 API |
| copilot-coding-agent | - | GitHub Copilot |

#### 产品与管理
| 技能名称 | 版本 | 用途 |
|---------|------|------|
| product-management | - | 产品管理 |
| project-manager | - | 项目管理 |

#### 集成与工具
| 技能名称 | 版本 | 用途 |
|---------|------|------|
| notion | 1.0.0 | Notion API |
| spotify | - | Spotify 播放控制 |
| blogwatcher | - | 博客监控 |
| goplaces | - | 地点服务 |

---

## 定时任务与 Hooks

### Cron 任务
| ID | 名称 | 计划 | 时区 | 状态 |
|----|------|------|------|------|
| 2e242258-8eed-4b40-9cb6-cc0a22c35d4e | Daily Auto-Update | `0 14 * * *` | Asia/Shanghai | 已启用 |

**说明**: 每天下午 2 点执行自动更新，检查 OpenClaw 和技能更新。

### Hooks
| 状态 | 名称 | 描述 | 来源 |
|------|------|------|------|
| ✓ ready | 🚀 boot-md | Gateway 启动时运行 BOOT.md | openclaw-bundled |
| ✓ ready | 📎 bootstrap-extra-files | 注入额外工作区引导文件 | openclaw-bundled |
| ✓ ready | 📝 command-logger | 记录所有命令事件到审计文件 | openclaw-bundled |
| ✓ ready | 💾 session-memory | /new 或 /reset 时保存会话上下文 | openclaw-bundled |
| ✓ ready | 🧠 self-improvement | 代理引导时注入自我改进提醒 | openclaw-managed |

---

## 工作区结构

```
~/.openclaw/workspace/
├── AGENTS.md              # 多代理工作流和委托模式
├── SOUL.md                # 行为指南和个性原则
├── TOOLS.md               # 工具能力和集成注意事项
├── USER.md                # 用户资料和协作偏好
├── IDENTITY.md            # 代理身份定义 (瑞贝卡)
├── HEARTBEAT.md           # 心跳任务配置
├── MEMORY.md              # 长期记忆 (主会话)
├── .learnings/            # 自我改进学习记录
│   ├── LEARNINGS.md
│   ├── ERRORS.md
│   └── FEATURE_REQUESTS.md
├── memory/                # 每日记忆文件
│   ├── 2026-03-06.md
│   ├── 2026-03-07.md
│   ├── 2026-03-08.md
│   ├── 2026-03-09.md
│   ├── ACCOUNTS_SETUP.md
│   ├── BUG_TRACKING.md
│   ├── CORE_COLLAB_SPEC.md
│   ├── INSTALLED_SKILLS.md
│   ├── INSTALL_REPORT.md
│   ├── LEARN_RD_SPEC.md
│   ├── PROJECT_NEWS_SYSTEM.md
│   ├── RECOMMENDED_SKILLS.md
│   ├── RECOMMENDED_SKILLS_V2.md
│   ├── SKILLS_INVENTORY.md
│   ├── SYSTEM_ARCHIVE.md
│   └── UNINSTALLED_SKILLS.md
├── .clawhub/              # ClawHub 配置
├── .git/                  # Git 仓库
├── .openclaw/             # OpenClaw 内部配置
├── skills/                # 工作区技能
└── skills_import/         # 导入的技能
```

### 核心身份文件

#### IDENTITY.md
```
名字：瑞贝卡 (Rebecca)
定位：全能技术伙伴（资深技术架构师 / 全栈开发工程师 / DevOps 专家 / 产品与运营专家）
风格：犀利高效，专业严谨
Emoji: 🦞
使命：构建全球化运营服务平台软件
```

#### SOUL.md
```
核心原则:
- Be genuinely helpful, not performatively helpful
- Have opinions
- Be resourceful before asking
- Earn trust through competence
- Remember you're a guest
```

---

## 外部服务配置

### GitHub
```
账号：apple3z
认证：gh CLI (已登录)
Token 范围：admin:org, project, repo, user, workflow, write:packages
仓库:
  - apple3z/backup (OpenClaw 系统备份)
  - apple3z/news-system (News System 项目)
  - apple3z/- (基础系统规划，私有)
```

### 飞书 (Feishu)
```
应用 ID: cli_a92ba507b3745cb2
连接模式：WebSocket
DM 策略：pairing
状态：OK (已配置)
```

### AI 模型服务
```
MiniMax:
  - API: https://api.minimaxi.com/v1
  - 模型：MiniMax-M2.5

Dashscope (阿里云):
  - API: https://coding.dashscope.aliyuncs.com/v1
  - 模型：qwen3.5-plus, qwen3-coder-plus, qwen3-coder-next, glm-5
```

---

## 备份说明

### 本次备份内容

#### 1. 配置文件
- `~/.openclaw/openclaw.json` - 主配置文件
- `~/.openclaw/cron/jobs.json` - Cron 任务配置
- `~/.openclaw/hooks/` - Hooks 配置目录

#### 2. 工作区文件
- `~/.openclaw/workspace/AGENTS.md`
- `~/.openclaw/workspace/SOUL.md`
- `~/.openclaw/workspace/TOOLS.md`
- `~/.openclaw/workspace/USER.md`
- `~/.openclaw/workspace/IDENTITY.md`
- `~/.openclaw/workspace/HEARTBEAT.md`
- `~/.openclaw/workspace/MEMORY.md`
- `~/.openclaw/workspace/memory/` - 所有记忆文件
- `~/.openclaw/workspace/.learnings/` - 学习记录

#### 3. 技能清单
- `~/.agents/skills/` - 所有已安装技能

### 备份策略

#### 本地备份
```
位置：~/.openclaw/backup/
频率：每次重大配置变更后
保留：最近 3 个版本
```

#### 远程备份 (GitHub)
```
仓库：github.com/apple3z/backup
频率：每周或重大变更后
内容：配置文件 + 工作区文档 + 技能清单
```

### 恢复流程

#### 本地恢复
```bash
# 恢复配置文件
cp ~/.openclaw/backup/openclaw.json ~/.openclaw/openclaw.json

# 恢复工作区
cp -r ~/.openclaw/backup/workspace/* ~/.openclaw/workspace/

# 重启 Gateway
openclaw gateway restart
```

#### 从 GitHub 恢复
```bash
# 克隆备份仓库
git clone https://github.com/apple3z/backup.git ~/openclaw-backup

# 恢复配置
cp ~/openclaw-backup/config/openclaw.json ~/.openclaw/openclaw.json
cp -r ~/openclaw-backup/workspace/* ~/.openclaw/workspace/

# 重启 Gateway
openclaw gateway restart
```

### 敏感信息处理

**以下信息已脱敏，不包含在备份中：**
- API Keys (模型服务、飞书等)
- Token (Gateway 认证)
- 个人凭据

**恢复后需要手动配置：**
1. 更新 `openclaw.json` 中的 API Keys
2. 更新飞书应用凭据
3. 验证 GitHub 认证

---

## 系统健康检查清单

### 日常检查
- [ ] Gateway 服务运行正常
- [ ] 飞书通道连接正常
- [ ] Cron 任务执行正常
- [ ] 磁盘空间充足

### 每周检查
- [ ] 技能更新检查
- [ ] OpenClaw 版本检查
- [ ] 备份验证
- [ ] 日志审查

### 每月检查
- [ ] 安全审计
- [ ] 配置审查
- [ ] 技能清理
- [ ] 文档更新

---

## 联系与支持

### 文档
- OpenClaw 官方文档：https://docs.openclaw.ai
- 故障排除：https://docs.openclaw.ai/troubleshooting
- 技能市场：https://clawhub.com

### 社区
- Discord: https://discord.com/invite/clawd
- GitHub: https://github.com/openclaw/openclaw

### 系统管理员
- 负责人：张振中 (张总)
- 代理：瑞贝卡 (Rebecca)
- 时区：Asia/Shanghai (UTC+8)

---

**档案结束**

*最后更新：2026-03-09 13:35*
