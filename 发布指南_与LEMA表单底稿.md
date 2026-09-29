# 个人主页：发布指南 + LEMA 表单填写底稿（2026-09-28）

> 触发：老大打开刘岳江的申请表，表单里有 **Q12「CV 链接」必答** 与 **Q13「个人主页」非必答**。
> 本文回答：**要不要做主页、怎么做、以及表单 16 题逐题怎么填**。
> 产物：`个人主页/index.html`（单文件，无外部依赖）+ `assets/`（**3 张论文图 + CV PDF**，共 ~1.09 MB）
> 🔄 **2026-09-29 更新**：**去头像，改用论文图**（见 §3.0）

---

## 一、先回答"要不要做" —— **Q13 不是必答，但我建议做**

表单原文逐字：

| # | 字段 | 必答？ | 原文 |
|---|---|---|---|
| 12 | Link to CV or resume | 🔴 **必答** | *(please **upload it to a cloud service** and paste a shareable link here)* |
| 13 | Link to personal website | ⚪ **`if applicable`（非必答）** | *Link to personal website, if applicable* |
| 14 | Link to Google Scholar | ⚪ `if applicable` | *Link to Google Scholar, if applicable* |
| 15 | Link to representative work | ⚪ `if applicable` | *Link to representative work, if applicable* |

**所以：不做也能交（Q13 跳过即可）。但建议做，三个理由：**

1. 🔴 **Q12「CV 链接」是必答，且明确要求"传到云服务再贴分享链接"** ——
   这一题**无论如何都要有一个可公开访问的链接**。既然必须解决"哪里放文件"这件事，
   **顺手用 GitHub Pages 一次解决 Q12 + Q13 + Q15 三题**，增量成本几乎是零。
2. **他的 lab 文化里主页是社交货币** —— 团队页上每个人（含合作者）都挂着**本人主页链接**
   （`xilunzhangrobo.github.io`、`yinpeidai.github.io`）。**在这个组里，没有主页反而显眼。**
3. **Q15「代表工作链接」** 可以直接指主页的 Publications 区，或分工给 arXiv。

> ⚠️ **别做的事**：**不要为了这一题临时去注册域名、买空间、学框架。** 这是加分项不是门槛项。
> 用最省的方式（GitHub Pages）在 **1 小时内**搞定即可。

---

## 二、怎么做：GitHub Pages（最省，且与你已有的 GitHub 账号同源）

**为什么是这个方案**：你已经有 `github.com/Aim404`（c3-jepa 仓库已 public），
所以不需要任何新账号、新域名、新托管。

### 两条路线，按"想不想动主账号"选

| | **路线 A：用户主页**（推荐） | **路线 B：项目仓库页** |
|---|---|---|
| 仓库名 | `Aim404.github.io`（**必须叫这个**） | 任意名，如 `homepage` |
| 最终网址 | **`https://aim404.github.io`** ✅ 短、好记 | `https://aim404.github.io/homepage/` |
| 适合 | 想要一个正式主页地址 | 不想让主页占 `Aim404.github.io` 这个名字 |
| 代价 | 这个名字**一旦建就被占用**（以后不能拿来做别的站） | 网址长一点 |

### 执行步骤（路线 A）

```bash
# 1) 在 GitHub 上新建一个 public 仓库，名字必须是 Aim404.github.io（不要勾 README）
# 2) 把本目录推上去
cd "E:/01_My_database/1_Postgraduate/5_phd/个人主页"
git init
git add index.html assets
git commit -m "Personal homepage"
git branch -M main
git remote add origin https://github.com/Aim404/Aim404.github.io.git
git push -u origin main

# 3) 等 1–2 分钟，访问 https://aim404.github.io
#    （Settings → Pages 里应自动显示 "Your site is live"）
```

> 📌 **不需要** Jekyll、不需要 Actions、不需要改代码 —— 根目录有 `index.html` 就会自动发布。
> ⚠️ **仓库必须 public**（private 仓库的 Pages 要付费）。

### 发布后自检（4 条，逐条过）

