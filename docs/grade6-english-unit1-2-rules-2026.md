# 高语桐六年级英语 · 单元试卷与云端记录规则（2026-11）

## 来源与新题型（2026-11-09 更新）
- 来源资料仍为 `Unit1 Amazing places 知识清单.docx` 与 `Unit2 Getting together知识清单.docx`，源数据 `source-unit1-amazing-places-2026.json` 和 `source-unit2-getting-together-2026.json` 不因变更题型而更改。
- **家长明确要求的新练习方向：** 所有词汇与词组都只给中文（例如“机场”），由孩子手写或键盘输入完整英文（`airport`）；不再显示英文让孩子选择中文，禁止题干提前泄露目标英文词语。
- **动词变形一律只给原形，让孩子写过去式**（例如 `clean → ______`）；删除 `cleaned → clean` 之类的反向题，避免同页互相泄露答案。
- 新版 Unit 1：11道动词过去式、27道中译英词汇词组、9句英语句子默写、15道语法应用，总计**62题**；Unit 2：10道动词过去式、37道中译英词汇词组、10句句子默写、17道语法应用，总计**74题**。
- Unit 1 `travel → travelled` 按教师清单英式拼法；Unit 2 `read → read` 过去式拼写不变，`dress in → dressed in`、`count down → counted down` 均完整考查。
- 题目示例中的答案只能在完成本轮全部作答并点击批改之后显示。已批改答案在核对后可再次查看；纸笔模式先确认整轮写完，才可显示答案。
- **历史保护：** 新的练习分类标识为 `past-only` / `dictation`，保留旧版 `verbs` / `reading` 的本机存储及云端历史记录。原有的 `QUIZ_ID` 和 `STORE` 不改；云端恢复仍兼容旧分类，但不把旧版英文选中文成绩视作新版中文默写英文。

## Unit 1 + Unit 2 合卷（2026-11-09）
- 将已有 Unit 1（62题）和 Unit 2（74题）的全部题目组合成**一张136题完整试卷**：动词过去式21题、中文默写英文词汇词组64题、句子19题、语法情境32题。以“类型→单元”分区呈现；不需要在两个单元页面切换。
- 新卷 GitHub 源文件：`papers/grade6/unit1-unit2-combined-cloud.html`；在线镜像：`gaoyutong-grade6-science/english/unit1-unit2-combined.html`。
- 合卷整体执行三轮复习：第一轮覆盖全部136题；第二、第三轮复习上轮尚未掌握的题目；保留单题的三轮勾选、纸笔／网页作答、完整作答后批改、错题榜和家庭 Supabase 同步。
- 新卷采用独立 `quiz_id=gaoyutong-grade6-english-unit1-unit2-combined-2026-v1`、`localStorage=gao-english-unit1-unit2-combined-2026-v1`。旧 Unit1/Unit2 试卷、云端历史、当地浏览器草稿均保留，但不会混入新卷的学习轮次或误作为新成绩。
- 已批改的轮次切走再切回保持答案可见，未批改轮次答案隐藏；真实完成并确认核对后才会提交云端成绩。

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
