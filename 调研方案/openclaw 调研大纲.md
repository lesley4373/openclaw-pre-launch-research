# OpenClaw 调研大纲

> **调研目标**：全面摸底 OpenClaw，产出"从项目理解直达创业决策"的研究框架
>
> **核心认知校准**：OpenClaw 不是"又一个开源 Agent 项目"。它正在从工具走向平台，形成产品叙事、生态叙事和分发叙事的三重结构。调研时应按"AI-native personal assistant runtime"来审视，而非按单一 Agent 项目来审视。
>
> **项目快照**（截至 2026.3.19）：~320K Stars | 61K Forks | 300+ Contributors | 27K+ PRs | 最新 release 2026.3.13 | 创始人 Peter Steinberger 已加入 OpenAI | 项目转 501(c)(3) 独立基金会 | MIT 许可证
>
> **统一分析模板**：每个一级模块结尾，统一用以下 6 问收敛到创业判断——
> ① 它是什么 ② 它为什么重要 ③ 它现在做得怎么样 ④ 它最强的点是什么 ⑤ 它最弱的点是什么 ⑥ 这对我的创业意味着什么
>
> **方法论**：本框架的三层递进结构（"它是什么" → "它为什么是现在这样" → "这对我意味着什么"）基于 SCR 叙事结构；模块设计综合运用 JTBD、平台经济学、Conway's Law、STEPPS 传播模型、战略群组分析、制度套利理论等方法论。详见附录 B「方法论索引」。框架本身只保证"问对问题"，结论质量取决于实际调研深度和验证实验结果。

---

## 框架全景图

```
第一层：理解它是什么（模块 1-4）
  ├─ 一、项目定位与一句话定义        → 产出：我能否用一句话说清它是什么、不是什么
  ├─ 二、目标用户与使用场景          → 产出：我应该瞄准哪类用户
  ├─ 三、产品能力地图（7 层模型）     → 产出：我应该在哪一层做增强/补足/替代
  └─ 四、技术架构与代码质量          → 产出：我能否在它的架构上搭建，还是需要另起炉灶

第二层：理解它为什么是现在这样（模块 5-10）
  ├─ 五、生态系统与可扩展性          → 产出：我应该做生态内应用，还是做生态基础设施
  ├─ 六、增长机制与传播解码          → 产出：我应该复制传播策略、借势流量、还是等热潮退去
  ├─ 七、竞争格局与对标分析          → 产出：我应该做替代者、增强层、垂类版本、还是分发渠道
  ├─ 八、商业模式与变现路径          → 产出：我应该切哪条变现路径、启动资金从哪来
  ├─ 九、市场规模与趋势             → 产出：我应该赌多大的市场
  └─ 十、核心体验链路与关键时刻      → 产出：我应该在哪个体验环节做差异化

第三层：这对我意味着什么（模块 11-14）
  ├─ 十一、风险全景与供应链依赖审计   → 产出：我的风险对冲策略是什么
  ├─ 十二、创始人离场与项目生命力     → 产出：我是否需要设计"OpenClaw 无关化"退出策略
  ├─ 十三、创业者-机会匹配度审计     → 产出：综合能力和资源，我最应该选哪条路
  └─ 十四、创业决策层               → 产出：一个可执行的创业行动方案
```

---

# 第一层：理解它是什么

---

## 一、项目定位与一句话定义

### 为什么要调研这部分
所有后续分析——竞品比较、用户判断、路径选择——都建立在"你怎么定义 OpenClaw"之上。如果你把它理解为"一个 Agent 框架"，你的竞品表里会放 LangChain 和 CrewAI；如果你理解为"一个个人 AI 操作系统"，你的竞品表里会放 Siri 和 Copilot。定义错了，后面所有分析都歪。更关键的是，OpenClaw 满足的到底是功能需求还是身份/控制感需求，直接决定了你创业时应该打"功能牌"还是"品牌牌"——前者拼性能和价格，后者拼社区和叙事。

### 最终要达成的判断
> 用一句话说清 OpenClaw 是什么、不是什么，它解决的核心需求属于功能层、情感层还是身份层。这个判断直接输入到模块七（竞品选谁来对标）和模块十四（创业定位选择）。

### 1.1 官方定位解析

**关键调研问题**：
- OpenClaw 的官方 slogan 和自我定义是什么？它强调的是"personal assistant"而非"agent framework"，这个措辞选择意味着什么？
- 它试图替代什么（Siri? ChatGPT App? 各类 AI Bot?），补足什么（跨平台、本地运行、数据自主）？
- 它的核心用户心智是什么——"我有一个自己的 AI"，还是"我有一个更好用的 AI 工具"？
- 它最突出的差异化关键词：own-your-data / messaging-first / model-agnostic / local-first——哪个在实际传播中最有效？
- 它从"工具"走向"产品"的关键包装方式是什么？（看 GitHub 首页、onboarding 流程、品牌视觉）

**推荐调研方法/工具**：
- `GitHub README` 精读：提取核心 positioning 语言
- `openclaw.ai/blog/introducing-openclaw`：官方发布博文
- `open-claw.org`：基金会官网定位
- `VISION.md`（三个仓库）：openclaw / clawhub / lobster
- 对比其他项目（Auto-GPT / Dify / Open Interpreter）的 README 措辞差异

### 1.2 三层需求定义

**关键调研问题**：
- **显性需求**（functional job）：跨平台消息接入、随时可用、语音交互、本地运行——这些功能层面解决了什么？
- **隐性需求**（emotional job）：用户不想每次打开某个 AI App，而是希望 AI 出现在已有沟通渠道里——这个"无感嵌入"的心智有多强？
- **深层需求**（social/identity job）：对"拥有自己的 assistant""数据自己掌控""长期陪伴型 AI"的满足——这到底是功能痛点，还是身份感和控制感的需求？
- 关键判断：如果它解决的是功能痛点，容易被替代；如果解决的是身份感/控制感需求，更容易形成品牌势能。OpenClaw 属于哪一类？

**推荐调研方法/工具**：
- `Discord 社区` 潜水：观察用户自发描述"为什么用 OpenClaw"的原话
- `Hacker News 讨论串`：提取正反面用户动机
- `Bilibili / 小红书评论区`：中国用户的使用动机和情感表达
- `Reddit r/openclaw`（如有）：英文社区用户画像

### 🔻 6 问收敛
> ① 它是什么？ ② 为什么这个定位重要？ ③ 它现在定位清晰吗？ ④ 定位中最强的锚点是什么？ ⑤ 定位中最模糊/最脆弱的地方是什么？ ⑥ 如果我创业，应该沿用这个定位、细化这个定位、还是错位竞争？

**⭐ 必读**

