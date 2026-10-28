# 课件空间清理 Skill

帮助 Codex 整理 Windows 或 macOS 上的课件项目，先选择保留程度，再分析文件、依赖和候选清理量。适合课件历史版本、预览图和制作素材长期积累的情况。

| 方案 | 主要清理内容 | 样本预计清理 |
|---|---|---:|
| A 保守 | 早期预览图等可再生产物 | 3.9% |
| B 售后修改 | 旧工作 PPT、过程预览、指定回退版本、已确认的营销资料 | 58.3% |
| C 交付优先 | B 的候选项及非必要制作源文件和重建过程 | 77.7% |

百分比来自一个 **13.62 GiB 课件的未执行候选清单**，不是其他项目的承诺或实测释放量。实际结果取决于文件和依赖检查；会保留尚不能确认用途的文件。

## 安装

支持 Agent Skills 的客户端可使用（需要 Node.js 和 npx）：

```bash
npx -y skills add pan-11/courseware-storage-cleanup -g --all
```

也可以下载仓库，将 `skills/courseware-storage-cleanup` 文件夹复制到 Codex 的 skills 目录：

- Windows：`%USERPROFILE%\.codex\skills\courseware-storage-cleanup`
- macOS：`~/.codex/skills/courseware-storage-cleanup`

如果配置了其他 Codex skills 目录，请放到对应目录。`SKILL.md`、`agents` 和 `references` 要一起保留。

## 使用

在 Codex 中输入：

> 使用 $courseware-storage-cleanup，帮我整理这个课件，先让我选择清理方式。

Skill 会展示三档及清理内容，核对实际文件、占用位置、保留资料和依赖，再给出候选清单。**选择档位只代表选择分析方向，实际删除须确认具体清单。**

完成后，如果空间仍不足，Skill 会说明如何核对和删除不再需要的 Codex 聊天。课件清理不会自动删除聊天；归档或压缩上下文不保证释放聊天记录的磁盘空间。

## 适用范围与验证

- 不包含清理脚本或自动定期删除任务；Skill 使用客户端已有的文件工具。
- 会区分实际存储卷、云文件状态、备份占用，以及文件大小与实测释放量。
- Windows 侧已完成结构及流程验证；macOS 侧已做规则审阅和情景模拟，**尚未在 Mac 上实机验证**。
- 本仓库包含运行 Skill 所需文件，不包含课件正文、聊天记录、私人路径或本地工作日志。
