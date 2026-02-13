# Reference: Project Category Controlled Vocabulary

**原则：** 一个项目只能属于一个 Category。如果模棱两可，问自己：“这件事最核心的风险和产出是什么？”

## The 7 Pillars (七大支柱)

| Category | 中文名称 | 核心定义 (Mental Model) | 典型产出 (Deliverables) |
| :--- | :--- | :--- | :--- |
| **`Legal`** | 法务 | **高风险、对抗性、契约精神。**<br>涉及第三方权益、政府、法院或律师。 | 判决书、合同、签证文件、律师函 |
| **`Asset`** | 资产 | **价值管理、交易、生命周期。**<br>关注物品的买入、维护、增值或变现。 | 交易收据、所有权证书、维修记录 |
| **`Admin`** | 行政 | **合规、流程、官僚系统博弈。**<br>低风险但繁琐的填表、申报、客服沟通。 | 确认信、退款、完税证明、账户变更 |
| **`Research`** | 研究 | **探索未知、理论构建、知识产出。**<br>没有标准答案，旨在发现新知。 | 论文(PDF)、实验数据、文献综述 |
| **`Dev`** | 工程 | **系统构建、工具制造、落地实现。**<br>将想法转化为可运行的代码或产品。 | 源代码(Repo)、App、自动化脚本 |
| **`Academic`** | 学术 | **结构化学习、被动输入、考核认证。**<br>有明确的大纲、作业和分数的外部课程。 | 成绩单、结课证书、作业提交记录 |
| **`Event`** | 活动 | **时效性、物流规划、社交体验。**<br>有明确开始和结束时间的物理移动或聚会。 | 行程单、预订确认、照片集 |

-----

## 详细定义与实例 (Detailed Definitions & Examples)

### 1\. `Legal` (法务)

**Trigger:** "这件事如果不小心，会有法律后果或身份危机。"

  * **思维模式:** 严谨、证据导向、防守型。
  * **包含:** 诉讼、移民申请、合同纠纷、房产过户(Escrow阶段)。
  * **Examples:**
      * `2025_Legal_Litigation_Landlord_Deposit` (诉讼)
      * `2025_Legal_Immigration_Doe_Jane_H1B` (身份)
      * `2025_Legal_Contract_Consulting_Agreement` (商业合同)

### 2\. `Asset` (资产)

**Trigger:** "这件事关于钱和物，我要确保买对了/卖贵了/修好了。"

  * **思维模式:** 财务计算、性价比、实物管理。
  * **包含:** 电子产品买卖、车辆买卖/维修、房屋挂牌/看房、高价值设备采购。
  * **Examples:**
      * `2025_Asset_Sale_iPhone17` (出售)
      * `2025_Asset_Car_Tesla_Maintenance` (大修/改装)
      * `2025_Asset_Home_Search_Eastside` (看房阶段，关注的是资产价值)

### 3\. `Admin` (行政)

**Trigger:** "这件事就是走个流程，填表，跟进，解决掉。"

  * **思维模式:** 耐心、流程图、记录留痕。
  * **包含:** 保险理赔(非诉讼类)、税务申报、银行开户/关户、运营商转网、证件更新。
  * **Examples:**
      * `2025_Admin_Claim_Chase_PurchaseProtection` (信用卡保险理赔)
      * `2025_Admin_Tax_Return_2024` (年度报税)
      * `2025_Admin_Telco_Transfer_Spectrum` (转网)

### 4\. `Research` (研究)

**Trigger:** "我在尝试理解一个问题，或者写一篇 Paper。"

  * **思维模式:** 批判性思维、假设验证、写作。
  * **包含:** 论文写作、领域调研(Survey)、算法实验(为了写Paper)。
  * **Examples:**
      * `2025_Research_LLM_Benchmark` (主要目标是发 Paper)
      * `2025_Research_Survey_TimeSeries_Reasoning` (文献综述)

### 5\. `Dev` (工程)

**Trigger:** "我在造轮子，或者写一个能跑的系统。"

  * **思维模式:** 架构设计、Debug、版本控制。
  * **包含:** 个人项目开发、系统脚本编写、网站搭建、模型部署(Engineering focused)。
  * **Examples:**
      * `2025_Dev_System_Automation_Scripts` (你的 mkproj 脚本)
      * `2025_Dev_FineTune_Llama_Pipeline` (侧重于搭建训练流水线，而非算法理论)

### 6\. `Academic` (学术)

**Trigger:** "我是学生，我有作业和考试。"

  * **思维模式:** 应试、知识吸收、按时提交。
  * **包含:** 大学课程、Coursera 证书课、执照考试。
  * **Examples:**
      * `2025_Academic_StateU_CS301` (学校课程)
      * `2025_Academic_Course_Coursera_MLOps` (自学考证)

### 7\. `Event` (活动)

**Trigger:** "我要去一个地方，或者组织一场聚会。"

  * **思维模式:** 时间表管理、预订管理、人员协调。
  * **包含:** 旅行、会议参展、婚礼、家庭聚会、搬家(物流部分)。
  * **Examples:**
      * `2026_Event_Travel_CES_LasVegas` (参展)
      * `2025_Event_Family_Reunion_Thanksgiving` (接待安排)

-----

## 边界案例判决法 (Edge Case Decision Logic)

在实际操作中，你会遇到交叉的情况。请使用 **“主要矛盾法”** 来判决。

**Q1: 买房子 (House Purchase) 是 Asset 还是 Legal？**

  * **阶段 A (看房/比价):** 此时主要矛盾是“价值判断”。 -\> **`Asset`**
  * **阶段 B (下Offer/进Escrow):** 此时主要矛盾是“合同与产权风险”。 -\> **`Legal`**
  * *建议：* 如果是个大项目，直接用 `Legal`，因为法律文件的重要性远超看房照片。

**Q2: 搬家 (Moving) 是 Event 还是 Admin？**

  * **物理搬运:** 找搬家公司、打包。 -\> **`Event`** (侧重物流)
  * **改地址:** 去银行、DMV 改地址。 -\> **`Admin`** (侧重手续)
  * *建议：* 建立 `2025_Event_Moving_House` 处理物理搬运；改地址作为 `20_Areas/Admin` 的 Checklist 处理。

**Q3: 那个 Chase 信用卡理赔，为什么不是 Legal？**

  * 如果是你自己填表申请 -\> **`Admin`** (行政流程)。
  * 如果 Chase 拒赔，你决定起诉 Chase -\> **`Legal`** (对抗性升级)。

**Q4: 写代码是为了发 Paper，是 Dev 还是 Research？**

  * 如果代码是手段，Paper 是目的 -\> **`Research`**。
  * 如果代码本身是产品（比如发布一个 Python Package 给别人用） -\> **`Dev`**。