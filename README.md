# 蓝色高亮三轮修订

这是一个在 Codex 中使用的技能。提供 Turnitin 报告 PDF 和送检时的英文 Word 论文，Codex 会定位蓝色高亮，逐段完成三轮苹果翻译往返，再把定稿写回 Word 副本。如果一段只标蓝了半句，修改范围就只包含那半句。

第三轮苹果翻译的英文回译保存后，Codex 使用内置的 Humanizer 3.1.0 编辑标蓝片段。原始回译和编辑稿分别保留，便于对照作者语气、数据和引用。[Humanizer 上游项目](https://github.com/blader/humanizer) · [随附的 MIT 许可证](references/humanizer/LICENSE)

## 安装

蓝色高亮版在本仓库的 `turnitin-highlights` 分支维护。用下面的命令安装，随后可在技能目录中运行 `git pull --ff-only` 获取该分支的更新。

```sh
git clone --branch turnitin-highlights --single-branch https://github.com/BiwayTong/apple-translate-paper-revision.git ~/.codex/skills/turnitin-highlight-revision
```

如果设置了 `CODEX_HOME`，请将目标目录换为该目录下的 `skills/turnitin-highlight-revision`。打开新的 Codex 会话即可调用。需要复现加入 Humanizer 之前的流程时，可以使用[首发版 v1.0.0 安装包](https://github.com/BiwayTong/turnitin-highlight-revision/releases/download/v1.0.0/turnitin-highlight-revision.zip)。直接修订普通稿件请看[普通论文版（main 分支）](https://github.com/BiwayTong/apple-translate-paper-revision/tree/main)。

## 使用

附上报告及对应的 Word 文件，然后输入：

> 用 $turnitin-highlight-revision 提取报告中的蓝色高亮，跑完三轮苹果翻译，再把修改稿放回论文。

在 Mac 上准备两条使用苹果“翻译文本”动作的快捷指令，分别设置为英译中和中译英。默认示例名称为 `论文英译中` 和 `论文中译英`。PDF 与 Word 工具使用 Python、pdfplumber 和 lxml。无法调用快捷指令时，可以用苹果翻译手动回填并从断点继续。[操作说明](references/operations.md)

每轮保留中文原始译文、中文调整稿、英文回译原文和校正后的英文稿。下一轮从上一轮英文稿开始。交付内容包括修订后的 Word、编号摘录、三轮过程稿和修改记录。Turnitin 报告用来确定编辑范围；技能本身不运行检测或预测分数。
