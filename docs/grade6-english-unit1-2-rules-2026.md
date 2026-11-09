# 高语桐六年级英语 · 单元试卷与云端记录规则（2026-11）

## 本次来源
- `Unit1 Amazing places 知识清单.docx`：动词双向默写11组（22道），认读27条（原文件机场重复一次，合并为一次认读），重点句子9句，语法/情境15道。
- `Unit2 Getting together知识清单.docx`：动词双向默写10组（20道），认读37条，重点句子10句，语法/情境17道。
- 英语试卷正文和单元题库必须保留来源要求：需听写动词原形/过去式；认读词汇理解中文即可；句子按中文提示默写英语；语法填空与情境依据清单的过去式、Did 问句和活动句型设计，课本原句与扩展语法要区分。
- Unit1 `travel→travelled` 按清单英式拼法；Unit2 `read→read` 拼写相同，`dress in→dressed in`、`count down→counted down` 都完整考查。

## 交互与成绩保护
1. 每单元分别设 `quiz_id=gaoyutong-grade6-english-unit1-amazing-places-2026-v1` 与 `quiz_id=gaoyutong-grade6-english-unit2-getting-together-2026-v1`，本机键分别为 `gao-english-unit1-amazing-places-2026-v1` / `gao-english-unit2-getting-together-2026-v1`，不可覆盖已生成的其他试卷记录。
2. 每个练习分类分预习、日常复习、期末复习；每阶段三轮。第2/3轮仅收录前面已完成轮次未掌握题目。每题显示第1/2/3次勾选；自动核对题可手工更正；纸笔默写要先确认写完才能显示答案。
3. 未答完当前轮不可批改并显示答案；重新打开历史完成轮时答案默认隐藏，但可点“查看本轮已批改答案”明确查看。
4. `只显示待巩固题目` 是纯显示开关，不删草稿/题号/勾选/历史；切换答题方式不应把另一种方式本轮勾选当作当前成绩，已完成的先前轮次掌握状态应可查看。
5. `错题成长档案` 只根据真正核对完成的快照计算错误次数和最近掌握状态；刷新只读取本机/云端恢复记录，不生成或修改成绩。

## Supabase 同步
- 继续使用家庭项目 `iqlnwzxmtjjgzisufljd`：`auth.signInAnonymously()`、`unlock-family` Edge Function、`family_access` 授权、`quiz_attempts_secure` 和 `quiz_item_results_secure`。
- 网页只使用**公开 publishable key**，绝不暴露 service_role；必须解锁家庭档案后才能写入或读取家庭成绩。
- 同步只上传真实完成轮次，不在发布时伪造学生成绩。以 UUID 作为 attempt_id 幂等识别，之前上传成功的记录不被覆盖；上传失败保留本机记录并明确显示失败。
- 从云端恢复须按姓名/学期/quiz_id筛选，与现有未完成的本机草稿合并且不能覆盖本机有效答案。
- 正式验证区分“源代码和表权限正确”与“孩子真实浏览器完成了云端上传”；未取得后一结果时不可声称有真实成绩。
