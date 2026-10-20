# 来源、归纳方式与限制

## 已完成的研究范围

按2026-10-18冻结目录，UID1786444896的14个投稿、1022个来源分P均有可用派生正文通读、抽取关键帧查看和带来源笔记的完成记录。它们含大量重复课程，不能说成1022个独立观点或1022次独立实验证明。

初始20P为4P全时间线OCR、16P全音轨ASR；后续1002P完成记录经过音轨/笔记哈希、完整ASR元数据、段数、帧数和分工去重检查。另对6P做了独立内容抽样，不能扩大为全量语义复核。前三项补读保留实际阅读者与归属，不重复计分。

完整覆盖索引见 [course-reading-index-20261020.json](research/course-reading-index-20261020.json)。索引内摘要哈希用于追溯研究记录，不需要原机器绝对路径来运行本Skill；原媒体、识别结果、帧和全量笔记保存在原研究档案，未打入运行材料。索引也不应在普通任务中全部加载。

## 核心案例

以下为课程观察摘要及本次工程归纳，均不是讲者对本Skill的背书。时间范围以研究笔记记录为准。

| ID | 来源与范围 | 实际观察与限制 |
| --- | --- | --- |
| S1 | [BV1x6pQ6jE3Y P67](https://www.bilibili.com/video/BV1x6pQ6jE3Y/?p=67)，14:49—16:51 | 代码检查多轮失败后到达上限/END，未见最终检查成功；终止与合格交付需分开 |
| S2 | [BV1aA3c6JEVs P84](https://www.bilibili.com/video/BV1aA3c6JEVs/?p=84)，05:50—17:35 | 护栏拒绝抛未捕获异常；另次配置关闭护栏，天气函数为固定文本，不能当实时天气或正式授权 |
| S3 | [BV1aA3c6JEVs P52](https://www.bilibili.com/video/BV1aA3c6JEVs/?p=52)，04:30—12:33、21:53—27:39 | 纯函数图可以不调用模型；缓存样例改user_id仍返前身份值，说明配置身份与缓存键需要核验 |
| S4 | [BV1x6pQ6jE3Y P78](https://www.bilibili.com/video/BV1x6pQ6jE3Y/?p=78)，04:45—09:44、27:41—33:37 | 模型自行生成Observation；后段手工执行并回填结果，不是完整自主闭环 |
| S5 | [BV1aA3c6JEVs P38](https://www.bilibili.com/video/BV1aA3c6JEVs/?p=38)，06:10—14:07 | 删除、读取、发信是stub，approve/reject是预写决策；不证明外部副作用、真人审批或拒绝后最终停止 |
| S6 | [BV1aA3c6JEVs P77](https://www.bilibili.com/video/BV1aA3c6JEVs/?p=77)，16:00—22:45、31:40附近 | 有真实小样本SQL查询，SELECT前缀/EXPLAIN不足以证明业务口径、行列权限和资源安全 |
| S7 | [BV1x6pQ6jE3Y P59](https://www.bilibili.com/video/BV1x6pQ6jE3Y/?p=59)，03:48—21:55 | 数据库checkpointer接入有响应，未演示进程重启；过滤模型输入与删除历史不是同一动作 |
| S8 | [BV1aA3c6JEVs P78](https://www.bilibili.com/video/BV1aA3c6JEVs/?p=78)，18:20—28:45 | 同一Team内存继续和移交暂停有演示；固定callback不能作为真人输入或跨进程恢复证明 |
| S9 | [BV1aA3c6JEVs P62](https://www.bilibili.com/video/BV1aA3c6JEVs/?p=62)，24:54—30:08 | Session内存/Mock测试；29:53原帧为15 passed，早期10的笔记已勘误，不代表用户授权或多实例持久恢复 |
| S10 | [BV1aA3c6JEVs P81](https://www.bilibili.com/video/BV1aA3c6JEVs/?p=81)，00:00—19:25 | 缓存、GraphRAG索引和工具调用有演示；更快不证明零API调用，索引成功和回答详细不证明逐字段正确 |

六个模型的提炼与边界见 [主题蒸馏记录](research/distillation-synthesis-20261020.md)，它们是适配工作任务的工程归纳。不同框架和不同任务可使用不同实现，不假定某个API或角色组合永久适用。

## 官方方法核对

- [Building effective agents](https://www.anthropic.com/engineering/building-effective-agents)：选择简单可组合结构，按需要增加自主性；不据旧文产品清单决定当前框架。
- [Effective context engineering](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)：按需检索、精简高信号上下文、长期任务的压缩与持久笔记。
- [Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents)：区分执行轨迹与最终结果，使用与任务相称的结果判定。
- 核对时间2026-10-20。具体SDK、参数、版本和供应商能力应在实施时重新核对官方文档，不由课程历史版本推断。

## 勘误与诚实边界

P62通过数采用修订后的15；三份补读笔记曾把终端显示乱码误判为目录title损坏，该判断已被源目录哈希及UTF-8检查的勘误覆盖，本Skill不采纳。P79末尾Traceback根因仍未知，保持未知。P84约13:35—14:06的ASR长重复由细节帧核对核心代码，但不宣称该段口述已无遗漏恢复。

OCR/ASR可能遗漏和误识，抽帧不是连续观看；文件一致和阅读声明不能证明理解或课程结论正确。未核验UP账号与讲者原创身份、未复跑全部课程代码、未训练/微调模型。Skill结构检查或合成任务通过也不能推导生产可靠性或专业工程结论。

## 女娲方法与许可

本Skill按[女娲·Skill造人术](https://github.com/alchaincyf/nuwa-skill)的主题蒸馏路径组织：从案例提取判断模型、应用条件、反模式和局限，再独立验证。方法原作者为[花叔](https://x.com/AlchainHust)，MIT许可保留于 [nuwa-LICENSE.txt](../sources/nuwa-LICENSE.txt)。本次具体工程归纳与实现不代表原作者或课程讲者审定。

历史0.2.0研究保留于原目录，不作为当前代码或API的实时状态。当前Skill使用以上精炼材料；原完整教程目录和旧审阅文件无需在普通任务中自动加载。

本版实际完成的结构检查、独立合成任务及未验证范围见 [0.3.0验证记录](research/skill-validation-030-20261020.md)。
