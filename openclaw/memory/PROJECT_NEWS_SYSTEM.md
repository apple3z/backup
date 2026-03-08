# 📁 项目档案 - News System (新闻系统)

> 接收时间: 2026-03-07
> 所有者: 张振中 (张总)
> 状态: 已接收，正在分析

---

## 一、项目概述

### 1.1 基本信息

| 项目 | 值 |
|------|-----|
| 项目名 | news_system |
| 技术栈 | Python Flask + SQLite |
| 主文件 | /home/zhang/news_system/app.py (3204行) |
| 数据目录 | /home/zhang/news_system/data/ |
| 启动方式 | ./start.sh 或 python app.py |

### 1.2 功能模块

| 模块 | 功能 | 状态 |
|------|------|------|
| /news | 新闻浏览 | 正常 |
| /skills | Skills浏览 | 正常 |
| /subscribe | 订阅管理 | 正常 |
| /sys | 系统管理 | ❌ 有Bug |
| /wiki | 研发Wiki | ❌ 有Bug |
| /dev | 开发页面 | 正常 |

---

## 二、数据库

| 数据库 | 大小 | 用途 |
|--------|------|------|
| news.db | 1.1MB | 新闻数据 |
| skills.db | 8KB | Skills数据 |
| subscribe.db | 12KB | 订阅数据 |
| news.json | 9KB | 新闻缓存 |

---

## 三、文档结构

### 3.1 版本管理文档
```
版本管理/
├── README.md              # 版本索引
├── v2.4.0/             # 已完成
│   └── (12个文档)
└── v2.5.0/             # 进行中 (当前)
    ├── 00-文档索引.md
    ├── 01-规划.md       ✅
    ├── 02-需求.md       ✅
    ├── 03-架构.md       ✅
    ├── 04-技术.md       ✅
    ├── 05-更新介绍.md   ✅
    ├── 06-测试计划.md   ✅
    ├── 07-测试报告.md   ✅
    ├── 08-问题清单.md   ✅
    ├── 09-迭代日志.md   🔄
    ├── 10-发布说明.md   ✅
    └── 11-状态看板.md   🔄
```

### 3.2 其他文档目录
- 版本历史/
- 文档中心/
- docs/

---

## 四、已知问题 (从日志分析)

### 4.1 Bug表现
从 app.log 发现大量 400 错误：
```
GET /api/v2/wiki/read/研发管理规范.md HTTP/1.1" 400
GET /api/v2/wiki/read/文档撰写规范.md HTTP/1.1" 400
```

### 4.2 Bug清单 (v2.5.0待修复)

| 编号 | 问题 | 状态 |
|------|------|------|
| B01 | 版本历史重复显示 | 📋 待开发 |
| B02 | 文档点击无响应 | 📋 待开发 |
| B03 | 版本顺序混乱 | 📋 待开发 |
| B04 | 文档列表不匹配 | 📋 待开发 |
| B05 | 保存后无法查看 | 📋 待开发 |
| B06 | 路径逻辑混乱 | 📋 待开发 |

---

## 五、核心API路由

```
# 新闻
GET /news/<id>           # 新闻详情

# Skills  
GET /skills              # Skills列表
GET /skill/<id>         # Skill详情

# 订阅
GET /subscribe          # 订阅管理
POST /api/subscribe     # 添加订阅

# 系统管理
GET /sys                # 系统主页
GET /sys/version/<vid>/<type>  # 版本文档

# Wiki
GET /wiki/<file>        # Wiki浏览
GET /wiki/<file>/edit   # Wiki编辑
POST /api/wiki/<file>   # 保存Wiki
```

---

## 六、关键文件

| 文件 | 行数 | 用途 |
|------|------|------|
| app.py | 3204 | 主应用 |
| fetch_news.py | - | 新闻抓取 |
| utils/version_manager.py | - | 版本管理 |
| templates/sys_v2.html | - | 系统页面 |

---

## 七、启动信息

```bash
cd /home/zhang/news_system
./start.sh
# 或
python app.py
```

访问: http://localhost:5000

---

## 八、张总的项目分工

- **瑞贝卡**: 技术实现，代码开发
- **小Q**: 编码执行 (辅助)
- **张总**: 产品需求，决策

---

## 九、下一步

1. 确认Bug优先级
2. 制定修复计划
3. 开始编码

---

*档案建立: 2026-03-07*
*档案更新: 2026-03-07 01:00*
