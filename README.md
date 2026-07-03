# GitHub Pages 内容更新源

把这个目录里的文件发布到 GitHub Pages 后，App 可以通过 `manifest.json` 下载新增章节。

## 发布结构

推荐把 `github-pages` 目录里的内容作为 Pages 根目录：

```text
manifest.json
books/葬天神庭/正文/第051章_待更新.md
```

如果你的 Pages 地址是：

```text
https://你的用户名.github.io/你的仓库名/
```

那么 App 里的更新地址应该是：

```java
private static final String REMOTE_MANIFEST_URL =
        "https://你的用户名.github.io/你的仓库名/manifest.json";
```

这个常量在：

```text
app/src/main/java/com/kaelyn/reader/MainActivity.java
```

## 新增章节

1. 把新的 `.md` 章节放到 `books/葬天神庭/正文/`。
2. 在 `manifest.json` 的 `chapters` 里追加一条。
3. 推送到 GitHub Pages。
4. 打开 App 首页，点「检查」。

`manifest.json` 支持两种写法。

使用 `baseUrl + path`：

```json
{
  "book": "葬天神庭",
  "version": 2,
  "baseUrl": "https://你的用户名.github.io/你的仓库名/",
  "chapters": [
    {
      "title": "第051章_新的试炼",
      "file": "第051章_新的试炼.md",
      "path": "books/葬天神庭/正文/第051章_新的试炼.md"
    }
  ]
}
```

或者每章直接写完整 `url`：

```json
{
  "book": "葬天神庭",
  "version": 2,
  "chapters": [
    {
      "title": "第051章_新的试炼",
      "file": "第051章_新的试炼.md",
      "url": "https://你的用户名.github.io/你的仓库名/books/葬天神庭/正文/第051章_新的试炼.md"
    }
  ]
}
```
