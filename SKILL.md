---
name: reread-claude-md
description: 重新读取全局和项目级 CLAUDE.md 规则文件。触发词：重新读 claude.md、重新读 claude、重读规则、读规则、重新加载规则、规则丢了、规则呢。
author: 胡志伟
motto: "规则再好的规则，加载回来才算数。"
---

# 重新加载 CLAUDE.md 规则

## 执行

收到触发请求后，立即执行：

1. 读取全局 CLAUDE.md：`C:\Users\Administrator\.claude\CLAUDE.md`
2. 读取项目 CLAUDE.md：`<当前工作区>/CLAUDE.md`（如果存在）
3. 确认关键规则已加载：
   - 回复开头加"亲爱的架构师："
   - 编辑前走三步流程（分析 → 方案+确认词 → 等回复）
   - 方案结尾带随机四字成语确认词
   - 用户说"改""行""好"不算确认，必须回确认词
   - git 提交走 git-commit skill
   - 下载走国内镜像
4. 报告"规则已加载"即可，不用重复全文

## 参见
- [git-commit](https://github.com/huzhw/git-commit-skill)：Git 提交流程
- [daily-record](https://github.com/huzhw/daily-record-skill)：日报记录
- [daily-merge](https://github.com/huzhw/daily-merge-skill)：日报合并