- [ ] `https://aim404.github.io` 能打开，且**三张论文图都显示出来**（说明 `assets/` 路径对、`.jpg`/`.png` 后缀没搞混）
- [ ] 点 **CV** 按钮能下载到 PDF（说明 `assets/yuncong-yang-cv.pdf` 上传成功）
- [ ] 点 **arXiv / GitHub** 按钮跳转正确
- [ ] 🔴 **用无痕窗口打开一次**（验证无需登录即可访问 —— 收件人不会登录你的 GitHub）

---

## 三、主页内容怎么写的（口径 = CV，一字不加码）

**设计原则：这是"CV 的可浏览版"，不是新的宣传材料。**

### 3.0 配图（2026-09-29 更新：**去头像，改用论文图**）

老大要求：**不要头像，改成论文图像/素材图**。

**素材来源的取舍**（关键判断）：

| 候选源 | 结论 |
|---|---|
| 🔴 `29、视频剪辑/视频编导/视频素材/简要版素材/` | **不用** —— 里面是 `r1g_rollout_40_cos_h16_s42`、`r1i_rollout_40_…` 这类**内部 run ID** 目录名。**对外材料不得暴露 run ID**（既定红线） |
| 🟡 视频抽帧（仿真/水池/真实水池 各类 mp4） | **本次未用** —— 抽帧要逐张核"画面内嵌文字"（顶部标题带常含 `segment 8/15`、`FREE ROLLOUT` 之类内部标识），成本高且易漏 |
| ✅ **`21、论文规划_世界模型/论文图像/`** | **采用** —— 论文官方插图，**本来就是为对外展示设计的**，无内部标识、图注即论文原意 |

**选用的 3 张**（全部来自论文，比例严格保持，零裁切）：

| 位置 | 图 | 源文件 | 用途 |
|---|---|---|---|
| **首图（header 正下方）** | 深海打捞作业场景（detecting → reaching → grasping → salvaging 四阶段环 + 光学衰减/动态交互两条难点） | `论文图像/fig1/fig1.png` | 一眼说明"这是干什么的领域"，**替代头像占据的视觉焦点** |
| **About 之后** | C³-JEPA 方法架构（Stage I 多视角感知 → Stage II 控制条件预测 → 预测接口 + critic 打分） | `论文图像/fig3/fig3_final.png` | **与主页的技术描述直接对应**，读者能看图核对 |
| **Research experience 之后** | DLROV UVMS 系统结构（水面支持 / 水下本体含推进-感知-导航阵列 / 机械爪阵列） | `论文图像/fig2/fig2.png` | 落在**机构学条目之后**，把"真机 + 机构那一半"可视化 |

> 🖼️ 每张图都配 `figcaption` —— **图注写"这张图说明什么"，不写"这张图多好"**（与 CV 的定性优先口径一致）。
> ⚠️ **不要放模型输出截图/仿真结果帧** —— 那类图常有画面内嵌标识，且容易被读成"效果展示"。

**技术处理（可复用）**：
- **等比缩放**，长边压到 1400–1640 px（正文宽 820 px，2× 屏够用）
- **照片型图转 JPEG（q=90, subsampling=0）**，文字型架构图留 PNG ——
  实测 `fig-overview` 1309 KB → **245 KB**、`fig-hardware` 1298 KB → **262 KB**，**总共从 4.3 MB 压到 1.09 MB**
- 🔴 **压缩后必须复核比例偏差**：三张实测 **0.04% / 0.00% / 0.05%**，全部 ≪ 3% 阈值
- 无 `srcset`/懒加载的简单写法即可 —— 1 MB 总量对静态页完全够

### 3.1 版面与内容决策

| 决策 | 理由 |
|---|---|
| **内容全部来自 CV**，无新增事实 | 避免主页与 CV 出现两个版本，也避免夸大风险 |
| 🔴 **不写内部代号** | CV 里那条 `PHONIC: ...` 在主页上改为 **"Grey-box inverse dynamics for the salvage ROV"** —— 描述性表述，与对外文书约定一致 |
| **专利只列 5 项** | 与 CV 正文一致（CV 列 6 项含一项本科第 5 发明人；主页取前 5 项中的要项，**不补等级、不补评价**） |
| **给 3 篇论文上状态标签** | `Under review`（T-ASE）/ `Accepted`（《机器人》）/ `In preparation` —— **状态可核验，不做形容词修饰** |
| **不写 GPA、不写获奖** | CV 里已有；主页放"研究相关"的部分即可。⚠️ **GPA 3.22 是弱项，主动放到主页没必要** |
| **不加"目标院校清单""套磁状态"** | 那是给自己看的，不是给导师看的 |
| 🔴 **不放头像** | 老大明确要求（2026-09-29） |

