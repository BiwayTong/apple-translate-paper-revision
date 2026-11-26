# Google 翻译论文三轮修订

给 Codex 一份英文 Word、UTF-8 文本或粘贴的段落，指定全文或章节，即可用 Google 翻译连续做三轮英中往返修订。每轮先将英文译成中文，调整中文表达，再译回英文。下一轮从刚校正的英文开始。最终交付另存的稿件、每轮四份过程稿、重点段落对照、修改记录与词数。

## 安装

```sh
git clone --branch google-translate --single-branch https://github.com/BiwayTong/apple-translate-paper-revision.git ~/.codex/skills/google-translate-paper-revision
```

打开新的 Codex 会话，附上文稿，例如：

> 用 $google-translate-paper-revision 修订这篇论文的 Discussion，跑完三轮，给我 Word 副本和过程稿。

## 选择翻译方式

- **自动调用 API**。在 Google Cloud 项目中启用 Cloud Translation API，并设置环境变量 `GOOGLE_TRANSLATE_API_KEY`，或配置应用默认凭据。每个选中段落会发送给 Google，费用按项目的使用量计算。[Google 身份验证](https://cloud.google.com/translate/docs/authentication) · [计费说明](https://cloud.google.com/translate/pricing)
- **使用 Google 翻译网页**。无需 API Key。Codex 可在能够访问网页时逐段翻译，也可导出带编号的待译表，导入从网页取得的原始译文并续跑。[打开 Google 翻译](https://translate.google.com/)
- **运行环境**。使用 Python 3，Word 回填另需 `lxml`，使用应用默认凭据另需 `google-auth[requests]`。每次翻译都记录实际来源、轮次和语言方向。[操作与恢复](references/workflow.md)

本仓库也提供[苹果翻译版](https://github.com/BiwayTong/apple-translate-paper-revision/tree/main)和[苹果翻译蓝色高亮版](https://github.com/BiwayTong/apple-translate-paper-revision/tree/turnitin-highlights)。
