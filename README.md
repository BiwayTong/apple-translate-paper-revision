# Turnitin 蓝色高亮 · 苹果翻译 · Humanizer 版

附上 Turnitin 报告 PDF 和送检时的英文 Word 原稿。按报告页码定位标蓝范围。一段只标蓝半句，就只处理那半句。第三轮英文回译保存后，内置的 Humanizer 3.1.0 只在指定范围内复核一次，保留作者原意、数字和引用。

[下载本版 ZIP](https://github.com/BiwayTong/apple-translate-paper-revision/releases/latest/download/turnitin-highlight-revision.zip) · [四个版本的下载与用法](https://github.com/BiwayTong/apple-translate-paper-revision#选一个版本)

## 安装和使用

1. 解压 ZIP，将 `turnitin-highlight-revision` 整个目录放到 `~/.codex/skills/`。如果自定义了 `CODEX_HOME`，则放入该目录下的 `skills/`。
2. 在 Mac 上准备两条使用苹果「翻译文本」动作的快捷指令，分别用于英译中和中译英。
3. 打开新的 Codex 会话，附上报告和对应的 Word 稿，输入下面的请求。

> 用 $turnitin-highlight-revision 从报告中提取标蓝的字句，用苹果翻译跑完三轮，只把必要的改动放回送检的 Word 原稿副本。给我修订稿和带页码的摘录。

每轮保存四种过程稿，下一轮承接上一轮英文。第三轮原始回译与 Humanizer 复核稿分别保存。PDF 高亮定位和 Word 回填需要 Python、pdfplumber 和 lxml。 [操作与断点恢复](references/operations.md) · [Humanizer 许可证](references/humanizer/LICENSE)

如需通过 Git 安装本分支，可运行以下命令。

```sh
git clone --branch turnitin-highlights --single-branch https://github.com/BiwayTong/apple-translate-paper-revision.git ~/.codex/skills/turnitin-highlight-revision
```