**版面**：单栏、正文 820px、主色沿用 CV 的 `#A8322D`、移动端有响应式（窄屏图注与间距收紧）。
**文件**：`个人主页/index.html`（13 KB，单文件内联 CSS，无 JS、无外部字体）——
**它能直接双击打开预览，也能原样推上 Pages。**

---

## 四、LEMA 表单逐题填写底稿（16 题）

> 打开 `https://forms.cloud.microsoft/r/xrW0nmy1Gi`（原 `forms.office.com/r/xrW0nmy1Gi`）
> **填写前先读**：`https://lema-nus.github.io/contact.html#openings`（表单页自己要求的）

| # | 字段 | 必答 | 建议填法 |
|---|---|---|---|
| 1 | Full name | ✅ | `Yuncong Yang` |
| 2 | Email address | ✅ | `aim404@sjtu.edu.cn` |
| 3 | Current affiliation | ✅ | `Shanghai Jiao Tong University, School of Ocean and Civil Engineering, Underwater Engineering Institute` |
| 4 | Current academic level | ✅ | 选 **`Master`** |
| 5 | Major / field of study | ✅ | `Civil and Hydraulic Engineering`（与成绩单一致，**不要写"水下工程"等自造名**） |
| 6 | Expected role with us | ✅ | 选 **`PhD`** |
| 7 | Hours per week | ✅ | 选 **`>= 40 hr / week`**（全日制博士的合理值） |
| 8 | When available to start | ✅ | 选 **2027** 对应项（他明说 *"starting in 2027"*；**如选项含具体月份，填 2027 年秋**） |
| 9 | Research areas interested in | ✅ 多选 | 勾 **`World Model`** + **`Robot Learning`** + **`Self-Improvement`**。<br>⚠️ **三个都勾但要能圆** —— 你确有：世界模型（C³-JEPA）/ 机器人学习（RL、行为克隆）/ 自我改进（critic 筛轨迹 + 想象 rollout 训练行为体）。<br>❌ `Data Curation` 慎勾（你数据是自采的，不是 curation 研究） |
| 10 | Most relevant research / project experience | ✅ | **见下方 §4.1** |
| 11 | Specific topics you'd like to work on | ⚪ | **见下方 §4.2**（**这题是想拿分的地方，值得写**） |
| 12 | Link to CV | ✅ | `https://aim404.github.io`（主页上的 CV 按钮）或直接 `.../assets/yuncong-yang-cv.pdf`<br>⚠️ **必须是可公开访问的链接** —— 这正是要主页的原因 |
| 13 | Link to personal website | ⚪ | `https://aim404.github.io` |
| 14 | Link to Google Scholar | ⚪ | **你现在没有** → **留空**。❌ **不要现造一个**（空 profile 比没有更糟） |
| 15 | Link to representative work | ⚪ | `https://arxiv.org/abs/2609.30214`（C³-JEPA 预印本）+ 主页 Publications 区 |
| 16 | Anything else we'd like to know | ⚪ | 一句话（见 §4.3） |

### 4.1 Q10 底稿（research / project experience，约 140 词）

> My master's project is **C³-JEPA**, an object-centric multi-view world model for a deep-water salvage ROV.
> It encodes several camera views into object-centric tokens, fuses them through held-out-view attention,
> and predicts how object state evolves through contact and under the vehicle's hydrodynamic lag,
> conditioned on control signals — with no contact sensors and no pixels, since the prediction lives in latent space.
> The representation transfers substantially more task-relevant information to downstream probes than a
> reconstruction-free latent baseline, and on real underwater video it recovers a withheld camera's object state.
> On top of it I built a flow-matching diffusion planner with delay-compensated label shifting and a
> block-causal transformer rollout that screens candidate trajectories with a critic.
> It is my first-author submission under review at IEEE T-ASE.
> Separately, I derived the closed-form kinetostatics and multibody dynamics of a double four-bar
> underactuated gripper and validated them against ADAMS and a physical prototype —
> a first-author paper accepted in *Robot* (EI-indexed).

