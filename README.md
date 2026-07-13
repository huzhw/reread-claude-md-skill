# reread-claude-md

重新加载全局和项目级 CLAUDE.md 规则的 Claude Code 技能。

## 解决了什么问题

Claude Code 长对话中，**上下文会逐步压缩**。全局 CLAUDE.md 和项目 CLAUDE.md 里写的规则（三步确认流程、国内镜像下载、交互风格等）可能在多轮对话后被精简甚至丢弃，导致 AI 行为不再符合规则——比如忘了回复开头加"亲爱的架构师"、跳过了确认词流程等。

这个技能提供了一个**一键重载**机制：用户说一句触发词，AI 立刻重新读取两份 CLAUDE.md 并回归规则约束。

## 怎么工作

1. 用户在对话中感觉 AI 行为异常（比如没加"亲爱的架构师"）
2. 说出触发词"规则丢了"
3. AI 执行技能：读取 `~/.claude/CLAUDE.md` + `<项目>/CLAUDE.md`
4. 确认关键规则（三步流程、确认词、国内镜像、git-commit 等）已重新加载
5. 后续回复恢复正常

**"亲爱的架构师"开头本身就是探针**——AI 漏了这句 = 规则丢了 = 该触发重载。

## 为什么需要它

| 方式 | 可靠性 |
|------|--------|
| 靠记忆 | ❌ 上下文压缩就忘 |
| 项目 memory 文件 | ❌ 一样会被压缩 |
| 用户手动提醒 | ⚠️ 得打一堆字 |
| **Skill 外部触发** | ✅ 系统级加载，不受压缩影响 |

Skill 作为独立模块被系统加载，不依赖当前对话上下文——即使 CLAUDE.md 已从上下文中消失，Skill 本身仍然可用。

## 触发词

"重新读 claude.md"、"重读规则"、"规则丢了"、"规则呢"、"reread"

## 安装

```bash
git clone https://github.com/huzhw/reread-claude-md-skill.git ~/.claude/skills/reread-claude-md
```

安装后重启 Claude Code，在任意对话中说"规则丢了"即可触发。

## 使用建议

- **主动检查**："亲爱的架构师"没出现 = 规则丢了 = 触发
- **不确定时**：直接说"规则丢了"，零成本验证

---

## 参见

- [git-commit](https://github.com/huzhw/git-commit-skill)：Git 提交规范
- [coding-rules](https://github.com/huzhw/coding-rules)：AI 编码协作规范
- [daily-record](https://github.com/huzhw/daily-record-skill)：日报记录
- [daily-merge](https://github.com/huzhw/daily-merge-skill)：日报合并

## 许可

MIT
