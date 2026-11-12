# GitHub 发布清单（词键 KeyWord）

这个目录只发布**编译产物 + 功能说明**，不发布源码。上传前请对照下面的清单确认。

---

## 一、仓库信息

**仓库名**

```
typewords-android
```

（主名 `typewords` 已被大量项目占用，加 `android` 后缀既唯一又表明平台）

**About / Description**（GitHub 只允许一段，建议英文，利于站内与搜索引擎命中）

```
An offline Android vocabulary trainer that makes you type every word: 100 built-in wordlists, three-stage practice (follow along / dictation / recall), no account, no network, no tracking.
```

**Topics**（复制到仓库首页右上角 ⚙ 的 Topics 里，一行一个，GitHub 会把它们做成可搜索标签）

```
android
android-app
kotlin
jetpack-compose
vocabulary
english-learning
english-vocabulary
spelling
dictation
typing-practice
wordbook
dictionary
word-lists
cet4
cet6
ielts
toefl
gre
offline
education
```

> 想再提高曝光，把 `cet4` / `ielts` / `toefl` / `gre` 这类**考试关键词**保留在上面的列表里——国内用户多数是靠"四六级 / 雅思 / 托福背单词"这类词搜过来的。

---

## 二、Release 文案

**Tag / Release title**

```
v1.0
```

**Release notes（直接粘贴）**

```markdown
首个公开版本，仅提供编译好的安装包。

## 特点
- 100 本词库全部内置、全部离线（四六级 / 考研 / 雅思 / 托福 / GRE / 专四专八 / 商务英语 / 中小学 …）
- 三阶段练习：跟写 → 听写 → 默写，全程键盘输入，不靠"看一眼点认识"
- 记忆曲线自动排程，每天新词 + 到期复习自动编排
- 收藏本 / 未掌握词本 / 自建词典
- 发音、例句、词源均在本机完成，不联网、不上传、无账号

## 安装
下载 `KeyWord-1.0.apk` 传进手机安装，Android 8.0 及以上。
包为调试签名，可直接侧载；安装时如提示"未知来源"，允许一次即可。

## 文件校验
- 大小：92,458,898 字节（88.2 MiB）
- SHA-256：`0752B4197B29EFEB9C5787EDB5653DE11E72EF1E05AABCBC9D7ECB197782E851`

授权采用离线授权码，**一个码只绑一台手机**，授权规则见 README 的「授权与免费范围」。
```

---

## 三、要上传的文件

上传到仓库根目录（或先在本地准备好，用网页的 "Add file → Upload files" 一次拖进去）：

| 文件 | 说明 |
|---|---|
| `README.md` | 仓库首页说明，必须传 |
| `KeyWord-1.0.apk` | 安装包；GitHub 单文件上限 100 MB，本包 88.2 MiB 可以直接放仓库 |
| `SHA256.txt` | 校验值，方便用户核对 |
| `screenshots/home.png` | 首页截图 |
| `screenshots/dicts.png` | 词库页截图 |
| `screenshots/follow.png` | 跟写页截图 |
| `screenshots/listen.png` | 听写页截图 |
| `screenshots/mine.png` | 我的页（授权与设备码）截图 |

更推荐的做法：`README.md` + `SHA256.txt` 放仓库，APK 挂到 **Releases**（Releases → Draft a new release → 选 tag `v1.0` → 上传 APK），仓库体积不会随版本膨胀，用户从 Releases 下载也更直观。

**不要上传**：源码、`tools\secret.key`、`tools\license_records.json`（发码密钥与客户记录必须留在本机，密钥泄露后所有授权码都可被伪造）。

---

## 四、操作步骤（网页版，不用命令行）

1. GitHub 右上角 **+ → New repository**
2. Repository name 填 `typewords-android`，Description 粘贴上面的英文描述
3. 选 **Public**，**不要**勾 "Add a README file"（本地已有）
4. 创建后进入仓库，点 **Add file → Upload files**，把本目录的 `README.md`、`SHA256.txt`、`screenshots\` 拖进去，Commit
5. 点右上角 **⚙**（About 旁），把 Topics 逐个粘进去
6. 左侧 **Releases → Draft a new release**：Tag 填 `v1.0`，标题 `v1.0`，说明粘贴上面的 Release notes，附件上传 `KeyWord-1.0.apk`，Publish release
7. 回到仓库首页，确认 README 里的图片能正常显示（相对路径 `screenshots/xxx.png` 只在仓库内有效）

---

## 五、发布前自查

- [ ] `KeyWord-1.0.apk` 与 `SHA256.txt` 里的哈希一致（`Get-FileHash .\KeyWord-1.0.apk -Algorithm SHA256`）
- [ ] 手机上覆盖安装一次，确认能启动、能激活、词库能解锁
- [ ] README 里没有出现密钥、序列号规则、内部文件路径
- [ ] 微信联系方式是你愿意公开的那个