### 4.2 Q11 底稿（topics you'd like to work on，约 90 词 —— **这题是拿分点**）

> Two things I would want to work on. First, the asymmetry between generating and verifying:
> I used a critic to screen imagined rollouts, and the bottleneck was never the generator but the
> absence of anything that could tell a plausible plan from a reachable one.
> Making the verifier a first-class object that feeds back into the model is what I would want to study.
> Second, I worked under a severe data constraint — one vehicle, one pool, limited footage —
> and I would like to know which parts of a world model survive that regime and which only
> look good because data was plentiful.

### 4.3 Q16 底稿（anything else，1–3 句）

> I build my own pipelines end to end — data collection, multi-GPU training, closed-loop evaluation —
> in simulation and, in part, on real pool data. I would also be glad to be considered for a
> research internship or visiting position before the 2027 intake, if either would be useful to the lab.
> *(Useful to know: I also bring the mechanical side — kinetostatics and multibody dynamics — which most
> embodied-AI applicants do not have.)*

> ⚠️ **Q16 第一句可删**（若不想主动提实习）；**第二句建议留** —— 它是与邵林那封一致的差异化点。
> ⚠️ **"in part" 不可删** —— 真机只是部分验证（数据集不够），这是既定的**事实边界硬约束**。

---

## 五、顺序建议（今天到 Dec 15）

| 步 | 动作 | 耗时 |
|---|---|---|
| 1 | 建 `Aim404.github.io` 仓 → 推 `个人主页/` → 等 1 分钟 → 自检 4 条 | ~30 分钟 |
| 2 | 填 LEMA 表单（用 §四底稿）→ **记下提交日期**（跟进信要写 `submitted on [日期]`） | ~40 分钟 |
| 3 | **一周内无回复** → 发 `下一批发信计划_20260928.md` §2.4 那封跟进信（主题行必须逐字照格式） | — |
| 4 | 同时走 NUS CS 官方博士申请（**Dec 15 = Fall intake 截止**，`comp.nus.edu.sg/programmes/pg/phdcs/application`） | 另计 |

---

## 六、待你确认

| # | 事项 | 说明 |
|---|---|---|
| 1 | **路线 A 还是 B**（`aim404.github.io` vs `.../homepage/`） | 建议 A；但这个名字会被占用，你若以后想另作他用就选 B |
| 2 | 🔴 **CV 里 `PHONIC` 是否要一并改掉** | 见下方说明 —— **这是个需要你拍板的问题** |
| 3 | **Q9 是否勾 `Data Curation`** | 建议不勾（见上表） |
| 4 | **Q16 是否主动提实习意愿** | 我建议留，但你可删 |
| 5 | **是否要我把主页也做成中英双语**（`/zh/` 子页） | 目前只有英文 —— 港新申请英文够了 |

### 关于第 2 条（PHONIC）

- **对外文书约定**是「🚫 不写内部代号 `PHONIC`」，但 **CV 正文里现在有一条独立的 `PHONIC: ...` 标题**
  （源：`夸大风险审计.md` 2026-09-16 的修订，当时的判断是"单独列出来作为正在研究点可以"）。
- **我这次在主页上已按约定改成描述性表述**（`Grey-box inverse dynamics for the salvage ROV`），
  但 **CV 里那条还在**，且**邵林那封已经连着 CV 发出去了**。
- 🟡 **两个选择**：
  - **(a) 保持现状** —— 它只是一条工作条目名，不是 run ID；且已在 v4/v5 套磁信文档里被记为"待定"。**风险低。**
  - **(b) 改为描述性名称** —— 与主页一致、与对外约定一致；代价是**要重跑 CV 重建并确认仍为 2 页**。
- **我的建议：(b)**，且**顺手把主页与 CV 统一**。但**这件事由你定** —— 因为你可能记得当初是故意保留的。