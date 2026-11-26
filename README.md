# 英文论文三轮修订

把英文 Word 论文、UTF-8 文本或一段粘贴的正文交给 Codex，就能按全文、指定章节或段落运行三轮中英文往返修订。稿件可以直接使用，无需标色或检测报告。

第三轮苹果翻译的英文回译保存后，Codex 使用内置的 Humanizer 3.1.0 编辑指定范围内的英文。原始回译和编辑稿分别保留，便于对照作者语气、数据和引用。[Humanizer 上游项目](https://github.com/blader/humanizer) · [随附的 MIT 许可证](references/humanizer/LICENSE)

想用 Google 翻译完成相同的三轮流程，可以安装 [Google 翻译版（google-translate 分支）](https://github.com/BiwayTong/apple-translate-paper-revision/tree/google-translate)。支持 Google Cloud Translation API 和 Google 翻译网页，两种渠道都会保留原始译文。

如果你有 Turnitin 报告，希望只修订标蓝的句子，请使用同一仓库的 [蓝色高亮版（turnitin-highlights 分支）](https://github.com/BiwayTong/apple-translate-paper-revision/tree/turnitin-highlights)。

## 安装与使用

在 Codex 的个人技能目录中新建 `apple-translate-paper-revision` 文件夹，将本仓库的 `SKILL.md`、`agents/`、`references/` 和 `scripts/` 放进去。默认目录为 `~/.codex/skills/`。也可以用 Git 安装：

```sh
git clone https://github.com/BiwayTong/apple-translate-paper-revision.git ~/.codex/skills/apple-translate-paper-revision
```

打开一个新的 Codex 会话，附上文稿并说明范围，例如：

> 用 $apple-translate-paper-revision 只修订这篇论文的 Discussion 章节，跑完三轮，给我 Word 副本和过程稿。

每轮先用苹果翻译英译中，编辑中文，再用苹果翻译译回英文并校对；下一轮以上一轮英文稿为输入。最终交付包括定稿、过程稿、重点段落对照、修改记录及词数。自动翻译需要 Mac 上已配置的两个苹果翻译快捷指令，也支持导入用户实际取得的苹果译文。文本工具使用 Python，Word 处理另需 lxml。[操作说明](references/workflow.md)
