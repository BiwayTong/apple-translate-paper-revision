# Turnitin 蓝色高亮修订 · Google 翻译版

附上 Turnitin 报告 PDF 和送检时的英文 Word 原稿，Codex 会按报告页码定位蓝色高亮，只修订选中的字句。三轮英中往返都使用 Google 翻译，每一轮从上一轮校正后的英文继续。定稿回填到 Word 副本，并附上编号摘录、各轮原始译文和调整稿、重点段落对照、修改记录及正文词数。

## 安装和使用

```sh
git clone --branch turnitin-highlights-google --single-branch https://github.com/BiwayTong/apple-translate-paper-revision.git ~/.codex/skills/turnitin-highlight-google-revision
```

打开新的 Codex 会话，附上两份文件后输入：

> 用 $turnitin-highlight-google-revision 提取报告里的蓝色高亮，用谷歌翻译跑完三轮，只把标蓝的部分放回 Word，给我定稿和过程包。

如果只有已经提取的高亮文本，也可以先做三轮修订，取得对应的 Word 底稿后再定位回填。

## 翻译方式

- **Google 翻译网页**可直接使用，无需 API Key。逐段取得原始译文后导入，程序核对编号、源文、轮次和方向。[Google 翻译](https://translate.google.com/)
- **Google Cloud Translation API** 支持自动调用。使用已启用 Cloud Translation API 的项目，设置环境变量 `GOOGLE_TRANSLATE_API_KEY` 或配置应用默认凭据。计费与配额由所用项目决定。[身份验证](https://cloud.google.com/translate/docs/authentication) · [计费](https://cloud.google.com/translate/pricing)

PDF 和 Word 在本地处理。Python 依赖为 `pdfplumber` 和 `lxml`，使用应用默认凭据时另需 `google-auth[requests]`。提取工具支持矩形色带；批注型高亮、扫描件与跨格式的选区可按操作指南逐处定位核对。[操作指南](references/operations.md)

同一仓库也提供[普通稿件 Google 版](https://github.com/BiwayTong/apple-translate-paper-revision/tree/google-translate)、[蓝色高亮苹果翻译版](https://github.com/BiwayTong/apple-translate-paper-revision/tree/turnitin-highlights)和[普通稿件苹果翻译版](https://github.com/BiwayTong/apple-translate-paper-revision/tree/main)。
