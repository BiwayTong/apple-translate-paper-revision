# 英文论文三轮翻译修订 · Humanizer 版

这组 Codex 技能适用于整篇英文论文、指定章节或 Turnitin 报告中的蓝色高亮。每轮用选定的工具英译中、核对中文，再译回英文。**第三轮英文回译原样保存后，才用内置的 Humanizer 3.1.0 复核一次。** 能沿用作者原句的地方就沿用。

## 选一个版本

| 你要修订的内容 | 翻译工具 | 安装包 | 使用说明 |
| --- | --- | --- | --- |
| 全文、章节或自选段落 | [苹果翻译](https://github.com/BiwayTong/apple-translate-paper-revision/tree/main) | [下载 ZIP](https://github.com/BiwayTong/apple-translate-paper-revision/releases/latest/download/apple-translate-paper-revision.zip) | [首页示例](#apple-paper) · [详细指南](https://github.com/BiwayTong/apple-translate-paper-revision/blob/main/references/workflow.md) |
| 全文、章节或自选段落 | [Google 翻译](https://github.com/BiwayTong/apple-translate-paper-revision/tree/google-translate) | [下载 ZIP](https://github.com/BiwayTong/apple-translate-paper-revision/releases/latest/download/google-translate-paper-revision.zip) | [首页示例](#google-paper) · [详细指南](https://github.com/BiwayTong/apple-translate-paper-revision/blob/google-translate/references/workflow.md) |
| Turnitin 标蓝的字句 | [苹果翻译](https://github.com/BiwayTong/apple-translate-paper-revision/tree/turnitin-highlights) | [下载 ZIP](https://github.com/BiwayTong/apple-translate-paper-revision/releases/latest/download/turnitin-highlight-revision.zip) | [首页示例](#apple-highlights) · [详细指南](https://github.com/BiwayTong/apple-translate-paper-revision/blob/turnitin-highlights/references/operations.md) |
| Turnitin 标蓝的字句 | [Google 翻译](https://github.com/BiwayTong/apple-translate-paper-revision/tree/turnitin-highlights-google) | [下载 ZIP](https://github.com/BiwayTong/apple-translate-paper-revision/releases/latest/download/turnitin-highlight-google-revision.zip) | [首页示例](#google-highlights) · [详细指南](https://github.com/BiwayTong/apple-translate-paper-revision/blob/turnitin-highlights-google/references/operations.md) |

## 安装与准备

1. 下载所选版本的 ZIP 并解压。将里面含有 `SKILL.md` 的整个目录放入 `~/.codex/skills/`，保留目录名。如果自定义了 `CODEX_HOME`，则放入该目录下的 `skills/`。Humanizer 已随包提供。
2. **苹果翻译**自动运行需要 Mac 上两条使用苹果「翻译文本」动作的快捷指令，分别设为英译中和中译英。**Google 翻译**可以使用网页，也可以用已启用 Cloud Translation API 的项目自动调用。API 方式按项目计费。
3. 打开新的 Codex 会话，附上文件或粘贴正文，复制下方对应版本的请求。

## 四种用法

<a id="apple-paper"></a>

### 普通论文 · 苹果翻译

附上英文 Word，写明章节名即可。也可以提供 UTF-8 文本或粘贴英文，指定全文或段落。

> 用 $apple-translate-paper-revision 只修订这篇英文 Word 的 Discussion 章节，用苹果翻译跑完三轮。第三轮英文回译后复核一次，尽量保留我的原句和引用，给我 Word 副本和过程稿。

<a id="google-paper"></a>

### 普通论文 · Google 翻译

附上英文 Word、UTF-8 文本或直接粘贴英文。可以指定全文或选段，使用网页方式时无需 API Key。

> 用 $google-translate-paper-revision 用 Google 翻译网页修订我贴出的英文段落，跑完三轮。保留我的措辞，给我最终英文和每轮过程稿。

<a id="apple-highlights"></a>

### Turnitin 蓝色高亮 · 苹果翻译

附上 Turnitin 报告 PDF 和送检时的英文 Word 原稿。按报告页码定位标蓝范围。一段只标蓝半句，就只处理那半句。

> 用 $turnitin-highlight-revision 从报告中提取标蓝的字句，用苹果翻译跑完三轮，只把必要的改动放回送检的 Word 原稿副本。给我修订稿和带页码的摘录。

<a id="google-highlights"></a>

### Turnitin 蓝色高亮 · Google 翻译

附上报告 PDF 和对应的英文 Word 原稿。已有编号摘录时也可以先修订，取得匹配的 Word 底稿后再回填。

> 用 $turnitin-highlight-google-revision 用 Google 翻译网页处理报告标蓝的片段，跑完三轮。按原位置回填 Word，保留引用和未标蓝的句子，另附过程稿。

## 会收到什么

定稿另存为副本。过程稿按编号保留每轮的中文原始译文、中文调整稿、英文回译原文和英文调整稿。第二、三轮分别承接上一轮校正后的英文。你可以对照第三轮英文回译与复核稿，查看 Humanizer 实际改了哪里。没有明确问题时，两份稿件可以完全相同。

交付还包括重点段落对照、必要修改的理由、待核实问题和注明统计口径的正文词数。高亮版另附编号摘录，便于回到报告核对位置。

[各版本发布记录](https://github.com/BiwayTong/apple-translate-paper-revision/releases) · [Humanizer 项目](https://github.com/blader/humanizer) · [随包许可证](references/humanizer/LICENSE) · [三轮翻译基础版](https://github.com/BiwayTong/paper-revision-translation-only)

<details>
<summary>用 Git 安装普通论文苹果翻译版</summary>

```sh
git clone --branch main --single-branch https://github.com/BiwayTong/apple-translate-paper-revision.git ~/.codex/skills/apple-translate-paper-revision
```

</details>
