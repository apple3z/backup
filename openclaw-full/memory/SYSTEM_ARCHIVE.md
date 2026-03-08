# 🦞 瑞贝卡完整系统档案

> 创建时间: 2026-03-06
> 最后更新: 2026-03-06 22:50
> 主人: 张振中 (张总)

---

## 一、系统基础信息

### 1.1 主机环境
| 项目 | 值 |
|------|-----|
| 主机名 | zhangvm |
| 操作系统 | Linux 6.17.0-14-generic (x64) |
| Node版本 | v22.22.1 |
| OpenClaw版本 | 2026.3.2 |
| 安装位置 | ~/.npm-global/lib/node_modules/openclaw/ |

### 1.2 网络配置
| 项目 | 值 |
|------|-----|
| Gateway地址 | 127.0.0.1:18789 |
| Dashboard | http://127.0.0.1:18789/ |
| 内网IP | 192.168.36.133 |

### 1.3 Gateway服务
| 项目 | 值 |
|------|-----|
| 状态 | systemd运行中 (pid 195703) |
| 启动命令 | openclaw gateway start |
| 停止命令 | openclaw gateway stop |

---

## 二、已安装的技能 (27个)

### 2.1 飞书扩展技能 (4个)
| 技能 | 说明 | 状态 |
|------|------|------|
| feishu-doc | 飞书文档读写 | ✅ |
| feishu-drive | 飞书云盘 | ✅ |
| feishu-perm | 飞书权限管理 | ✅ |
| feishu-wiki | 飞书知识库 | ✅ |

### 2.2 系统内置技能 (4个)
| 技能 | 说明 | 状态 |
|------|------|------|
| gh-issues | GitHub Issues | ✅ |
| healthcheck | 安全审计 | ✅ |
| skill-creator | 技能创建器 | ✅ |
| weather | 天气查询 | ✅ |

### 2.3 从文件安装的技能 (10个) - 你提供的11个zip文件
| 技能 | 说明 | 状态 |
|------|------|------|
| Agent Browser | Rust浏览器自动化 | ✅ |
| Auto Updater | 自动更新技能 | ✅ |
| Find Skills | 查找安装新技能 | ✅ |
| GitHub | GitHub操作 | ✅ |
| Nano Banana Pro | Gemini 3 Pro图像 | ✅ |
| Notion | Notion集成 | ✅ |
| Proactive Agent | 主动式AI代理 | ✅ |
| Self Improving | 自我改进代理 | ✅ |
| Summarize | URL/文件摘要 | ✅ |
| Tavily Search | AI优化搜索 | ✅ |
| ArmouryCrateInstallTool | 非技能(华硕驱动) | ❌ |

### 2.4 从ClawHub安装的技能 (9个)
| 技能 | 说明 | 安装命令 |
|------|------|----------|
| blogwatcher | RSS博客监控 | npx skills add steipete/clawdis@blogwatcher |
| copilot-coding-agent | Copilot编程 | npx skills add supercent-io/skills-template@copilot-coding-agent |
| goplaces | Google Places | npx skills add heldinhow/openclaw-swarm@goplaces |
| product-management | 产品管理 | npx skills add vasilyu1983/ai-agents-public@product-management |
| project-manager | 项目管理 | npx skills add 404kidwiz/claude-supercode-skills@project-manager |
| python-mcp-server-generator | MCP服务器生成 | npx skills add github/awesome-copilot@python-mcp-server-generator |
| subagent-driven-development | 子代理开发 | npx skills add obra/superpowers@subagent-driven-development |
| test-driven-development | TDD测试驱动 | npx skills add obra/superpowers@test-driven-development |
| webapp-testing | Web应用测试 | npx skills add anthropics/skills@webapp-testing |

### 2.5 额外安装的AI/媒体技能
| 技能 | 说明 | 安装命令 |
|------|------|----------|
| imagegen | OpenAI图像生成 | npx skills add openai/skills@imagegen |
| spotify | Spotify控制 | npx skills add brgrp/skills@spotify |

---

## 三、团队成员

### 3.1 成员档案

**张振中 (张总)**
- 身份: 全球化AI平台与内容生产服务公司创始人
- 沟通风格: 犀利高效
- 决策模式: 张总提需求，瑞贝卡负责落地

**瑞贝卡 (Rebecca) - AI主控**
- 身份: 全能技术伙伴 / 技术总负责
- 上级: 张总
- 下级: 小Q

**小Q - AI编码助手**
- 身份: 编码执行者 (Qoder)
- 上级: 瑞贝卡
- 老板: 张总
- 特点: 编程能力强

---

## 四、已配置的账号

### 4.1 已授权
| 服务 | 账号 | 状态 |
|------|------|------|
| GitHub CLI | apple3z | ✅ 已授权 |
| Qoder | Eric Zhang (Pro Trial) | ✅ 已登录 |

### 4.2 待配置
| 服务 | 需要 | 状态 |
|------|------|------|
| Notion | API Key | ⏳ 等待中 |
| 阿里云 DashScope | API Key | ⏳ key无效 |

---

## 五、项目

### 5.1 GitHub仓库
| 仓库名 | 描述 | 状态 |
|--------|------|------|
| 基础系统 | 全球化AI平台建设方案 | ✅ 已创建 (private) |

### 5.2 飞书项目
| 名称 | 地址 | 状态 |
|------|------|------|
| 项目任务管理 | https://vcnticcwmng9.feishu.cn/base/P2xxbZI0lahIy1sXhCTcykUSnId | ✅ 已创建 |

---

## 六、待办事项

### 6.1 需要你帮忙
- [ ] Notion API Key - 去 https://www.notion.so/my-integrations 申请
- [ ] 阿里云 DashScope - 确认正确的 API Key
- [ ] Ollama (宿主机) - 本地大模型

### 6.2 可选配置
- [ ] Discord Bot Token
- [ ] Slack API Key
- [ ] OpenAI API Key (用于 imagegen)
- [ ] Spotify 账号

---

## 七、已安装的CLI工具

| 工具 | 版本 | 用途 |
|------|------|------|
| gh | 2.45.0 | GitHub CLI |
| Qoder | 0.1.29 | 编程助手 |
| obsidian-cli | 0.5.1 | Obsidian笔记 |
| uv | 0.10.8 | Python包管理 |
| nano-pdf | 0.2.1 | PDF处理 |

---

## 八、常用命令

```bash
# OpenClaw
openclaw status
openclaw gateway restart
openclaw security audit

# 技能管理
npx skills find <关键词>
npx skills add <owner/repo@skill> -g -y

# 编程
export PATH="$HOME/.npm-global/bin:$PATH" && qodercli -p "任务"
```

---

## 九、重要文件路径

| 用途 | 路径 |
|------|------|
| 工作区 | /home/zhang/.openclaw/workspace/ |
| 配置文件 | ~/.openclaw/openclaw.json |
| 技能库 | ~/.agents/skills/ |
| 日志 | /tmp/openclaw/openclaw-2026-03-06.log |

---

*此档案为永久记忆，每次系统更新后需同步更新*
