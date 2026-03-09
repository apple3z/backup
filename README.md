# OpenClaw 系统备份

**备份日期**: 2026-03-09  
**系统版本**: OpenClaw 2026.3.7  
**负责人**: 张振中 (张总)  
**代理**: 瑞贝卡 (Rebecca)

---

## 📁 备份结构

```
backup/
├── config/          # 配置文件
│   ├── openclaw.json.*    # OpenClaw 主配置 (带时间戳)
│   ├── cron-jobs.json     # Cron 任务配置
│   └── hooks-list.txt     # Hooks 列表
├── workspace/       # 工作区文件
│   ├── AGENTS.md          # 多代理工作流
│   ├── SOUL.md            # 行为指南
│   ├── TOOLS.md           # 工具配置
│   ├── USER.md            # 用户资料
│   ├── IDENTITY.md        # 代理身份
│   ├── HEARTBEAT.md       # 心跳配置
│   ├── MEMORY.md          # 长期记忆
│   └── memory/            # 每日记忆文件
├── skills/          # 技能清单
│   └── installed-skills.txt
└── docs/            # 文档
    └── BACKUP_SYSTEM_REPORT.md  # 完整系统报告
```

---

## 🔄 恢复流程

### 从本地备份恢复

```bash
# 1. 停止 Gateway
openclaw gateway stop

# 2. 恢复配置文件
cp ~/.openclaw/backup/config/openclaw.json.* ~/.openclaw/openclaw.json

# 3. 恢复工作区
cp -r ~/.openclaw/backup/workspace/* ~/.openclaw/workspace/

# 4. 重启 Gateway
openclaw gateway restart
```

### 从 GitHub 备份恢复

```bash
# 1. 克隆备份仓库
cd /tmp
git clone https://github.com/apple3z/backup.git openclaw-backup
cd openclaw-backup

# 2. 停止 Gateway
openclaw gateway stop

# 3. 恢复配置
cp config/openclaw.json.* ~/.openclaw/openclaw.json
cp -r workspace/* ~/.openclaw/workspace/

# 4. 重启 Gateway
openclaw gateway restart
```

---

## ⚠️ 敏感信息

**备份中已脱敏的信息：**
- ❌ API Keys (模型服务、飞书等)
- ❌ Token (Gateway 认证)
- ❌ 个人凭据

**恢复后需要手动配置：**
1. ✅ 更新 `openclaw.json` 中的 API Keys
2. ✅ 更新飞书应用凭据 (appId, appSecret)
3. ✅ 验证 GitHub 认证 (`gh auth status`)
4. ✅ 检查 Gateway Token

---

## 📅 备份策略

### 自动备份
- **频率**: 每次重大配置变更后
- **位置**: `~/.openclaw/backup/`
- **保留**: 最近 3 个版本

### GitHub 备份
- **仓库**: https://github.com/apple3z/backup
- **频率**: 每周或重大变更后
- **可见性**: Public

### 本地备份
- **频率**: 实时 (配置变更时)
- **位置**: `~/.openclaw/backup/`
- **保留**: 最近 3 个版本

---

## 📋 备份清单

### 已备份
- [x] OpenClaw 主配置
- [x] Cron 任务配置
- [x] Hooks 配置
- [x] 工作区核心文件 (AGENTS.md, SOUL.md, etc.)
- [x] 记忆文件 (memory/)
- [x] 技能清单
- [x] 完整系统报告

### 未备份 (敏感信息)
- [ ] API Keys
- [ ] Token
- [ ] 个人凭据

---

## 🔧 维护任务

### 每次备份后
1. 验证备份文件完整性
2. 更新备份日期
3. 提交到 GitHub (如适用)

### 每月检查
1. 验证备份可恢复性
2. 清理过期备份
3. 更新系统报告

---

## 📞 联系

- **系统管理员**: 张振中
- **代理**: 瑞贝卡 (Rebecca)
- **时区**: Asia/Shanghai (UTC+8)
- **文档**: https://docs.openclaw.ai

---

**最后更新**: 2026-03-09 13:36
