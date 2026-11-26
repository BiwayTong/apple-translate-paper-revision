# 普通论文 · Google 翻译 · Humanizer 版

附上英文 Word、UTF-8 文本或直接粘贴英文。可以指定全文或选段，使用网页方式时无需 API Key。第三轮英文回译保存后，内置的 Humanizer 3.1.0 只在指定范围内复核一次，保留作者原意、数字和引用。

[下载本版 ZIP](https://github.com/BiwayTong/apple-translate-paper-revision/releases/latest/download/google-translate-paper-revision.zip) · [四个版本的下载与用法](https://github.com/BiwayTong/apple-translate-paper-revision#选一个版本)

## 安装和使用

1. 解压 ZIP，将 `google-translate-paper-revision` 整个目录放到 `~/.codex/skills/`。如果自定义了 `CODEX_HOME`，则放入该目录下的 `skills/`。
2. 可直接用 Google 翻译网页。需要自动调用时，在 Google Cloud 项目中启用 Cloud Translation API，并配置 API Key 或应用默认凭据。
3. 打开新的 Codex 会话，附上稿件或粘贴英文，输入下面的请求。

> 用 $google-translate-paper-revision 用 Google 翻译网页修订我贴出的英文段落，跑完三轮。保留我的措辞，给我最终英文和每轮过程稿。

每轮保存四种过程稿，下一轮承接上一轮英文。第三轮原始回译与 Humanizer 复核稿分别保存。Word 回填需要 Python 和 lxml。使用应用默认凭据时另需 `google-auth[requests]`。 [操作与断点恢复](references/workflow.md) · [Humanizer 许可证](references/humanizer/LICENSE)

如需通过 Git 安装本分支，可运行以下命令。

```sh
git clone --branch google-translate --single-branch https://github.com/BiwayTong/apple-translate-paper-revision.git ~/.codex/skills/google-translate-paper-revision
```