| 材料                                                         | 类型     | 语言  | 价值点                                                       |
| ------------------------------------------------------------ | -------- | ----- | ------------------------------------------------------------ |
| [VISION.md（主仓库）](https://github.com/openclaw/openclaw/blob/main/VISION.md) | 官方文档 | EN    | 创始人亲写的项目愿景，定位原话："an assistant that can run real tasks on a real computer"，选择 TypeScript 的理由，安全哲学，MCP 策略 |
| [OpenClaw 官网首页](https://openclaw.ai/)                    | 官网     | EN    | 品牌定位、用户证言（"open source built a better Siri"）、官方 slogan 集合 |
| [Introducing OpenClaw — 官方博客](https://openclaw.ai/blog/introducing-openclaw) | 博客     | EN    | 官方首次发布的自我定义                                       |
| [36Kr：OpenClaw 正在重新定价所有 AI 创业赛道](https://eu.36kr.com/en/p/3681452218461832) | 深度分析 | EN/CN | 关键定位洞察："执行中心 + 工具生态 + 权限系统"，slogan "Your assistant. Your machine. Your rules" |

**📖 推荐阅读**

| 材料                                                         | 价值点                                                       |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [DigitalOcean：What is OpenClaw?](https://www.digitalocean.com/resources/articles/what-is-openclaw) | 面向入门者的定义解读，提炼了"JARVIS"类比                     |
| [KDnuggets：OpenClaw Explained](https://www.kdnuggets.com/openclaw-explained-the-free-ai-agent-tool-going-viral-already-in-2026) | 从"chatbot"到"programmable digital worker"的定位演进         |
| [Wikipedia: OpenClaw](https://en.wikipedia.org/wiki/OpenClaw) | 中立第三方视角的定义、历史、争议全景                         |
| [CNBC/CCTV 报道](https://www.cnbc.com/2026/03/11/cctv-script-11/03/26.html) | 主流媒体如何向大众定义 OpenClaw："The AI that actually does things" |

---

## 二、目标用户与使用场景

### 为什么要调研这部分
OpenClaw 有 32 万 stars，但 stars 不是用户。320K 里有多少人只是点了个星，有多少人真的每天在用，有多少人在为它花钱——这三个数字之间可能差两个数量级。如果你不搞清楚"真实活跃用户是谁"，你设计的产品就是在服务一个幻想中的市场。更具体地说，中国市场的"养龙虾"热潮制造了大量围观流量，但围观流量不等于付费意愿。你需要穿透热度，找到那些真正有需求、有预算、有使用场景的用户群体。

### 最终要达成的判断
> 明确你的创业应该瞄准哪一类用户（开发者/效率用户/企业/消费者），以及这类用户在中国市场的规模、获客渠道和付费意愿。这个判断直接输入到模块八（变现路径选择）和模块十三（能力匹配度评估）。

### 2.1 用户分层画像

**建议分 6 类用户分别分析**：

| 用户类型 | 核心分析维度 |
|----------|-------------|
| 极客开发者 | 被什么吸引？最先用哪个入口？最容易留在哪个功能？最可能因什么流失？是否愿意付费？愿意为什么付费？ |
| 个人效率重度用户 | 同上 |
| 内容创作者 | 同上 |
| 独立开发者 / AI 创业者 | 同上 |
| 跨平台消息重度用户 | 同上 |
| "私人 AI 管家"高意愿消费人群 | 同上 |

### 2.2 中国市场特殊用户群

**关键调研问题**：
- "养龙虾"文化中，技术用户 vs 跟风用户 vs 政策驱动用户的比例？
- 腾讯 QClaw 开放后，微信生态内的用户画像和使用场景？
- B 站/小红书教程的受众——他们是"学技术"还是"赶潮流"？
- 闲鱼代部署服务的买家画像——他们的真实需求是什么？
- 企业用户（尤其龙岗补贴政策覆盖的眼镜/珠宝/家具/跨境电商行业）的需求和付费意愿？

### 2.3 使用场景优先级

**关键调研问题**：

- 高频场景 Top 5 是什么？（日常对话？信息检索？自动化任务？内容创作？代码辅助？）
- 哪些场景用户粘性最高？哪些场景尝鲜后即流失？
- 中国市场的高价值场景是否与全球不同？（微信生态、企业微信/钉钉/飞书场景）

**推荐调研方法/工具**：

- `Discord` + `GitHub Discussions`：用户自发分享的 use case
- `datacamp.com/blog/openclaw-projects`：9 个 OpenClaw 项目案例
- `ClawHub` 热门 skills 排行：反推高频使用场景
- **实际部署 + 使用 2 周**：第一手体验日志
- `闲鱼/淘宝`：分析代部署服务的描述词（反推买家需求）

### 🔻 6 问收敛
> ① 它的核心用户到底是谁？ ② 这个用户群为什么重要？ ③ 目前用户基础的质量如何（深度使用 vs 围观）？ ④ 最强的用户粘性点是什么？ ⑤ 最大的用户流失风险是什么？ ⑥ 如果我创业，应该瞄准哪类用户？

**⭐ 必读**

| 材料                                                         | 类型     | 价值点                                                       |
| ------------------------------------------------------------ | -------- | ------------------------------------------------------------ |
| [Discord "Friends of the Crustacean"](https://discord.gg/openclaw)（需加入） | 社区     | 直接观察用户自发描述"为什么用 OpenClaw"的原话，#help 频道高频问题 = 高频卡点 |
| [DataCamp：9 OpenClaw Projects to Build](https://www.datacamp.com/blog/openclaw-projects) | 教程     | 9 个真实使用案例，反推高频场景（Reddit Bot、自愈服务器、自动化工作流等） |
| [Fortune："养龙虾"如何改变中国 AI 行业](https://fortune.com/2026/03/14/openclaw-china-ai-agent-boom-open-source-lobster-craze-minimax-qwen/) | 深度报道 | 中国用户画像：学生/退休人员/白领排队装 OpenClaw，闲鱼代装 500 元/次 |
| [CNBC：中国科技公司争相部署 OpenClaw](https://www.cnbc.com/2026/03/12/china-openclaw-ai-agent-adoption-tech-companies-government-support-lobster-shrimp.html) | 新闻     | JD.com 399 元远程安装服务、百度总部排队现场、腾讯"龙虾特种兵"产品矩阵 |

**📖 推荐阅读**

| 材料                                                         | 价值点                                                 |
| ------------------------------------------------------------ | ------------------------------------------------------ |
| [ClawHub Skills 注册表](https://github.com/openclaw/clawhub)（GitHub） | 热门 Skills 排行 → 反推高频使用场景                    |
| [Medium："60 天打破 React 十年纪录，但没人知道该拿它怎么办"](https://medium.com/@aftab001x/openclaw-just-beat-reacts-10-year-github-record-in-60-days-now-nobody-knows-what-to-do-with-it-937b8f370507) | 用户困惑的真实声音，围观 vs 深度使用的张力             |
| [Bilibili 搜索"OpenClaw"/"养龙虾"](https://www.bilibili.com/) | 中国用户的真实教程内容，观察受众是"学技术"还是"赶潮流" |
| [闲鱼搜索"OpenClaw 部署"](https://www.xianyu.com/)           | 代部署服务定价 + 买家留言 → 反推非技术用户的真实需求   |

---

## 三、产品能力地图（7 层模型）

### 为什么要调研这部分
创业最常犯的错误之一是"在别人最强的地方跟别人竞争"。如果你不清楚 OpenClaw 的能力在 7 个层面上分别处于什么水平，你就无法判断应该在哪一层做增强（它已经强但还不够的地方）、在哪一层做补足（它还没做好的地方）、在哪一层做替代（它做得差且难以改善的地方）。更进一步，在一个分层系统中，价值最终会聚合到某一层——你必须找到那个价值聚合层，围绕它设计商业模式。

### 最终要达成的判断
> 明确 OpenClaw 7 层中哪层是护城河（不应正面竞争）、哪层是标配（竞品可追平）、哪层是短板（存在创业机会），以及价值最终聚合在哪一层。这个判断直接输入到模块七（竞品的真正差异化维度）和模块十四（创业切入的具体层级）。

### 3.1 七层能力分析

| 层级 | 分析内容 | 关键问题 |
|------|---------|---------|
| **接入层** | 22+ 消息渠道、语音入口、设备平台（macOS/iOS/Android/Linux/Web） | 多渠道抽象是否足够优雅？新渠道接入成本多高？ |
| **交互层** | 文本、语音、Canvas 可视化工作区、主动提醒、长期对话 | 交互体验在哪个渠道上最好？Canvas 成熟度如何？ |
| **能力层** | 模型调用（多 LLM 路由）、工具调用、Skills 系统、Lobster 自动化引擎 | Skills 和 Lobster 是否形成了真正的能力壁垒？ |
| **记忆层** | 个人记忆、上下文管理、长期偏好学习 | 记忆能力的持久性和精准度如何？与竞品差距多大？ |
| **执行层** | 操作应用、搜索信息、调用本地/远程工具、浏览器控制 | 执行可靠性如何？成功率和出错时的恢复机制？ |
| **控制层** | Gateway 控制面、配置管理、权限控制、安全边界、沙箱隔离 | 权限模型是否能支撑企业级需求？ |
| **体验层** | onboarding 流程、安装成本（30-60 分钟）、响应速度、稳定性 | 第一次体验到底有多丝滑？最容易劝退的环节是什么？ |

### 3.2 护城河判断

**关键调研问题**：
- 7 层中，哪些层是 OpenClaw 的真正护城河？（初步假设：接入层的多渠道抽象 + 能力层的 Skills 生态）
- 哪些层是"标配"——竞品可以快速追平？
- 哪些层是当前短板——存在被竞品反超的风险？
- 从"能跑起来的仓库"到"能长出生态的平台"，它的抽象做得够好吗？

**推荐调研方法/工具**：
- **本地部署全链路体验**：从安装到接通第一个渠道到日常使用，逐层记录
- `docs.openclaw.ai`：官方文档逐层审阅
- `GitHub 源码`：重点读 `src/gateway/` `src/channels/` `src/skills/` `src/apps/`
- `ppaolo.substack.com`：架构深度解析
- **竞品同步体验**：Lindy AI / Dify / Open Interpreter，逐层对比

### 🔻 6 问收敛
> ① 它的产品能力全景是什么？ ② 能力全面性为什么重要？ ③ 7 层各自的成熟度？ ④ 最强的能力层是哪个？ ⑤ 最弱的能力层是哪个？ ⑥ 如果我创业，应该在哪一层做增强/补足/替代？

**⭐ 必读**

| 材料                                                         | 类型     | 价值点                                                       |
| ------------------------------------------------------------ | -------- | ------------------------------------------------------------ |
| [OpenClaw 官方文档](https://docs.openclaw.ai/)               | 官方     | 逐层审阅每一层能力的官方说明、配置项、限制                   |
| [GitHub README](https://github.com/openclaw/openclaw)        | 官方     | 最新功能列表、支持的渠道、安装方式、skills 列表              |
| [36Kr：OpenClaw 从 GitHub 到 AI 体验变革](https://eu.36kr.com/en/p/3706443833487493) | 深度分析 | 四层技术架构拆解（前台/大脑/双手/档案柜），与 Claude Skills 的逐层对比 |
| **本地部署实测**（亲手操作）                                 | 一手体验 | 从安装到日常使用 2 周，逐层记录每一层的实际体验              |

**📖 推荐阅读**

| 材料                                                         | 价值点                                                      |
| ------------------------------------------------------------ | ----------------------------------------------------------- |
| [Flypix：Best AI Models for OpenClaw](https://flypix.ai/best-ai-model-openclaw/) | 模型兼容性层的详细评测（Claude vs GPT vs DeepSeek）         |
| [VidAU：MaxClaw vs OpenClaw](https://www.vidau.ai/maxclaw-vs-openclaw-how-to-pick-the-right-ai-agent-now/) | 能力层对比：MiniMax MaxClaw 的成本优势 vs OpenClaw 的灵活性 |
| [Lobster 工作流引擎 VISION.md](https://github.com/openclaw/lobster/blob/main/VISION.md) | 能力层：Lobster 自动化引擎的设计哲学和路线图                |

---

## 四、技术架构与代码质量

### 为什么要调研这部分
你的所有创业路径——无论是做 Skill 开发、做托管服务、还是做安全产品——都建立在 OpenClaw 的技术底座之上。如果它的架构是耦合的，第三方扩展的天花板就很低，"围绕它做生态生意"这条路就不成立。如果它的安全模型是脆弱的，"企业级部署"这条路就必须你自己补安全层。如果它的代码质量不支持高频迭代，项目的长期稳定性就有疑问。技术调研的目的不是复述代码，而是判断：你到底能不能信任这个底座来承载你的业务。

### 最终要达成的判断
> 回答一个核心问题：我是应该在 OpenClaw 的架构上搭建我的业务，还是需要 fork 改造甚至另起炉灶？同时识别安全层面是否存在可以商业化的缺口。这个判断直接输入到模块十一（供应链依赖评估）和模块十四（技术路线选择）。

### 4.1 系统架构设计

**关键调研问题**：
- 整体是单体还是多模块工作区？（当前仓库已有 apps / extensions / packages / skills / sandbox / ui 等多层结构）
- Gateway（WebSocket 控制面，端口 18789）的职责边界：只做路由，还是承担更多逻辑？
- Assistant runtime 怎么组织？skills / extensions / packages / apps 之间的关系是什么？
- 多渠道消息适配层的抽象质量——新增一个渠道的开发成本有多大？
- 语音链路和 Canvas 链路如何接入？是原生集成还是插件式？
- 本地运行 / Docker / sandbox / browser sandbox 的边界？
- 模型层是 provider 抽象（model-agnostic），还是围绕某些模型深度优化？

**推荐调研方法/工具**：

- `GitHub 源码深读`：目录结构 → 核心模块 → 依赖关系
- `ppaolo.substack.com`：架构解析文章
- `cloc` / `tokei`：代码行数和语言分布
- **本地 debug 模式运行**：跟踪一条消息从渠道接入到模型调用到响应返回的全链路

### 4.2 代码质量与工程成熟度

**关键调研问题**：
- 320,000+ 行 TypeScript 的模块化程度和代码规范一致性？
- 测试覆盖率？CI/CD pipeline 成熟度？
- 依赖安全性（npm audit 结果）？
- PR 审核标准和合并速度？
- 选择 TypeScript 而非 Python/Rust 的技术决策逻辑？对生态扩展性的影响？

**推荐调研方法/工具**：
- `SonarQube` / `CodeClimate`：代码质量扫描
- `npm audit`：依赖安全审计
- `GitHub Actions`：查看 CI/CD 配置
- `GitHub PR 列表`：抽样看 10 个已合并 PR 的审核质量

### 4.3 安全性深度评估

**关键调研问题**：
- 已公开 9 个 CVE 的详情、严重等级和修复状态？
- ClawHub ~20% 恶意 Skills（1,184+）的攻击模式分类？
- 220,000+ 暴露实例的攻击面分析？
- 本地运行与云端依赖各占多少？账号/密钥/模型调用的安全边界？
- 多消息渠道接入后新增的风险面？
- 沙箱隔离的实际效果？
- 中国 CNCERT 安全警告的具体内容和影响？
- "高权限、高私密、高长期记忆"场景下的可信边界怎么建立？
- **关键判断**："安全感"本身是否可以成为付费点？

**推荐调研方法/工具**：
- `NVD`：搜索 OpenClaw CVE
- `thehackernews.com` / `particula.tech` / `theregister.com`：安全分析报告
- `Shodan` / `Censys`：暴露实例扫描
- `CNCERT 官网`：安全警告原文
- **渗透测试**：本地部署后尝试 prompt injection、权限绕过等基本攻击

### 🔻 6 问收敛
> ① 它的技术架构核心是什么？ ② 架构设计为什么重要（决定能否长出生态）？ ③ 当前架构成熟度如何？ ④ 架构中最强的设计是什么？ ⑤ 最大的安全/架构短板是什么？ ⑥ 如果我创业，是在它的架构上搭建，还是需要重写核心层？

**⭐ 必读（架构）**

| 材料                                                         | 类型       | 价值点                                                       |
| ------------------------------------------------------------ | ---------- | ------------------------------------------------------------ |
| [Substack：OpenClaw Architecture, Explained](https://ppaolo.substack.com/p/openclaw-system-architecture-overview) | 深度技术   | 最佳架构解析：Hub-and-Spoke 架构、Gateway 控制面、Agent Runtime、Canvas、Skill 发现机制 |
| [DeepWiki：Architecture Deep Dive](https://deepwiki.com/openclaw/openclaw/15.1-architecture-deep-dive) | 自动化文档 | 从源码自动生成的架构文档，含代码路径引用、数据流图、模块关系 |
| [GitHub Gist：Reference Architecture（Opus 4.6 生成）](https://gist.github.com/royosherove/971c7b4a350a30ac8a8dad41604a95a0) | 技术深潜   | 带 ASCII 架构图的完整技术深潜，含内存系统、向量搜索、Context Window 管理 |
| [Medium：Deep Dive into OpenClaw](https://medium.com/@dingzhanjun/deep-dive-into-openclaw-architecture-code-ecosystem-e6180f34bd07) | 技术分析   | Monorepo 结构（packages/core, gateway, agent, cli, sdk, ui），插件系统详解 |
| [TechAways：OpenClaw Architecture and Insights](https://navant.github.io/posts/openclaw-architecture-and-insights/) | 技术博客   | 5 层安全防御架构、部署模式（Solo vs Team）、Plugin vs Skill 区别 |

**⭐ 必读（安全）**

| 材料                                                         | 类型     | 价值点                                                       |
| ------------------------------------------------------------ | -------- | ------------------------------------------------------------ |
| [Conscia：The OpenClaw Security Crisis](https://conscia.com/blog/the-openclaw-security-crisis/) | 安全深度 | 最全面的安全危机分析：CVE-2026-25253 完整攻击链、ClawHavoc 供应链攻击、30,000+ 暴露实例 |
| [Kaspersky：Key OpenClaw Risks](https://www.kaspersky.com/blog/moltbot-enterprise-risk-management/55317/) | 安全评估 | 企业级风险管理视角，默认配置的系统性弱点清单                 |
| [The Hacker News：ClawJacked Flaw](https://thehackernews.com/2026/02/clawjacked-flaw-lets-malicious-sites.html) | 安全新闻 | 最新 CVE 列表（含 CVSS 评分）、恶意 Skills 的 Atomic Stealer 投放链路 |
| [Particula：250K Stars Then 20% Malicious Skills](https://particula.tech/blog/openclaw-security-crisis-malicious-ai-agents) | 安全分析 | 防御建议：isolation-first 部署、allowlist-only skill 安装、网络分段 |
| [CyberDesserts：OpenClaw Security Risks](https://blog.cyberdesserts.com/openclaw-malicious-skills-security/) | 安全指南 | 1,184 恶意 Skills 分类、135,000 暴露实例数据、9 个 CVE 全列表 |
| [InfoQ：AWS Lightsail OpenClaw + Security](https://www.infoq.com/news/2026/03/aws-lightsail-openclaw-security/) | 技术新闻 | AWS 安全加固方案、Bitdefender 20% 恶意率数据、Token Security 影子 AI 研究 |
| [Infosecurity Magazine：Six New Vulnerabilities](https://www.infosecurity-magazine.com/news/researchers-six-new-openclaw/) | 安全新闻 | Endor Labs 发现的 6 个新 CVE 详情                            |

---

# 第二层：理解它为什么是现在这样

---

## 五、生态系统与可扩展性

### 为什么要调研这部分
一个项目能不能长成平台，关键不在于它自身有多强，而在于第三方能在上面创造多少价值。如果 OpenClaw 的 skills/extensions/packages 体系设计得好、开发门槛低、分发渠道通，你的创业策略就应该是"在生态里做应用层的生意"（类似在 iOS 生态做 App）；如果体系设计得差、第三方贡献困难，你的策略就应该是"做生态本身缺失的基础设施"（类似做 App Store 本身）。这个判断决定了你是做"应用"还是做"平台"。

### 最终要达成的判断
> 回答两个问题：① ClawHub 的双边网络效应飞轮是否真正转起来了？② 第三方开发者的贡献门槛和留存率如何？这两个判断直接输入到模块八（Skills 市场变现潜力评估）和模块十四（"中国版 ClawHub"路径可行性）。

### 5.1 Skills / Extensions / Packages 体系

**关键调研问题**：
- SKILL.md 的 YAML 元数据规范和自然语言指令格式——开发门槛高不高？
- skills / extensions / packages / apps 四者的边界和关系？
- 第三方开发者的贡献门槛和体验？文档是否支持生态共建？
- Agent 自主创建新 Skills 的"自我进化"能力——实际效果如何？

### 5.2 ClawHub 市场生态

**关键调研问题**：
- 13,700+ Skills 的分类分布、质量分层、下载量分布？
- 头部 skills 的类型和使用场景？
- 付费 skills（$10-200）的实际交易量和卖家收入？
- 恶意 Skills 的治理机制和审核流程？
- ClawHub 更像"应用商店"、"脚本仓库"、还是"工作流生态"？
- **双边网络效应判断**：更多 skills → 更多用户 → 更多开发者的飞轮是否转起来了？
- **多归属成本**：开发者在 ClawHub 发布 skill 的排他性有多强？能否同时在其他平台发布？

### 5.3 MCP 生态融合

**关键调研问题**：
- MCPorter（MCP 集成器）的解耦设计和协议兼容性？
- 与 Anthropic MCP 生态的融合深度？
- MCP 是否会成为 Agent 互操作的标准协议？对 OpenClaw 意味着什么？

### 5.4 社区基础设施

**关键调研问题**：
- Discord 146,500+ 成员的活跃度和讨论主题？
- X/Twitter 27,500+ 成员的影响力？
- 中国社区聚集地：哪些微信群/知识星球/B 站频道/公众号最活跃？
- 文档多语言支持情况（尤其中文）？

**推荐调研方法/工具**：
- `ClawHub` 直接浏览分析
- `GitHub: openclaw/clawhub`：注册表源码
- `docs.openclaw.ai`：开发者文档评估
- `npm`：搜索 openclaw 相关包的数量和下载量
- **亲手开发一个 Skill 并发布到 ClawHub**：实测全流程
- `Discord` 加入观察 + `Bilibili` / `知乎` / `小红书` 搜索

### 🔻 6 问收敛
> ① 它的生态体系是什么？ ② 生态为什么是平台型项目的关键？ ③ 当前生态健康度如何？ ④ 生态中最强的部分是什么？ ⑤ 生态中最薄弱/最危险的环节是什么？ ⑥ 如果我创业，是做生态内的应用，还是做生态本身的基础设施？

**⭐ 必读**

| 材料                                                         | 类型       | 价值点                                                     |
| ------------------------------------------------------------ | ---------- | ---------------------------------------------------------- |
| [ClawHub VISION.md](https://github.com/openclaw/clawhub/blob/main/VISION.md) | 官方       | Skills 市场的设计哲学和路线图                              |
| [DeepWiki：OpenClaw 完整文档](https://deepwiki.com/openclaw/openclaw) | 自动化文档 | Skills / Extensions / Packages / Apps 四者关系的源码级说明 |
| [OpenClaw 插件文档](https://docs.openclaw.ai/plugins/community) | 官方       | 社区插件列表、Plugin 开发指南、上架标准                    |
| **亲手开发一个 Skill 并发布**（实操）                        | 一手体验   | 开发门槛、文档完备度、发布流程、审核体验                   |

**📖 推荐阅读**

| 材料                                                         | 价值点                             |
| ------------------------------------------------------------ | ---------------------------------- |
| [WiTechPedia：OpenClaw AI Wiki](https://www.witechpedia.com/wiki/openclaw-ai/) | ClawHub 市场生态概览、MCP 集成说明 |
| [ClickClaw：Architecture Explained](https://clickclaw.me/blog/openclaw-architecture-explained) | Skill 管理界面和配置流程的实操说明 |

---

## 六、增长机制与传播解码

### 为什么要调研这部分
OpenClaw 的爆火速度是开源历史上前所未有的——60 天超越 React 十年的 stars 积累。但对创业者来说，关键不是"它很火"，而是"它怎么被火起来的"以及"这个火还能烧多久"。如果爆火主要靠产品力，你应该在生态里深耕；如果主要靠话题和情绪，你应该在窗口期内快进快出。如果它的传播路径是可复制的，你也许可以用同样的方法推广自己的产品；如果是不可复制的偶然事件（如 Moltbook 催化 + 更名风波 + 两会讨论的多重巧合），你就不应该指望复制这个增长奇迹。

### 最终要达成的判断
> 回答三个问题：① 增长的核心驱动力是产品力、品牌力、还是时机巧合？② "养龙虾"热度的半衰期有多长？③ 增长策略中有没有可复制到我自己产品上的元素？这些判断直接输入到模块九（市场趋势的泡沫度评估）和模块十四（创业 timing 选择）。

### 6.1 品牌符号系统

**关键调研问题**：
- "龙虾"品牌符号的形成过程（Clawdbot → Moltbot → OpenClaw + 🦞）——是刻意设计还是偶然形成？
- 视觉风格与 meme 化表达：龙虾 emoji 在中国市场的传播效力？
- 项目 slogan 和世界观构建：它讲的"故事"是什么？
- GitHub 首页的包装方式——与同类项目相比，信息密度和"第一眼吸引力"如何？

### 6.2 传播链路拆解

**关键调研问题**：
- Moltbook（AI Agent 社交网络）在引爆增长中的角色——是"渠道"还是"催化剂"？
- 传播路径分析：Hacker News → X/Twitter → 中国开发者社区 → B 站/小红书 → 大众媒体？还是另一条路径？
- 它引发的是技术圈传播还是大众圈传播？两者的交叉点在哪里？
- 产品演示是否有"可传播截图感"？用户截图/录屏最多的场景是什么？
- KOL / 开发者社群扩散机制——有哪些关键节点人物？
- 中国市场的独特传播路径：两会讨论 → 腾讯总部排队 → B 站教程 → 闲鱼代部署 → 地方政府补贴

### 6.3 增长本质判断

**关键调研问题**：
- OpenClaw 的爆火，核心驱动力到底是：a) 技术/能力领先 b) 品牌/包装领先 c) 市场情绪/timing d) 社交裂变机制 e) 以上组合？各占多少权重？
- 320K stars 中有多少是"真实技术兴趣"，多少是"社交从众效应"？
- 与 DeepSeek 在中国的传播路径对比——有什么共性和差异？
- "养龙虾"文化现象的可持续性——是短期 meme 还是长期品牌资产？

**推荐调研方法/工具**：
- `star-history.com`：stars 增长曲线中的关键拐点
- `Google Trends` + `百度指数` + `微信指数`：跨平台搜索热度对比
- `Hacker News` 历史帖子：追踪最早的爆发帖
- `X/Twitter` 时间线分析：识别关键传播节点
- `SimilarWeb`：openclaw.ai 流量来源分析

### 🔻 6 问收敛
> ① 它的增长机制是什么？ ② 理解增长机制为什么对创业重要？ ③ 增长的质量如何（泡沫 vs 实质）？ ④ 增长策略中最可复制的是什么？ ⑤ 增长中最不可持续的部分是什么？ ⑥ 如果我创业，应该复制它的传播策略、借势它的流量、还是等热潮退去后切入？

**⭐ 必读**

| 材料                                                         | 类型       | 价值点                                                       |
| ------------------------------------------------------------ | ---------- | ------------------------------------------------------------ |
| [Peter Steinberger 个人博客：OpenClaw, OpenAI and the future](https://steipete.me/posts/2026/openclaw) | 创始人叙事 | 第一手的增长故事：从第 44 个实验到 OpenAI acqui-hire，传播如何发生 |
| [Medium："60 天打破 React 十年纪录"](https://medium.com/@aftab001x/openclaw-just-beat-reacts-10-year-github-record-in-60-days-now-nobody-knows-what-to-do-with-it-937b8f370507) | 传播分析   | 增长曲线关键拐点、"Stars ≠ 用户"的清醒分析                   |
| [Fortune：OpenClaw creator Peter Steinberger](https://fortune.com/2026/02/19/openclaw-who-is-peter-steinberger-openai-sam-altman-anthropic-moltbook/) | 人物报道   | Moltbook 催化角色、Anthropic 商标投诉、OpenAI/Meta/Anthropic 三方抢人 |
| [Wikipedia: Moltbook](https://en.wikipedia.org/wiki/Moltbook) | 百科       | Moltbook（AI Agent 社交网络）的完整背景和引爆机制            |
| [star-history.com/openclaw](https://star-history.com/#openclaw/openclaw&Date) | 数据工具   | Stars 增长曲线可视化，精确到日的拐点识别                     |

**📖 推荐阅读**

| 材料                                                         | 价值点                                   |
| ------------------------------------------------------------ | ---------------------------------------- |
| [Google Trends: "OpenClaw"](https://trends.google.com/trends/explore?q=openclaw) | 全球搜索热度趋势                         |
| [百度指数: "龙虾 AI" / "OpenClaw"](https://index.baidu.com/) | 中国市场热度趋势                         |
| [SimilarWeb: openclaw.ai](https://www.similarweb.com/website/openclaw.ai/) | 流量来源分析（直接/搜索/社交/引荐）      |
| [People's Daily：OpenClaw craze inspires the future](https://en.people.cn/n3/2026/0312/c90000-20435265.html) | 官方媒体态度：从两会讨论到"创新生态"叙事 |

---

## 七、竞争格局与对标分析

### 为什么要调研这部分
"AI Agent"这个标签下至少有四类完全不同的产品，表面看是竞品，实际上可能不在同一个市场里。如果你把 LangChain（框架）和 OpenClaw（个人助手）放在同一张竞品表里比功能数量，你会得出错误的结论。竞品分析的真正目的不是"列出谁和 OpenClaw 像"，而是回答"如果我基于 OpenClaw 创业，谁会跟我抢同一批用户的钱"。同时，中国市场存在一个独特现象：大厂（腾讯/阿里/百度/MiniMax）同时在 OpenClaw 生态里做产品，它们既是 OpenClaw 的增长推手，也是独立开发者的竞争对手。你必须搞清楚大厂的真实意图是"培育生态"还是"收割生态"。

### 最终要达成的判断
> 回答两个问题：① 如果我创业，我的真正竞争对手是谁（可能不是 OpenClaw 本身，而是腾讯 WorkBuddy 或 MiniMax MaxClaw）？② 我应该做替代者（正面竞争）、增强层（补足缺口）、垂类版本（细分市场）、还是分发渠道（流量生意）？这个判断直接输入到模块十三（竞争态势下的能力匹配评估）和模块十四（具体路径选择）。

### 7.1 四类竞品矩阵

| 类型 | 代表项目 | 与 OpenClaw 的关系 |
|------|---------|-------------------|
| 通用开源 Agent 框架 | Auto-GPT (178K★) / CrewAI / LangGraph | 底层框架 vs 用户产品——是否真正同赛道？ |
| 个人 AI Assistant 产品 | Lindy AI / Dust.tt / Microsoft Copilot | 商业闭源 vs 开源自托管——定位差异多大？ |
| 本地/自托管 AI 助手 | Open Interpreter / Jan.ai | 同为 local-first，差异化在哪里？ |
| 多渠道 AI Bot 工具 | Dify (130K★) / n8n / Botpress | 开发平台 vs 个人助手——路线之争？ |
| 中国本土 Agent 产品 | Manus AI / 扣子(Coze) / 各大厂产品 | 直接竞争还是生态互补？ |

### 7.2 12 维横向对比

| 对比维度 | 要回答的问题 |
|---------|------------|
| 定位 | 自我定义和目标场景 |
| 目标用户 | 开发者 vs 消费者 vs 企业 |
| 安装复杂度 | 从下载到可用的时间 |
| 多渠道能力 | 支持的消息平台数量和质量 |
| 语音能力 | 语音交互的成熟度 |
| 记忆能力 | 长期记忆和个性化深度 |
| 工具/Skills 生态 | 扩展丰富度和开发门槛 |
| 模型兼容性 | 支持的 LLM 范围 |
| 安全边界 | 权限控制和隐私保护 |
| 品牌叙事 | 社区认知和情感连接 |
| 社区规模与活跃度 | Stars / 贡献者 / 讨论活跃度 |
| 商业化想象力 | 变现路径和天花板 |

### 7.3 大厂 OpenClaw 产品矩阵（中国特有）

**关键调研问题**：
- 腾讯（QClaw + WorkBuddy + 云部署）：三件套的产品逻辑和协同效应？
- 阿里（JVS Claw + QoderWork）：移动端 vs 桌面端的差异化？
- 百度（DuClaw）：零部署服务的技术实现？
- 字节（ArkClaw / 火山引擎）：目标客群和定价？
- MiniMax（MaxClaw）：1/7~1/20 Claude 成本的可持续性？
- Nvidia（NemoClaw）：企业版安全增强的技术路线？
- 关键判断：这些大厂产品是"OpenClaw 的增强层"还是"OpenClaw 的替代品"？独立开发者还有多少空间？

**推荐调研方法/工具**：
- `vidau.ai`：MaxClaw vs OpenClaw 对比
- `gumloop.com` / `bluehost.com`：Agent 框架横评
- **实际注册使用** 各家产品体验对比
- `caixinglobal.com` / `hellochinatech.com` / `cntechpost.com`：中国大厂产品报道

### 🔻 6 问收敛
> ① 竞争格局全景是什么？ ② 理解竞争格局为什么重要？ ③ OpenClaw 在竞争中的当前位置？ ④ 它最大的竞争优势是什么？ ⑤ 最可能被谁、在哪个维度上超越？ ⑥ 如果我创业，应该做替代者、增强层、垂类版本、还是分发渠道？

**⭐ 必读**

| 材料                                                         | 类型     | 价值点                                                       |
| ------------------------------------------------------------ | -------- | ------------------------------------------------------------ |
| [VidAU：MaxClaw vs OpenClaw](https://www.vidau.ai/maxclaw-vs-openclaw-how-to-pick-the-right-ai-agent-now/) | 对比评测 | MiniMax MaxClaw 与 OpenClaw 的逐维度对比                     |
| [36Kr：OpenClaw 从 GitHub 到体验变革](https://eu.36kr.com/en/p/3706443833487493) | 深度分析 | OpenClaw vs Claude Skills 的四维度对比（定位/场景/隐私/架构） |
| [Gumloop：6 Best AI Agent Frameworks](https://www.gumloop.com/blog/ai-agent-frameworks) | 框架横评 | LangGraph / CrewAI / AutoGen 等框架的横向评测                |
| [TechCrunch："一些 AI 专家认为 OpenClaw 没那么令人兴奋"](https://techcrunch.com/2026/02/16/after-all-the-hype-some-ai-experts-dont-think-openclaw-is-all-that-exciting/) | 反面观点 | 批评性视角，平衡热度泡沫                                     |

**📖 推荐阅读**

| 材料                                                         | 价值点                                    |
| ------------------------------------------------------------ | ----------------------------------------- |
| [HelloChinaTech：为什么腾讯比谁都需要 OpenClaw](https://hellochinatech.com/p/tencent-openclaw-wechat-ai-strategy) | 腾讯 WeChat + OpenClaw 策略分析           |
| [CnTechPost：百度发布 DuClaw](https://cntechpost.com/2026/03/12/baidu-releases-duclaw-its-openclaw-joining-fierce-chinese-ai-race/) | 百度 DuClaw 产品定位和竞争态势            |
| [Caixin Global：腾讯将 OpenClaw 引入微信](https://www.caixinglobal.com/2026-03-10/tencent-moves-to-bring-openclaw-ai-assistant-into-wechat-102421338.html) | 腾讯 QClaw / WorkBuddy / 云部署三件套细节 |
| [TNW：Nvidia NemoClaw 企业版](https://thenextweb.com/news/nvidia-nemoclaw-openclaw-enterprise-security) | Nvidia 企业级 Agent 平台的技术路线        |

---

## 八、商业模式与变现路径

### 为什么要调研这部分
OpenClaw 本身零收入（MIT 开源，基金会运营），但围绕它的生态已经每月产生千万美元级别的现金流。对创业者来说，你不是在和 OpenClaw 竞争——OpenClaw 永远不会收费——你是在和其他试图从 OpenClaw 生态中赚钱的人竞争。这意味着你必须搞清楚"钱在生态中怎么流动"：从用户口袋到 LLM API 提供商、到云厂商、到 Skill 开发者、到硬件卖家、到服务商，每一段的金额、毛利和增长率各是多少。只有画清楚这张"钱流图"，你才能找到毛利最高且规模化潜力最大的切入点。中国市场还叠加了一层政策补贴变量——龙岗最高 1000 万的股权投资可以大幅改变早期创业的财务模型。

### 最终要达成的判断
> 回答三个问题：① 生态中哪个变现环节毛利最高、规模化潜力最大？② 政策补贴能否覆盖我到达盈亏平衡之前的现金缺口？③ 6 条创业路径中，哪条路径的风险收益比最优？这些判断直接输入到模块十三（路径 vs 能力匹配）和模块十四（单元经济学验算）。

### 8.1 项目可持续性

**关键调研问题**：
- MIT 许可证下的商业化边界？
- 501(c)(3) 基金会的运营资金（OpenAI / 腾讯云 / 百度赞助）是否足够？
- 有无引入付费功能的计划？如果引入，社区反应预判？

### 8.2 生态变现地图

**关键调研问题**：
- **LLM API 消费**：月流水 ，轻度5−15M+，轻度10-30 → 重度 $100-700+，分布模型？
- **云托管**：腾讯云 vs 阿里云 vs 火山引擎 vs 华为云的竞争格局？
- **Skills 市场**：付费 skills 个，卖家月收入10−200/个，top卖家月收入100-1,000？
- **硬件**："龙虾盒子"台，头部卖家5,000/台，头部卖家1.8M 收入——可复制吗？
- **服务**：闲鱼代部署 ¥100-1,000/次，API 中转月收 $1M+——合规风险？
- **关键判断**：哪个环节毛利最高？哪个最有规模化潜力？

### 8.3 六条创业路径评估

| 路径 | 核心价值主张 | 关键风险 |
|------|------------|---------|
| 个人用户订阅 | 免安装、免配置的托管 OpenClaw | 与大厂免费产品直接竞争 |
| 极客高级功能包 | 高级 Skills / 模型路由优化 / 多 Agent 协作 | 用户付费意愿不确定 |
| 托管部署 / 一键安装 | 企业级合规 + 安全沙箱 + 国产模型路由 | 大厂可快速复制 |
| 技能/模板市场 | 垂直行业 Skill 包 + 本地化 ClawHub | 需要持续内容供给 |
| 企业版 / 私有化部署 | 合规 + 审计 + SSO + 多租户 | 销售周期长 |
| 咨询/集成/代运营 | 传统企业 AI Agent 落地 | 人力密集 |

### 8.4 中国市场补贴与政策红利

**关键调研问题**：
- 龙岗"龙虾十条"各项补贴的具体条件和申请门槛
- 无锡 ≤500 万、常熟 ≤600 万、合肥 ≤1000 万+1000 万算力券
- 深圳 OPC 行动计划（2026-2027）
- 补贴政策的持续性——长期产业政策还是短期跟风？

**推荐调研方法/工具**：
- `chinanews.com.cn` / `thepaper.cn` / `bjnews.com.cn`：政策原文
- `getlago.substack.com`："能否变现 OpenClaw" 分析
- `panewslab.com` / `odaily.news`：变现路径拆解
- **联系龙岗区科创局**：获取补贴申请细则
- `闲鱼` / `淘宝`：真实交易数据

### 🔻 6 问收敛
> ① 钱在哪里流动？ ② 理解变现路径为什么是创业的第一步？ ③ 当前各变现路径的成熟度？ ④ 最有利润的环节是什么？ ⑤ 最大的商业化风险是什么？ ⑥ 如果我创业，应该切哪条变现路径？启动资金从哪来？

**⭐ 必读**

| 材料                                                         | 类型     | 价值点                                                    |
| ------------------------------------------------------------ | -------- | --------------------------------------------------------- |
| [Substack（Lago）："Can anyone actually monetize OpenClaw?"](https://getlago.substack.com/p/can-anyone-actually-monetize-openclaw) | 变现分析 | 最系统的变现路径分析：API 消费、云托管、Skills 市场、服务 |
| [PANews：每个人都在养龙虾，别人怎么赚钱](https://www.panewslab.com/en/articles/019cd682-ae89-754f-92b1-4304328aa56f) | 变现拆解 | 中国市场变现链路全景：代部署/龙虾盒子/API 中转/课程       |
| [ODaily：OpenClaw 淘金热——卖铲人永远不愁](https://www.odaily.news/en/post/5209695) | 商业分析 | "卖铲人"商业模式分析                                      |
| [Superframeworks：5 Profitable Business Ideas](https://superframeworks.com/articles/openclaw-business-ideas-indie-hackers) | 创业点子 | 5 条具体商业化路径和预估收入                              |

**⭐ 必读（中国政策补贴）**

| 材料                                                         | 类型     | 价值点                                             |
| ------------------------------------------------------------ | -------- | -------------------------------------------------- |
| [NYU Shanghai：龙岗 OpenClaw 补贴政策详解](https://rits.shanghai.nyu.edu/ai/shenzhen-longgang-backs-openclaw-with-millions-in-subsidies-for-one-person-ai-companies) | 政策分析 | 龙虾十条 10 项措施逐条英文解读                     |
| [SCMP：中国地方政府补贴 OpenClaw](https://www.scmp.com/tech/policy/article/3345986/chinese-local-governments-offer-openclaw-project-subsidies-security-questions-linger) | 新闻     | 龙岗/无锡补贴对比，安全风险与政策支持的张力        |
| [Business Insider/DNYUZ：免费住房 + 72 万美元补贴](https://dnyuz.com/2026/03/10/free-housing-offices-and-up-to-720000-subsidies-chinese-cities-go-all-in-on-openclaw-startups/) | 新闻     | 无锡 12 项措施、龙岗免费住房/办公空间/人才补贴细节 |
| [Digitimes：龙岗+无锡补贴政策对比](https://www.digitimes.com/news/a20260310PD211/china-ai-agent-subsidies-policy.html) | 行业媒体 | 两地政策横向比较                                   |
| [建始 APP：龙岗十条原文解读](https://jianshiapp.com/shenzhen-longgang-plans-to-release-the-ten-ai-lobster-measures-for-the-first-time/) | 政策原文 | 中文政策原文 + 逐条解释，含 OPC 行动计划背景       |

---

## 九、市场规模与趋势

### 为什么要调研这部分
市场规模决定创业天花板。如果 AI Agent 个人助手是一个千亿级市场，做一个细分领域的 1% 就足以建立一家好公司；如果实际有效市场只有几十亿，你的定价空间和增长上限都会受到严重约束。更重要的是，市场"处于什么阶段"直接影响你的策略选择——早期市场需要教育用户、拼速度；成熟市场需要差异化、拼效率。中国的 AI Agent 市场还叠加了政策监管变量（合规要求可能把一部分玩家挡在门外，也可能为合规服务商创造需求）。

### 最终要达成的判断
> 回答两个问题：① 我的目标细分市场有多大（TAM/SAM/SOM）？② 当前市场处于早期探索还是快速增长阶段？这些判断直接输入到模块十四（创业规模和融资需求估算）。

### 9.1 全球 AI Agent 市场

**关键调研问题**：
- 2025 ~8B→2034140-250B，CAGR 40-50% 的增长假设是否合理？
- 个人 AI 助手细分：2026 $4.84B，CAGR 42.2% 的驱动因素？
- 开源 vs 商业 AI Agent 的份额演变？

### 9.2 中国市场特殊性

**关键调研问题**：
- 中国 AI Agent 市场的独立规模估算？
- DeepSeek 5-20x 成本优势对中国市场 Agent 普及的推动？
- "养龙虾"热潮后的用户留存率预判？

### 9.3 政策与监管环境

**关键调研问题**：
- 中国"限制政府使用 + 大力补贴民间"的双轨政策逻辑？
- CNCERT 安全指南的具体合规要求？
- 信通院可信 AI Agent 标准（预计 2026.3 下旬）的内容预判？
- 韩国/荷兰等国限制措施对全球化的影响？

**推荐调研方法/工具**：
- `fortunebusinessinsights.com` / `grandviewresearch.com` / `demandsage.com`
- `CAICT（信通院）` / `艾瑞咨询` / `IDC 中国`
- `Google Trends` + `百度指数` + `微信指数`
- `CNCERT 官网`

### 🔻 6 问收敛
> ① 市场有多大？ ② 市场规模为什么决定创业天花板？ ③ 当前市场处于什么阶段？ ④ 最确定的增长驱动力是什么？ ⑤ 最大的市场风险？ ⑥ 如果我创业，应该赌多大的市场？

**⭐ 必读**

| 材料                                                         | 类型     | 价值点                                                       |
| ------------------------------------------------------------ | -------- | ------------------------------------------------------------ |
| [Fortune Business Insights：AI Agents Market 2034](https://www.fortunebusinessinsights.com/ai-agents-market-111574) | 市场报告 | 全球 AI Agent 市场规模预测                                   |
| [Grand View Research：AI Agents Market 2033](https://www.grandviewresearch.com/industry-analysis/ai-agents-market-report) | 市场报告 | 细分市场数据                                                 |
| [DemandSage：AI Agents Market 2026-2034](https://www.demandsage.com/ai-agents-market-size/) | 数据汇编 | 多个数据源的交叉验证                                         |
| [TrendForce：OpenClaw 如何重塑算力和芯片格局](https://www.trendforce.com/news/2026/03/17/news-everyone-raising-a-lobster-how-openclaw-reshapes-the-computing-and-chip-landscape/) | 行业分析 | 从算力/芯片供应链视角看 OpenClaw 的产业影响                  |
| [Invezz：黄仁勋背书后中国 AI 股暴涨](https://invezz.com/news/2026/03/18/why-chinese-stocks-are-surging-over-nvidia-ceos-openclaw-endorsement/) | 资本市场 | 最新（3.18）：黄仁勋 GTC 背书 OpenClaw，MiniMax/智谱股价 20%+ 涨幅 |

**📖 推荐阅读**

| 材料                                                         | 价值点                                     |
| ------------------------------------------------------------ | ------------------------------------------ |
| [AI Magicx：开源 AI 革命（DeepSeek + OpenClaw）](https://www.aimagicx.com/blog/open-source-ai-revolution-deepseek-openclaw-2026) | OpenClaw + DeepSeek 双轮驱动的开源 AI 趋势 |
| [CNBC：OpenClaw 为中国科技股注入新生命](https://www.cnbc.com/2026/03/15/openclaw-breathes-new-life-into-this-chinese-tech-stock-ahead-of-earnings.html) | 资本市场视角的中国 AI Agent 市场           |

---

## 十、核心体验链路与关键时刻

### 为什么要调研这部分
体验决定留存，留存决定商业模式。如果用户安装 OpenClaw 后 30 分钟内没有体验到"Aha Moment"，他大概率会弃用——你的所有下游变现都建立在"用户留下来了"这个前提之上。更关键的是，体验链路中的断裂点往往就是创业机会：如果安装太复杂，"一键部署服务"就有市场；如果第一次对话效果差，"预配置模板"就有市场；如果从尝鲜到深度使用之间缺少引导，"培训和社区服务"就有市场。你的产品应该插入在用户旅程中最痛的那个断裂点上。

### 最终要达成的判断
> 识别体验链路中最大的断裂点在哪里，以及这个断裂点是否构成一个可商业化的切入机会。这个判断直接输入到模块十四（创业切入点选择）。

### 10.1 五阶段用户旅程

| 阶段 | 分析维度 |
|------|---------|
| **① 认知** | 用户预期是什么？GitHub 首页 / 媒体报道 / 社区推荐——哪个渠道转化率最高？ |
| **② 决策** | 安装门槛（30-60 分钟）是否劝退非技术用户？`openclaw onboard` 的体验？ |
| **③ 激活** | 第一次对话的"Aha Moment"是什么？最常见的失败点？ |
| **④ 深入** | 哪些功能驱动深度使用？哪些功能体验断裂？ |
| **⑤ 留存** | 什么让用户留下来？什么让用户弃用？付费转化在哪个阶段？ |

### 10.2 关键体验节点

**关键调研问题**：
- 从安装到"第一次有用的对话"需要多久？
- 哪些设计在制造"惊艳感"？哪些在制造"留存门槛"？
- 中国用户 vs 全球用户的体验差异？

**推荐调研方法/工具**：
- **亲自走完全链路**：记录每一步的时间、情绪、卡点
- `Discord #help 频道`：高频问题 = 高频卡点
- `GitHub Issues`："bug" / "UX" / "onboarding" 标签
- **邀请 3-5 个非技术朋友尝试安装**

### 🔻 6 问收敛
> ① 核心体验链路是什么？ ② 体验为什么决定留存？ ③ 当前体验做得怎么样？ ④ 最惊艳的体验点？ ⑤ 最大的体验断裂？ ⑥ 如果我创业，应该在哪个体验断裂点做差异化？

**⭐ 必读**

| 材料                                                         | 类型     | 价值点                                     |
| ------------------------------------------------------------ | -------- | ------------------------------------------ |
| **亲自完成全链路安装和使用**（实操）                         | 一手体验 | 最核心的材料——没有任何文档可以替代亲手体验 |
| [OpenClaw Getting Started](https://docs.openclaw.ai/)        | 官方文档 | 官方推荐的 onboarding 流程                 |
| [DigitalOcean：How to Run OpenClaw](https://www.digitalocean.com/community/tutorials/how-to-run-openclaw) | 教程     | 云端部署的完整教程，含安全加固             |
| [Cybernews：Build Your Own AI Discord Bot](https://cybernews.com/best-web-hosting/run-ai-discord-agent-with-openclaw/) | 教程     | 从零到接通第一个渠道（Discord）的全流程    |
| Discord #help 频道（需加入）                                 | 社区     | 高频问题 = 最大的体验卡点                  |

---

# 第三层：这对我意味着什么

---

## 十一、风险全景与供应链依赖审计

### 为什么要调研这部分
创业者天然倾向于高估机会、低估风险——这是认知偏差，不是性格缺陷。风险评估模块存在的意义，是强制你在热情最高涨的时候冷静下来，问自己"最坏的情况是什么，我是否承受得起"。更进一步，OpenClaw 不是独立运行的系统——它依赖 LLM API（随时可能涨价）、消息平台 API（随时可能封杀）、一个刚成立 3 个月的基金会（治理结构未经考验）。你的业务建立在这些外部依赖之上，其中任何一环断裂，你的业务可能归零。所以风险评估不是"走过场"，而是帮你识别"哪些风险是致命的、不可对冲的"——如果存在这样的风险，你可能需要重新设计整个商业模式。

### 最终要达成的判断
> 回答两个问题：① 在所有风险中，哪些是致命的（会让业务归零）、哪些是可管理的（可以对冲或缓解）？② 是否存在"风险本身就是机会"的情况（如安全问题催生安全产品市场）？这些判断直接输入到模块十四（路径选择的风险过滤）。

### 11.1 技术风险
- Prompt Injection 的缓解策略？
- Skills 供应链安全的长效治理？
- Gateway 单点故障的高可用方案？

### 11.2 生态风险
- OpenAI 作为 sponsor 是否会逐步收编项目？
- MIT 许可证下的闭源 fork 风险（国内大厂）？
- 社区治理能否支撑百万级用户？

### 11.3 市场风险
- "养龙虾"是短期泡沫还是长期趋势？
- 大厂免费/低价产品对独立开发者的挤压？
- 中美技术脱钩对"美国基金会 + 中国市场"结构的影响？

### 11.4 竞争风险
- Apple/Google 在 OS 级别推出原生 AI Assistant 的降维打击？
- 微信/钉钉/飞书原生 AI 能力增强后的渠道替代风险？

### 11.5 供应链依赖审计

**依赖链矩阵**：

| 依赖环节 | 具体依赖对象 | 替代难度 | 变更概率 | 风险等级 | 创业影响 |
|---------|------------|---------|---------|---------|---------|
| LLM API | Claude / GPT / DeepSeek / Gemini | 中 | 高 | ⚠️ 高 | DeepSeek 涨价 → "便宜"叙事崩塌 |
| 消息平台 API | WhatsApp / Telegram / 微信 | 高 | 中 | 🔴 极高 | 微信封杀第三方接入 → 中国核心场景消失 |
| npm 生态 | Node.js 22+ / TypeScript | 低 | 低 | 🟢 低 | 基本可控 |
| 云基础设施 | 各大云厂商 | 低 | 低 | 🟢 低 | 基本可控 |
| MCP 协议 | Anthropic 主导 | 高 | 中 | ⚠️ 中 | 协议方向变化 → 集成层需重构 |
| ClawHub 审核 | 基金会运营 | 高 | 中 | ⚠️ 中 | 审核收紧 → 第三方上架受阻 |

**推荐调研方法/工具**：
- `WhatsApp Business API 文档`：审查 bot 限制
- `微信开放平台文档`：审查第三方接入合规边界
- `DeepSeek 定价页` + 行业分析
- **绘制完整依赖链图**

### 🔻 6 问收敛
> ① 最大的风险和最脆弱的供应链环节是什么？ ② 为什么必须在创业前评估这些？ ③ 当前风险的紧迫程度？ ④ 哪些风险可以被转化为机会？ ⑤ 哪些风险是致命的、不可对冲的？ ⑥ 如果我创业，风险对冲策略是什么？

**⭐ 必读**

材料同模块四（安全部分），额外补充：

| 材料                                                         | 类型 | 价值点                              |
| ------------------------------------------------------------ | ---- | ----------------------------------- |
| [Tom's Hardware：中国禁止政府电脑使用 OpenClaw](https://www.tomshardware.com/tech-industry/artificial-intelligence/china-bans-openclaw-from-government-computers-and-issues-security-guidelines-amid-adoption-frenzy) | 监管 | 中国政府限制令的完整细节            |
| [Yahoo Finance：中国限制银行和国有机构](https://finance.yahoo.com/news/china-moves-curb-openclaw-ai-063815637.html) | 监管 | 央行和国有企业的限制措施            |
| [The Register：中国 CERT 警告 OpenClaw](https://www.theregister.com/2026/03/12/china_cert_openclaw_security_warning/) | 安全 | CNCERT 安全警告的技术细节           |
| [WhatsApp Business API 文档](https://developers.facebook.com/docs/whatsapp) | 政策 | 审查 WhatsApp 对 bot/中继的使用限制 |
| [微信开放平台文档](https://open.weixin.qq.com/)              | 政策 | 审查第三方接入的合规边界            |

---

## 十二、创始人离场与项目生命力评估

### 为什么要调研这部分
Peter Steinberger 加入 OpenAI 是整个 OpenClaw 故事中最关键的事件——不是因为它是好消息还是坏消息，而是因为它从根本上改变了项目的权力结构。一个只有 3 个月历史的项目，创始人就已经离开了日常开发，加入了项目最大的 sponsor。这意味着你需要回答一个非常尖锐的问题：12 个月后，OpenClaw 是由社区驱动的独立项目（像 Debian），还是由 OpenAI 事实控制的附属品（像 Docker 被收购后的轨迹）？如果答案是后者，你就需要在商业模式中设计一个"OpenClaw 无关化"的退出策略——确保你的业务价值即使脱离 OpenClaw 生态也能存活。

### 最终要达成的判断
> 回答一个核心问题：我的创业计划是否需要内建一个"Plan B"——即如果 OpenClaw 被 OpenAI 事实控制/项目活力衰退/出现社区分裂，我的业务能否独立存活？这个判断直接输入到模块十四（退出策略设计）。

### 12.1 历史案例参照

| 项目 | 创始人 | 离场方式 | 离场后演化 | 对 OpenClaw 的启示 |
|------|-------|---------|-----------|------------------|
| Docker | Solomon Hykes | 2018 辞去 CTO | 从平台缩为开发工具 | 创始人愿景 ≠ 社区方向时的分裂风险 |
| Debian | Ian Murdock | 早期退出管理 | 治理成功过渡，项目持续 30+ 年 | 强治理结构可替代个人影响力 |
| Node.js | Ryan Dahl | 2012 离开后创建 Deno | 社区接管，但创始人的新项目形成竞争 | 创始人可能成为竞争者 |
| Mozilla | Brendan Eich | 2014 辞去 CEO | Firefox 持续衰落 | 品牌惯性可维持一段时间但非永久 |

### 12.2 OpenClaw 特殊性评估

**关键调研问题**：
- 300+ contributors 中有多少是核心架构贡献者？
- 基金会治理章程能否约束 OpenAI 的影响力？
- Steinberger 在 OpenAI 的角色——会不会做一个商业版 personal AI 与开源版竞争？
- 项目的 bus factor？
- 是否有清晰的技术路线图决策机制？

**推荐调研方法/工具**：
- `GitHub contributor graph`：top 20 贡献者分析
- `truck-factor` 工具：关键人物风险系数
- 基金会治理文件
- `steipete.me`：Steinberger 本人表态

### 🔻 6 问收敛
> ① 创始人离场意味着什么？ ② 这个事件为什么对创业决策至关重要？ ③ 项目当前的治理过渡做到什么程度？ ④ 最乐观的演化路径？ ⑤ 最悲观的演化路径？ ⑥ 如果我创业，是否需要设计"OpenClaw 无关化"退出策略？

**⭐ 必读**

| 材料                                                         | 类型       | 价值点                                                       |
| ------------------------------------------------------------ | ---------- | ------------------------------------------------------------ |
| [Peter Steinberger 博客：OpenClaw, OpenAI and the future](https://steipete.me/posts/2026/openclaw) | 创始人声明 | Steinberger 本人对项目未来的表态和承诺                       |
| [TechCrunch：OpenClaw creator joins OpenAI](https://techcrunch.com/2026/02/15/openclaw-creator-peter-steinberger-joins-openai/) | 新闻       | acqui-hire 的正式报道和 OpenAI 声明                          |
| [AllClaw：Peter Steinberger Biography](https://allclaw.org/blog/peter-steinberger) | 传记       | PSPDFKit → €100M 退出 → burnout → OpenClaw → OpenAI 的完整轨迹 |
| [Sam Altman X/Twitter 声明](https://x.com/sama/status/2023150230905159801) | 社交媒体   | Altman 原话："a genius with amazing ideas about smart agents interacting with each other" |
| [AI Tools Review：OpenAI Acqui-Hires OpenClaw Creator](https://aitoolsreview.co.uk/insights/openai-acquihires-openclaw) | 分析       | acqui-hire 对 agentic AI 未来的影响分析                      |
| [GitHub Contributors Graph](https://github.com/openclaw/openclaw/graphs/contributors) | 数据       | top 贡献者画像、贡献类型分布、bus factor 评估                |

---

## 十三、创业者-机会匹配度审计

### 为什么要调研这部分
这是整份框架中唯一"向内看"而非"向外看"的模块。前面 12 个模块分析的全部是 OpenClaw 和市场——"机会好不好"。但创业决策的另一半是"我是不是做这个机会的合适人选"。一个 PM 背景的创业者去做安全合规产品，和一个安全工程师去做同样的产品，成功概率完全不同。如果跳过这个自审直接选路径，最容易犯的错误就是"选了一个看起来最好但自己做不了的路径"——就像选了一个自己搬不动的宝箱。之前研究过的联合创始人股权架构和出力型合伙人定位，在这里是直接的输入变量。

### 最终要达成的判断
> 对每条候选创业路径，产出一个"匹配度评分"：机会吸引力 × 能力匹配度 × 资源可及性 × 风险承受力。最终选择的路径不是"最好的机会"，而是"最好的机会 × 我最能做的交集"。这个判断直接输入到模块十四（最终路径锁定）。

### 13.1 能力栈审计

| 创业路径 | 核心能力要求 | 自评（1-5） | 差距与补足方案 |
|---------|------------|-----------|-------------|
| 行业垂直 Skill 包 | 行业 know-how + Skill 开发 + 行业客户资源 | ？ | ？ |
| Token 成本优化 | 模型路由技术 + 成本建模 + ToB 销售 | ？ | ？ |
| 合规托管 SaaS | 安全工程 + 合规知识 + 云架构 + ToB 销售 | ？ | ？ |
| 安全合规产品 | 安全研究 + 标准解读 + 产品化 | ？ | ？ |
| 中国版 ClawHub | 平台运营 + 内容审核 + 开发者关系 + 融资 | ？ | ？ |
| 企业咨询/集成 | 行业人脉 + 交付团队 + 项目管理 | ？ | ？ |

### 13.2 资源盘点

**关键自审问题**：
- **资金**：启动资金有多少？能 burn 多久？政策补贴能否覆盖启动期？
- **技术**：TypeScript/Node.js 能力？能否独立开发 Skill？
- **人脉**：目标行业有无现成客户关系？龙岗有无政策对接人？
- **合伙人**：是否有互补型合伙人？（联合创始人框架在这里是直接输入）
- **时间**：全职还是兼职？窗口期容忍度？
- **风险承受力**：最坏情况能承受多大损失？

### 13.3 匹配度决策矩阵

```
匹配度 = 机会吸引力 × 能力匹配度 × 资源可及性 × 风险承受力
```

**推荐调研方法/工具**：
- **自我 SWOT 分析**
- **合伙人能力互补评估**
- **政策补贴匹配度审查**
- **与 3-5 位目标用户深度交谈**

### 🔻 6 问收敛
> ① 我的核心能力栈是什么？ ② 能力匹配为什么决定创业成败？ ③ 我目前与最优机会的匹配度如何？ ④ 我最强的可迁移能力？ ⑤ 最大的能力缺口？ ⑥ 综合能力和资源，我最应该选哪条路径？

这个模块的"材料"主要是你自己——但以下资源可以辅助你的自审过程：

| 材料                                                         | 类型     | 价值点                                   |
| ------------------------------------------------------------ | -------- | ---------------------------------------- |
| 你之前关于联合创始人股权和出力型合伙人定位的调研             | 个人积累 | 直接输入到合伙人能力互补评估             |
| 龙岗区科创局联系方式（需搜索"龙岗区人工智能（机器人）办公室"） | 政策对接 | 直接确认补贴申请条件和流程               |
| [深圳 OPC 行动计划原文](https://www.chinanews.com.cn/cj/2026/03-08/10583524.shtml) | 政策     | OPC 创业生态的政策背景，判断补贴可获得性 |

---

## 十四、创业决策层

### 为什么要调研这部分
这是整份框架的终点，所有前面 13 个模块的分析在这里汇聚成一个可执行的决策。如果前面做了大量调研但最后没有落到"我接下来到底做什么"的具体行动上，整个调研就只是知识的积累而非决策的输入。这个模块还承担一个纠偏功能：通过单元经济学速算，把定性判断（"这条路听起来不错"）转化为定量检验（"这条路的 LTV/CAC 比能到 3x 吗"）；通过二阶效应分析，避免你被锚定在 OpenClaw 生态里而错过更大的市场；通过最小验证实验，确保你不是在真空中做决策，而是用最低成本的真实市场反馈来校准判断。

### 最终要达成的判断
> 产出一个可执行的创业行动方案，包含：选定的路径、目标用户、变现模式、启动步骤、资金来源、关键里程碑、风险对冲策略、退出条件。这不是一份计划书——而是一个"下周一就可以开始执行的第一步"。

### 14.1 核心判断清单

- 它最不可复制的东西是什么？
- 它最容易被复制的东西是什么？
- 它真正领先的是产品、技术、品牌，还是社区？
- 它当前最脆弱的点在哪里？
- 它未来 6-12 个月最可能长出的机会点是什么？

### 14.2 创业路径选择

- 如果"借势 OpenClaw"——从哪个切口切进去？
- 如果"避开正面战场"——差异化方向是什么？
- 做替代者 vs 增强层 vs 垂类版本 vs 分发渠道？
- 中国市场 vs 全球市场——第一战场选哪个？

### 14.3 机会优先级矩阵

| 时间窗口 | 机会方向 | 启动条件 | 关键风险 |
|---------|---------|---------|---------|
| **0-6 月** | 行业垂直 Skill 包 | 政策补贴 ≤200 万 | 窗口期短 |
| **0-6 月** | Token 成本优化方案 | 技术门槛低 | 差异化不足 |
| **6-18 月** | 合规托管 SaaS | 信通院标准落地后 | 与大厂竞争 |
| **6-18 月** | 安全合规产品 | 信通院标准落地后 | 市场教育成本 |
| **18 月+** | 中国版 ClawHub | 需规模化运营 | 平台型难度大 |
| **18 月+** | 垂直行业 Agent OS | 需行业 know-how | 周期长投入大 |

### 14.4 单元经济学速算

**每条路径至少回答 8 个数字**：

| 指标 | 定义 |
|------|------|
| CAC | 获取一个付费客户的全部成本 |
| ARPU | 单个客户每月贡献的收入 |
| COGS | 服务单个客户的直接成本 |
| 毛利率 | (ARPU - COGS) ÷ ARPU，目标 > 60% |
| LTV | ARPU × 毛利率 × 平均留存月数 |
| LTV/CAC | 核心健康度指标，目标 > 3x |
| 盈亏平衡客户数 | 固定成本 ÷ (ARPU - COGS) |
| 到达盈亏平衡的时间 | 按月增长率推算 |

**示例：合规托管 SaaS 路径**

```
ARPU = ¥2,000 | COGS = ¥1,000 | 毛利 = ¥1,000
CAC = ¥5,000 | LTV = ¥12,000 | LTV/CAC = 2.4x（略低，需优化）
盈亏平衡 = 80 个企业客户 | 月增 10 个 ≈ 8 个月
压力测试：ARPU 降 30% → LTV/CAC = 1.7x（不成立，需提价或降 CAC）
```

### 14.5 二阶效应与非 OpenClaw 中心机会

**核心逻辑**：跳出 OpenClaw 生态，扫描由同一波趋势驱动但不依赖 OpenClaw 的机会。

| OpenClaw 一阶效应 | 二阶机会 | 是否依赖 OpenClaw |
|-------------------|---------|-----------------|
| 数百万人首次接触 AI Agent | AI 素养培训 / 科普内容 | 不依赖 |
| 大量个人数据流经 Agent | 数据管理/备份/迁移工具 | 不依赖 |
| 安全漏洞频发 | 全赛道 AI Agent 安全基础设施 | 不依赖 |
| 企业探索 Agent 落地 | 行业定制模型微调 | 不依赖 |
| 政府出台 Agent 政策 | 合规咨询 / 政策解读 | 不依赖 |
| 各厂产品百花齐放 | Agent 评测 / 选型工具 | 不依赖 |

### 14.6 最终决策框架

> 1. 我要做 OpenClaw 生态里的生意，还是 OpenClaw 做不了的生意，还是 OpenClaw 催生的二阶市场？
> 2. 我的差异化壁垒是技术、渠道、行业知识、还是合规能力？
> 3. 我的第一批用户从哪里来？获客成本可控吗？
> 4. 单元经济学能跑通吗？政策补贴能否覆盖到盈亏平衡？
> 5. 如果 OpenClaw 热度 6 个月后消退 50%，我的业务还能活吗？
> 6. 我的能力栈和资源与这个机会的匹配度是否 > 70%？
> 7. 我是否设计了"OpenClaw 无关化"的退出策略？

### 🔻 6 问收敛
> ① 最终选择的路径是什么？ ② 为什么这个路径优于其他路径？ ③ 启动需要的最小资源是什么？ ④ 第一个里程碑是什么？ ⑤ 最大的不确定性是什么？ ⑥ 下周一开始执行的第一步是什么？

这个模块是前 13 个模块的汇聚，核心材料来自前面模块的调研结论。额外参考：

| 材料                                                         | 类型     | 价值点                       |
| ------------------------------------------------------------ | -------- | ---------------------------- |
| [Superframeworks：5 Profitable Business Ideas](https://superframeworks.com/articles/openclaw-business-ideas-indie-hackers) | 创业参考 | 每条路径的预估收入和启动成本 |
| [Substack（Lago）：能否变现 OpenClaw](https://getlago.substack.com/p/can-anyone-actually-monetize-openclaw) | 商业分析 | 单元经济学速算的参考基准     |
| [PANews：养龙虾变现拆解](https://www.panewslab.com/en/articles/019cd682-ae89-754f-92b1-4304328aa56f) | 变现案例 | 真实案例的收入数据           |

---

## ⚡ 附录 A：最小验证实验设计

### 为什么需要这个附录
调研框架是望远镜，验证实验是探针。14 个模块的调研可能需要 2-4 周，但市场不会等你——尤其是在龙岗补贴窗口期和"养龙虾"热度都有时效性的情况下。最小验证实验的目的是：在调研进行的同时，用最低成本（总计 < ¥500）和最短时间（< 2 周）获得真实市场信号，避免你花 4 周做了一份完美的调研报告，但错过了最佳行动窗口。

### 实验矩阵

| 编号 | 验证假设 | 方法 | 成本 | 周期 | 成功标准 | 触发模块 |
|-----|---------|------|------|------|---------|---------|
| E1 | 垂直 Skill 有真实需求 | 开发 1 个行业 Skill 发布 ClawHub | ¥0 | 1 周 | 7 天 > 50 下载 + > 3 条反馈 | 模块五 |
| E2 | 非技术用户愿意付费部署 | 闲鱼发布 ¥299 部署服务 | ¥0 | 3 天 | > 10 咨询 + > 2 成交 | 模块八 |
| E3 | 企业客户有托管需求 | 5 家企业 30 分钟访谈 | ¥0 | 1 周 | ≥ 3 家表达试用意愿+预算 | 模块二 |
| E4 | 政策补贴可获得 | 联系龙岗科创局确认条件 | ¥0 | 3 天 | 获得申请指引和时间表 | 模块八 |
| E5 | Token 路由优化有价值 | DeepSeek+Claude 混合路由测试 | ~¥200 | 3 天 | 成本省 > 50% 且质量损失 < 10% | 模块三 |
| E6 | 安全是真实付费点 | 3 个暴露实例安全扫描+报告 | ¥0 | 3 天 | ≥ 1 人回复咨询安全服务 | 模块四 |

### 执行原则
1. **并行执行**：E1-E4 在调研第一周同步启动
2. **快速决策**：达标 → 加注该路径；未达标 → 降低优先级
3. **成本控制**：总成本 < ¥500，总时间 < 2 周
4. **迭代校准**：结果反馈到模块 13 和 14，更新路径优先级

---

## 附录 B：方法论索引

| 模块 | 核心方法论 | 来源 | 核心价值 |
|------|----------|------|---------|
| 整体结构 | SCR 叙事结构 | 麦肯锡 | 三层递进，避免"项目赏析" |
| 模块 1-2 | JTBD（Jobs to be Done） | Clayton Christensen | 从用户任务出发理解需求 |
| 模块 3 | 分层架构 + 聚合理论 | OSI / Ben Thompson | 识别价值聚合层 |
| 模块 4 | Conway's Law 逆向应用 | Melvin Conway | 从代码推断生态接口 |
| 模块 5 | 平台经济学（双边网络效应） | Parker, Van Alstyne | 判断飞轮是否转动 |
| 模块 6 | STEPPS + 冷启动理论 | Berger / Andrew Chen | 拆解增长驱动力 |
| 模块 7 | 战略群组分析 | Michael Porter | 识别真正竞争对手 |
| 模块 8 | 制度套利理论 | 经济学 | 利用政策优化启动成本 |
| 模块 11 | 供应链依赖审计 | 供应链管理 | 识别致命单点依赖 |
| 模块 12 | 开源创始人离场案例分析 | 历史案例法 | 评估项目生命力 |
| 模块 13 | 创业者-机会匹配度 | 综合 | 避免选了搬不动的宝箱 |
| 模块 14 | 单元经济学 + 精益验证 | SaaS / Lean Startup | 从故事升级为数字 |
| 6 问模板 | 决策强制函数 | 军事 / Amazon / Bridgewater | 每模块强制收敛 |

---

## 附录 C：调研资源索引

| 分类 | 资源 | 用途 |
|------|------|------|
| 官方 | github.com/openclaw/openclaw | 源码 / Issues / PRs |
| 官方 | docs.openclaw.ai | 技术文档 |
| 官方 | openclaw.ai/blog | 官方博客 |
| 官方 | open-claw.org | 基金会官网 |
| 社区 | Discord "Friends of the Crustacean" | 社区讨论 |
| 中国 | 36kr / zhidx / jiemian / thepaper | 行业报道 |
| 中国 | chinanews.com.cn / bjnews.com.cn | 政策原文 |
| 国际 | Fortune / TechCrunch / CNBC | 科技媒体 |
| 安全 | CNCERT / Hacker News / The Register | 安全跟踪 |
| 市场 | Fortune BI / Grand View Research | 规模数据 |
| 变现 | panewslab / odaily / superframeworks | 商业分析 |
| 架构 | ppaolo.substack.com / witechpedia.com | 技术解析 |

---

## 附录 D：实操验证清单

- [ ] 本地完整部署 OpenClaw，接入 DeepSeek + Claude，使用 2 周
- [ ] 亲手开发一个行业 Skill 并发布到 ClawHub（= E1）
- [ ] 注册并深度使用腾讯 WorkBuddy / MiniMax MaxClaw / 百度 DuClaw
- [ ] 联系龙岗区科创局了解补贴申请流程（= E4）
- [ ] 加入 3-5 个 OpenClaw 中文社区群，潜水观察 1 周
- [ ] 在闲鱼/淘宝调研"龙虾"相关真实交易量
- [ ] 在闲鱼发布部署服务测试付费意愿（= E2）
- [ ] 邀请 3-5 个非技术朋友安装 OpenClaw
- [ ] 对暴露实例做基础安全测试（= E6）
- [ ] 找 5 家目标行业企业做需求访谈（= E3）
- [ ] DeepSeek + Claude 混合路由成本优化测试（= E5）
- [ ] 参加一次线下 OpenClaw meetup 或线上 AMA
- [ ] 用各主要竞品完成同一任务，横向对比

