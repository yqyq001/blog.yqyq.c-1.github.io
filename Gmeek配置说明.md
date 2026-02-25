# Gmeek 配置说明

本文档详细介绍 `config.json` 文件中各项配置的作用和设置方法。

---

## 基础配置

### title
- **作用**：博客标题，显示在浏览器标签页和页面顶部
- **类型**：字符串
- **示例**：
```json
"title": "我的个人博客"
```

### displayTitle
- **作用**：页面显示的标题（可与 title 不同）
- **类型**：字符串（可选）
- **示例**：
```json
"displayTitle": "MyBlog"
```

### subTitle
- **作用**：博客副标题/描述，显示在首页标题下方
- **类型**：字符串
- **示例**：
```json
"subTitle": "记录生活，分享技术"
```

### homeUrl
- **作用**：博客首页地址（通常自动生成，无需手动配置）
- **类型**：字符串
- **说明**：如果仓库名为 `XXX.github.io`，则自动为 `https://XXX.github.io`

---

## 头像与图标

### avatarUrl
- **作用**：博主头像URL
- **类型**：字符串（图片URL）
- **示例**：
```json
"avatarUrl": "https://avatars.githubusercontent.com/u/12345678"
```

### faviconUrl
- **作用**：网站图标（浏览器标签页小图标）
- **类型**：字符串（图片URL，可选）
- **说明**：默认使用 avatarUrl
- **示例**：
```json
"faviconUrl": "https://example.com/favicon.ico"
```

### ogImage
- **作用**：社交分享时显示的预览图片
- **类型**：字符串（图片URL，可选）
- **说明**：默认使用 avatarUrl
- **示例**：
```json
"ogImage": "https://example.com/og-image.png"
```

---

## 背景图片配置（毛玻璃设计）

### desktopBackground
- **作用**：电脑端背景图片URL
- **类型**：字符串（图片URL）
- **说明**：建议使用高清图片，支持 jpg/png/webp 格式
- **示例**：
```json
"desktopBackground": "https://images.unsplash.com/photo-1506905925346-21bda4d32df4?w=1920"
```

### mobileBackground
- **作用**：手机端背景图片URL
- **类型**：字符串（图片URL）
- **说明**：建议使用适合手机屏幕的图片
- **示例**：
```json
"mobileBackground": "https://images.unsplash.com/photo-1507400492013-162706c8c05e?w=1080"
```

> **提示**：如果两个配置都为空，将显示默认的紫色渐变背景。推荐使用 Unsplash、Pexels 等免费图床获取背景图片。

---

## 主题与样式

### themeMode
- **作用**：主题模式切换方式
- **类型**：字符串
- **可选值**：
  - `"manual"` - 手动切换（显示切换按钮）
  - `"fix"` - 固定主题（不显示切换按钮）
- **示例**：
```json
"themeMode": "manual"
```

### dayTheme
- **作用**：日间主题样式
- **类型**：字符串
- **可选值**：`"light"`, `"light_colorblind"`, `"light_high_contrast"`
- **示例**：
```json
"dayTheme": "light"
```

### nightTheme
- **作用**：夜间主题样式
- **类型**：字符串
- **可选值**：`"dark"`, `"dark_colorblind"`, `"dark_high_contrast"`, `"dark_dimmed"`
- **示例**：
```json
"nightTheme": "dark"
```

### style
- **作用**：全局自定义CSS样式
- **类型**：字符串（CSS代码）
- **示例**：
```json
"style": "<style>body { font-family: 'Microsoft YaHei', sans-serif; }</style>"
```

### script
- **作用**：全局自定义JavaScript脚本
- **类型**：字符串（JS代码）
- **示例**：
```json
"script": "<script>console.log('欢迎访问！');</script>"
```

### head
- **作用**：在 `<head>` 标签内添加自定义内容
- **类型**：字符串
- **示例**：
```json
"head": "<meta name='keywords' content='博客,技术'>"
```

### indexStyle
- **作用**：首页专用CSS样式
- **类型**：字符串
- **示例**：
```json
"indexStyle": "<style>.avatar { border-radius: 50%; }</style>"
```

### indexScript
- **作用**：首页专用JavaScript脚本
- **类型**：字符串
- **示例**：
```json
"indexScript": "<script>/* 首页特效代码 */</script>"
```

---

## 国际化设置

### i18n
- **作用**：界面语言
- **类型**：字符串
- **可选值**：
  - `"CN"` - 简体中文
  - `"EN"` - 英文
  - `"RU"` - 俄语
- **示例**：
```json
"i18n": "CN"
```

---

## 文章列表设置

### onePageListNum
- **作用**：每页显示的文章数量
- **类型**：整数
- **默认值**：15
- **示例**：
```json
"onePageListNum": 10
```

---

## URL设置

