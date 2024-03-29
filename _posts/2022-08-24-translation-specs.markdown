---
layout: post
title:  "翻译指南"
date:   2022-08-24 08:05:18 +0800
categories: evemodx translation
---

由于国服已经独立开发，国服更新进度已经严重滞后于世界服，且国服与欧服的中文资源已经产生了一些[冲突](https://p.sda1.dev/4/09628a3c84b47b5654e08276c319e240/Snipaste_2022-01-18_19-16-40.jpg)。且近期国服出于合规原因，对游戏文本进行了大范围的[和谐](https://blog.evemodx.com/2022/08/10/yc124-cn-servers/)，修改了大量表述。因此，EVE世界服汉化项目将不再使用国服的中文资源，而是进行独立的翻译工作。

这篇文章将会指导你如何进行翻译。为保证翻译的效率和质量，请加入 QQ 群 771790118 以便进行交流。

*(持续修订中)*

## 翻译平台使用

本项目使用[Weblate系统](https://weblate.evemodx.com/)进行翻译，对所有人开放注册，不同用户所拥有的权限如下（后者拥有前者权限）：

- 游客及注册用户：对翻译条目提出建议。
- 翻译：可提交并编辑翻译。
- 审校：对提交的翻译条目进行复查并批准。经过批准的字符串只有审校可以再次编辑。

更详细的说明可参阅[Weblate文档](https://docs.weblate.org/en/latest/workflows.html)

注册后可以在 QQ 群中获得翻译权限；审校权限将视情况发放。

### 进行翻译

在登录系统后，从顶部菜单进入 “EVE Online” 翻译项目 - “Tranquility” 部件- “中文（简体）” 点击右方翻译按钮或者“未完成的字符串”开始翻译。

请使用翻译页面底部的“附近字符串”功能进行上下文判断，并使用“其它的出现位置”和“自动建议”功能查找相同或者接近的翻译。当遇到不确定的名词或者表述时，可以新开窗口使用搜索功能进行查找。

在正式开始翻译前，请确保你已经阅读以下规范和特殊语法标记。

## 语言规范

### 用语

- 请优先使用游戏内一致的词语，如游戏内已出现“开采”，则翻译时近似的语境尽量不使用“采集”

### 标点及符号

- 请在 中文文字 与 英文字母、数字、符号 间加入空格，具体规则请参考 [ArchWiki](https://wiki.archlinux.org/title/Help:Style_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)#%E4%B8%AD%E8%8B%B1%E6%96%87%E6%B7%B7%E6%8E%92)

## 特殊语法标记

在翻译中，有一些特殊的标记将会在生成最终翻译文件时被特殊处理。

### `!DNT`

`!DNT` 代表这个条目不需要翻译.该字符串不会生成到最终文件中，而是由汉化工具 fallback 到英文条目。使用场景包括但不限于
- 英文原文标注了不需要翻译的条目 (Do not translate)
- 游戏中已经不再使用的字符串，例如 Dust514 的历史遗留
- 已经过期的活动相关字符串
- CCP 自己还没想好名字的东西（试炼纤维，文件名等）

### 格式化参数
CCP 在 EVE 的本地化模块中使用了一套自定义的格式化参数处理器，用于将变量正确格式化输出到文本中。由于这些附加参数对于生成游戏可用的最终文件不可或缺，我们将其拼接到了文本中，以便在翻译过程中进行处理。带有格式化参数的字符串结构如下：

```
文本模板
!====FORMAT-KWARGS====!
格式化参数
```

整个字符串分为两部分，由特殊分割字符串 `!====FORMAT-KWARGS====!` 单独占一行分开。文本模板中包含若干格式化占位符，使用 `{}` 标记；格式化字符串为一个 JSON 字符串，该 JSON 中的 key 与文本模板中的格式化占位符需要严格对应。在提交翻译时，系统将会对格式化参数进行[检查](https://p.sda1.dev/6/a4cb2a731739bdf36272e255f512f5bc/Snipaste_2022-08-24_09-03-56.png)。

在翻译含格式化参数的字符串时，只需要翻译文本模板，分割字符串和格式化参数字符串请原样复制到译文中，文本模板中的格式化占位符也需要保持原样，不要随意进行修改。
由于CCP在文件中混用了`\r\n`和`\n`，页面有时无法正确渲染换行符，**请不要直接从英文文本框中手动复制，而是使用右上角的“复制到剪贴板”或者“克隆到翻译”功能。**

但有以下情况时，则需要手动对格式化占位符和参数进行处理：

#### 复数形式

(TBD)

#### 所有格

(TBD)


