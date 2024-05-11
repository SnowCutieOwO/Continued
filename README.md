# Continued
Translated resources public repository.

## 介绍 Introduction

因为 MCBBS 挂了，所以要在这里放上之前 MCBBS 里面的资源。

`Continue` 是个人的私用仓库，而 `Continued` 是所有用户均可发表的。

希望火种不会灭。有你们而更精彩。

## 贡献人员 Contributor

* [RaymondChang1204](https://github.com/RaymondChang1204)：
  * BlackJack (Wiki)
  * HardcoreSeasons (Wiki)
* [Sy1rKimihiro](https://github.com/Sy1rKimihiro)
  * MyWorld (Wiki)

## 推荐标准

### 文件命名

`章节名称.子章节名称`

* 全部小写
* 单个符号以 `-` 代替，如 `第一章：以 Apple 为例` -> `第一章-以-apple-为例`
* 多个符号以一个 `-` 代替，如 `注意事项！！——不要使用模组端` -> `注意事项-不要使用模组端`

* 示例：
  ```
  🏠 General
      🔌 Getting Started
  ```
  则该章节在文件中命名为：`general.getting-started.md`（无视 emoji 符号且一律遵照上述规则）

### 图片命名

`章节名称.子章节名称[.序号].png/jpg`

* 规则与上方 `.md` 文件命名相同，此条规则针对图片
* 若**原维基存在图片且可获得图片原件，则文件名称保持一致**

### 更新格式

标题：`Updated [文件名称.文件后缀]`
正文：N/A

* 建议使用英文
* 正文可简要概括更新包含的内容
* 正文附加描述不建议超过三行

标题：`Synced update with [原文章节名称]`

* 引用的`原文章节名称`与原维基保持一致，但只需子章节标题即可
* 其他规则见[文件命名](#文件命名)

> [!NOTE]
> 注意，Github 会自动将 commit 连接转化为 **作者/仓库名称:@xxxxxx** 的格式。

### css 文件夹

`css\文件名称.css/cssx`

* 全部小写
* 根据功能或原出处进行简短而合适的命名
* 针对引用的层叠样式表

### 目录结构

```
前言
更新日志
主页
---
正文章节
```

* 前言：填写翻译相关信息，如碎碎念、翻译字数及时间、参与用户等
* 更新日志：用于翻译备忘的可选章节，默认存放维基的文本更新内容，及撰写时的维护内容，固定命名为 `changelog.md`
* 主页：若有，将插件维基的主页译文置入此页，此页若不存在侧边栏，则固定命名为 `home.md`
* 正文章节：文章的正常目录结构

### 附加信息

#### 翻译信息

```
翻译作者：xxx
翻译时间：
最后校对：
翻译字数：
```

翻译作者：参与翻译的用户名称，请尽量填写常用平台名称及联系方式    
翻译时间：翻译完成/发布的时间点，精确到日即可    
最后校对：最后编辑修改的时间，精确到日即可    
翻译字数：文章全文包括目录在内的字数统计    

> [!TIPS]
> [Continue 后台仓库](https://www.github.com/SnowCutieOwO/snowcutieowo.github.io)中包含了一个用于计算维基字数的 `.py` 脚本，名为 `hiCount`。