### urlMode
- **作用**：文章URL生成方式
- **类型**：字符串
- **可选值**：
  - `"pinyin"` - 使用拼音（默认）
  - `"issue"` - 使用 Issue 编号
  - `"ru_translit"` - 俄语转写
- **示例**：
```json
"urlMode": "pinyin"
```

---

## 标签颜色设置

### commentLabelColor
- **作用**：评论数量标签的背景颜色
- **类型**：字符串（十六进制颜色值）
- **示例**：
```json
"commentLabelColor": "#006b75"
```

### yearColorList
- **作用**：不同年份文章的日期标签颜色
- **类型**：数组（颜色值数组）
- **说明**：颜色循环使用，如第1年用第1个颜色，第5年用第1个颜色
- **示例**：
```json
"yearColorList": ["#bc4c00", "#0969da", "#1f883d", "#A333D0"]
```

---

## 单页面设置

### singlePage
- **作用**：独立页面标签列表（这些标签的文章不会出现在首页列表）
- **类型**：数组
- **示例**：
```json
"singlePage": ["about", "links"]
```
> 创建标签为 `about` 的 Issue 后，该文章将作为独立页面，可通过导航栏访问。

---

## 其他设置

### startSite
- **作用**：网站建立日期，用于显示"网站运行X天"
- **类型**：字符串（日期格式）
- **示例**：
```json
"startSite": "2024-01-01"
```

### filingNum
- **作用**：网站备案号（中国大陆用户适用）
- **类型**：字符串
- **示例**：
```json
"filingNum": "京ICP备12345678号"
```

### UTC
- **作用**：时区设置
- **类型**：整数
- **默认值**：+8（北京时间）
- **示例**：
```json
"UTC": 8
```

### rssSplit
- **作用**：RSS摘要分割符
- **类型**：字符串
- **可选值**：
  - `"sentence"` - 按句子分割（中文用"。"，英文用"."）
  - 其他字符 - 按指定字符分割
- **示例**：
```json
"rssSplit": "sentence"
```

### showPostSource
- **作用**：是否显示文章来源链接（跳转到GitHub Issue）
- **类型**：整数（1=显示，0=隐藏）
- **示例**：
```json
"showPostSource": 1
```

### needComment
- **作用**：是否启用评论功能
- **类型**：整数（1=启用，0=禁用）
- **示例**：
```json
"needComment": 1
```

### bottomText
- **作用**：文章底部显示的文字
- **类型**：字符串
- **示例**：
```json
"bottomText": "本文采用 CC BY-NC-SA 4.0 协议"
```

### allHead
- **作用**：所有页面 `<head>` 中添加的内容
- **类型**：字符串
- **示例**：
```json
"allHead": "<meta name='author' content='Your Name'>"
```

### exlink
- **作用**：外部链接（显示在导航栏）
- **类型**：对象
- **示例**：
```json
"exlink": {
  "GitHub": "https://github.com/yourname",
  "Twitter": "https://twitter.com/yourname"
}
```

### iconList
- **作用**：自定义图标SVG路径
- **类型**：对象
- **示例**：
```json
"iconList": {
  "GitHub": "M8 0c4.42 0 8 3.58 8 8a8.013..."
}
```

---

## 完整配置示例

```json
{
  "title": "我的博客",
  "displayTitle": "MyBlog",
  "subTitle": "记录生活，分享技术",
  "avatarUrl": "https://avatars.githubusercontent.com/u/12345678",
  "faviconUrl": "https://example.com/favicon.ico",
  "desktopBackground": "https://images.unsplash.com/photo-1506905925346-21bda4d32df4?w=1920",
  "mobileBackground": "https://images.unsplash.com/photo-1507400492013-162706c8c05e?w=1080",
  "themeMode": "manual",
  "dayTheme": "light",
  "nightTheme": "dark",
  "i18n": "CN",
  "onePageListNum": 15,
  "urlMode": "pinyin",
  "commentLabelColor": "#006b75",
  "yearColorList": ["#bc4c00", "#0969da", "#1f883d", "#A333D0"],
  "singlePage": ["about"],
  "startSite": "2024-01-01",
  "filingNum": "",
  "UTC": 8,
  "rssSplit": "sentence",
  "showPostSource": 1,
  "needComment": 1,
  "bottomText": "",
  "style": "",
  "script": "",
  "head": "",
  "indexStyle": "",
  "indexScript": "",
  "allHead": "",
  "exlink": {},
  "iconList": {}
}
```

---

## 注意事项

1. **修改配置后需要全局重新生成**：通过 `Actions -> build Gmeek -> Run workflow` 重新构建
2. **JSON格式要求**：确保配置文件是有效的JSON格式，注意引号和逗号
3. **图片URL**：确保图片URL可公开访问，建议使用稳定的图床服务
4. **备份配置**：修改前建议备份原有的 `config.json` 文件

---

如有问题，请访问 [Gmeek GitHub](https://github.com/Meekdai/Gmeek) 提交 Issue。
