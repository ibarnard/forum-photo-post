# BBCode 格式速查表

适用于 Discuz! X 论坛的 BBCode 映射规则。

## 不输出的内容

以下 HTML 元素**不转换**到 BBCode：
- `<nav>` 导航栏
- `<header>` 文章标题区（含 meta 信息行）
- `<footer>` 页脚（除非用户要求）
- CSS 样式、class、id 等

## 格式映射

| HTML 元素 | BBCode | 说明 |
|-----------|--------|------|
| 主标题 `<h1>` | `[align=center][size=6][b]标题[/b][/size][/align]` | 居中、大号、加粗 |
| 章节标题 `<h2>` | `[size=6][b]标题[/b][/size]` | 左对齐、大号、加粗 |
| 图片 `<img>` | `[img]文件名.jpg[/img]` | 占位符，上传后替换为 `[attachimg]ID[/attachimg]` |
| 图注 | `[align=center][size=4][color=gray]▲ [b]图X[/b] 描述[/color][/size][/align]` | 居中、灰色、小字、图号加粗 |
| 引用 `<blockquote>` | `[quote]内容[/quote]` | 不嵌套引号 |
| 加粗 `<strong>` / `**` | `[b]文字[/b]` | |
| 视频（B站） | `[media=x,800,600]BV号[/media]` | 或直接保留 iframe 链接 |
| 超链接 `<a>` | `[url=地址]文字[/url]` | |
| 段落 `<p>` | 空行 | 段落间用空行分隔 |

## 禁止使用的 BBCode

- 不使用分隔线 `────` 或 `[hr]`
- 不输出 CSS 背景色 `[backcolor]`
- 不使用过多的字号变化（保持 title=6, caption=4, body=默认）

## 图片引用替换

当用户提供附件 ID 映射后，按上传后的实际文件名进行替换：
```
[img]实际上传文件名.jpg[/img] → [attachimg]论坛返回的附件ID[/attachimg]
```

ID 映射规则：以第一张图片的附件 ID 为起始，若论坛返回的 ID 连续递增，后续编号自动计算。文件名取 4.1 重命名后的实际名称，不预设固定前缀。

## 示例

```
[align=center][size=6][b][深圳]带娃打卡 西蒙神奇车库六周年展[/b][/size][/align]

最近刷小红书，看到西蒙神奇车库的六周年展回到了深圳南山海岸城...

[attachimg]11842450[/attachimg]
[align=center][b]商场入口闪电麦昆和Sally[/b][/align]
[align=center][size=4][color=gray]▲ [b]图1[/b] 商场入口就是西蒙复古赛车的展区大门[/color][/size][/align]

  [quote]部分资料来自于网络，不一定正确，欢迎补充。[/quote]
```
