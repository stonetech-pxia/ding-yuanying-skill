# 丁元英 · Claude Skill

让 Claude 用丁元英（豆豆小说《遥远的救世主》、电视剧《天道》主人公）的思想、思维方式和学养来回答你的问题。

**只取他的思想和文化水平，不复述剧情，不谈书中人物。**

> A Claude skill that answers in the reasoning and voice of Ding Yuanying, the protagonist of the Chinese novel *遥远的救世主* (TV adaptation: *天道*). It carries his ideas and erudition only — no plot retelling. Content is in Chinese.

---

## 效果示例

> **问：** 我是一家30人创业公司的老板。我觉得强势文化说白了就是优胜劣汰，所以打算把绩效排最后的几个人直接裁掉，补偿能少给就少给，反正他们也闹不出什么。这样做挺符合天道的吧？
>
> **答：** 你这问题命题错误。强势文化不是优胜劣汰，跟“补偿能少给就少给”更挨不上边。
>
> 裁人本身没什么好说的。雇佣是一笔契约，合不来就散，这是规矩。可规矩是两头的：你有权按规矩请人走，人家也有权按规矩拿走该拿的那份。前一半你要，后一半你想省，还算准了“他们闹不出什么”——这就是欺负拿你没办法的人，指望规则为你弯一弯。这叫破格获取，是强盗的路数。你以为这是强，其实是弱。
>
> ……
>
> 天道不站谁的队。规律不为员工弯，也不为老板弯，它只管收账。裁不裁、裁谁，是你的事。要裁，就按规矩给足、把话说明白。
>
> （节选自本 skill 的一次测试输出）

能聊的范围：人生选择、事业商业、投资、职场人际、感情、社会文化、宗教哲学、艺术审美，也包括 AI、躺平、原生家庭这类书里没有的现代话题。

## 和“语录合集”有什么不同

- **有推演，不是背语录。** 他的思想被整理成三条根命题：规律不为任何人弯曲；人被自己看不见的“主”推着走；出路只有觉悟，而觉悟没法转交。十几条立场都从这三条推出来，遇到书里没有的情境，就从根上推。
- **矛盾推到底。** 宿命与主体性、强势与善、看透与安住、如实与用诈……八处最容易演错的地方，逐条写清楚他会怎么处理。
- **区分来源。** 推演文件里每条判断都标注【原文】【推论】【延伸】；引用的原话都对照原著核对过，附章节号。
- **辨伪。** 网上流传的不少“丁元英语录”出自电视剧改编或纯属杜撰（比如“养儿防老”“父母是天然债权人”“等靠要”），skill 里单独列了核对清单，扮演时不会用。
- **不洗白，不神化。** 他的傲慢、嗔心、对女性的偏见、心不能安住，都保留着。

## 安装

### 方式一：Claude Code 插件（推荐）

在 Claude Code 里依次运行：

```
/plugin marketplace add stonetech-pxia/ding-yuanying-skill
```

```
/plugin install ding-yuanying@ding-yuanying
```

也可以直接在终端里装：

```bash
claude plugin marketplace add stonetech-pxia/ding-yuanying-skill
```

```bash
claude plugin install ding-yuanying@ding-yuanying
```

装好后重启 Claude Code，或在会话里运行 `/reload-plugins`。

以后更新到最新版：

```bash
claude plugin marketplace update ding-yuanying
```

```bash
claude plugin update ding-yuanying@ding-yuanying
```

### 方式二：手动放进 skills 目录

全局可用（所有项目）——macOS / Linux / Git Bash：

```bash
git clone https://github.com/stonetech-pxia/ding-yuanying-skill.git ~/.claude/skills/ding-yuanying
```

Windows PowerShell：

```powershell
git clone https://github.com/stonetech-pxia/ding-yuanying-skill.git "$env:USERPROFILE\.claude\skills\ding-yuanying"
```

只在某个项目里用：在项目根目录运行

```bash
git clone https://github.com/stonetech-pxia/ding-yuanying-skill.git .claude/skills/ding-yuanying
```

以后更新：在克隆下来的目录里运行 `git pull`。

### 方式三：Claude 网页版 / 桌面版

下载 [仓库 zip](https://github.com/stonetech-pxia/ding-yuanying-skill/archive/refs/heads/main.zip)，在 Claude 的技能（Skills）设置里上传。具体入口以 Claude 当前的界面为准。

## 使用

直接这样说就会触发：

- “用丁元英的角度回答：……”
- “你是丁元英，……”
- “丁元英会怎么看……”
- “让丁哥说两句”
- 提到强势文化、弱势文化、文化属性、破格获取，并想听他的视角

想跳出角色、正常讨论小说本身时，直接说“跳出角色”。

## 文件结构

```
ding-yuanying-skill/
├── SKILL.md                    # 入口：人设、思维内核、回答流程、说话方式、边界
├── references/
│   ├── derivation.md           # 推演层：三条根命题、推导链、八处矛盾、书外推法与示范
│   ├── thinking-model.md       # 思想体系：本体论、文化属性论、认识论、价值排序、方法论、人生观、伦理观、隐藏命题、局限
│   ├── culture.md              # 学养：知识构成、怎么用学问、两种语域、审美标准、作诗填词
│   ├── voice.md                # 口吻：句式、词汇、禁忌、示范对话
│   ├── quotes.md               # 思想性原话（按主题分类，附章节）
│   └── commentary.md           # 网上的解读与批评、误传语录核对
└── .claude-plugin/             # Claude Code 插件与插件市场配置
```

`SKILL.md` 每次触发都会加载；`references/` 里的文件按需读取。

## 边界

- **不讲剧情**：问到书里的人和事，他会说“那些事不提了”，转去谈道理。
- **不编原话**：拿不准是不是原著原文，就不说成是他说的。
- **真实危险面前跳出角色**：用户流露出自伤、轻生念头时，先放下角色，正常回应并提供求助渠道。
- **不构成专业建议**：投资、法律、医疗等重大决定，只帮你看清结构和风险，具体请咨询专业人士。

## 声明

- 这是非官方的人物思想研究与角色扮演工具，与作者豆豆、出版方及电视剧《天道》的制作方无关。
- 书中引文的版权归原作者所有，这里只为评论和研究做少量引用。本仓库**不包含小说全文**。权利人如认为不妥，请提 issue，我会处理。
- “推论”“延伸”部分是对人物的解读，不代表作者本意。

## 许可

本仓库的原创分析文字采用 [MIT](LICENSE) 许可。小说引文不在授权范围内，版权归原作者所有。
