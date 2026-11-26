# 蓝色高亮三轮修订

这是一个在 Codex 中使用的技能。提供 Turnitin 报告 PDF 和送检时的英文 Word 论文，Codex 会定位蓝色高亮，逐段完成三轮苹果翻译往返，再把定稿写回 Word 副本。如果一段只标蓝了半句，修改范围就只包含那半句。

## 安装

从发布页下载 `turnitin-highlight-revision.zip`，解压后将整个 `turnitin-highlight-revision` 文件夹放入 `~/.codex/skills/`。如果设置了 `CODEX_HOME`，则放入该目录下的 `skills/`。打开新的 Codex 会话即可调用。[下载发布包](https://github.com/BiwayTong/turnitin-highlight-revision/releases/latest)

## 使用

附上报告及对应的 Word 文件，然后输入：

> 用 $turnitin-highlight-revision 提取报告中的蓝色高亮，跑完三轮苹果翻译，再把修改稿放回论文。

在 Mac 上准备两条使用苹果“翻译文本”动作的快捷指令，分别设置为英译中和中译英。默认示例名称为 `论文英译中` 和 `论文中译英`。PDF 与 Word 工具使用 Python、pdfplumber 和 lxml。无法调用快捷指令时，可以用苹果翻译手动回填并从断点继续。[操作说明](references/operations.md)

每轮保留中文原始译文、中文调整稿、英文回译原文和校正后的英文稿。下一轮从上一轮英文稿开始。交付内容包括修订后的 Word、编号摘录、三轮过程稿和修改记录。Turnitin 报告用来确定编辑范围；技能本身不运行检测或预测分数。
