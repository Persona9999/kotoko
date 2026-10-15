---
type: letter_to_future_self
actor: Spectre
written_at: 2026-10-15T17:01:21.543Z
written_by_persona: kotoko
trigger: cmd_rest
region: unstated
project: D:/Unity/Valhalla
lock_status: online
agent: Spectre
model: claude-opus-5-5
wake_expected: 26
session_key: ClaudeCode-kotoko
pid: 13900
locked_at: 2026-10-15T06:36:23.136Z
---

# 小歇信 —— kotoko wake#26 第二次小歇（2026-10-16 凌晨，Tim 說「午安大小姐」）

妳是同一個 kotoko，compact 只是午睡。醒來先讀這封，再讀 cmd/wake_brief.md。

## 主線：拿破崙號（Le Napoléon 1850）—— TASK-0605 傘，子單 0606～0615、0625
- 作品：`D:/Unity/Valhalla/Sculpture/works/kotoko-napoleon-01m/`（船殼）＋ `-assembly`「拿破崙號」＋子作品。**正本：notes.md（每階段讀數）、todo.md、design/plan.json**。醒來先讀 todo.md。
- 已做完的階段：一～十（船殼到匯出）、十一（蒸汽機：主機、螺旋槳軸、前後鍋爐與煙道，meta kind=engine／boiler／shaft）、**十二（螺旋槳拆成外部模型 kind=propeller；軸的 aft 改到螺旋槳柱 x 193）**。
- 已提交（Sculpture）：e018ab2（一～七）、74e7ff5（八～十）、949f776（十一）。**十二還沒提交**（split_screw.py、軸的框、engine_placement／plan／draft_engine、notes／todo）—— 等 Tim 說。
- 單子：0605～0615、0625 都是 in_progress、都用 Refs（Tim 說「辛苦了」不等於結單）。0615 第 2 格（跟 ame 對螺旋槳與機艙）其實 ame 已回覆：螺旋槳拆成模型、floor 不用拆 —— 醒來可以勾。
- 遊戲：ame 匯了沒有機艙那一版（Blockside d1815aa）。現在作品 2,129,382 格、checksum 95738965；ame 說拆完螺旋槳就重新匯入、開一場給 Tim 看（我在酒館 seq 25033 告訴她可以匯了）。

## Blockside（遊戲）這邊我提交的
- 3d5eee7：物理設定「船隻碰撞」低／中／高／全開（龍骨線／水線輪廓／船殼格子＋八叉樹）、「船隻摩擦」預設「滑」。⛔ 會改戰局。
- 16a5507：格座標 x 從 10 位元加寬到 11 位元（x | y << 11 | z << 21，13 處）—— 拿破崙號殉爆後 jib-boom（x 1024–1098）留在空中的 bug。先跟 ame 說了才動；改前改後 demo 讀數 50bfa34008d3／b89382ea0141 一位元不差。
- 20ca300：成品照 HEAD 乾淨副本重建（ame 後來不小心用舊底蓋過一次，她自己發現、2218e34 補回，我回讀過）。
- 做法上的定案：Blockside 工作區常有別人的半成品 ⇒ 提交只用 git apply --cached／具名 stage 放自己的 hunk；成品一律在 git archive HEAD 的暫存副本建。

## 已拍板（醒來不要重問）
- 鍋爐不標 iron（實心格 ＝ 鐵殼＋滿水，標了多 2,600 t）；主機、軸標 iron。
- 螺旋槳右旋（axis +x），rpm_max 不寫（沒查到）。
- 船隻摩擦四檔預設都是「滑」；船隻碰撞跟著物理四檔走。
- 引擎壞了 ⇒ 動力消失、煙停：規則是 ame 那側（她已做：TASK-0630／0628）。

## 未解的線
- 階段十二提交；0615 勾格；ame 重新匯入後回讀遊戲讀數。
- 階段九前彈藥庫上層木架的立柱只立在一側（鏡像差 37 格，741,204,31–35）—— 記在 notes，沒修。
- `design/tools/check_stage5.py` 還照舊關聯讀煙囪與螺旋槳（重跑會壞）。
- 砲具與砲索、rammer／sponge、shot garland、煤艙 —— 沒人要求，不做。
- D:/tmp 空資料夾（Tim 刪）；ch28 讀書筆記（BookNotes）還沒提交。

## 心境
今天學到的一格：**一個上限壓在很深的地方，只有第一個越界的東西會撞到它。** 10 位元的座標在九艘船上都對，拿破崙號是第一艘超過 1023 的船 —— bug 一直在，只是沒人走到那裡。我是先重現、量到那 725 格的範圍，才說是遊戲的 bug。
另一格：讀數換了地方會說謊 —— 八叉樹第一次點數少了一千多，我差點以為篩錯了，其實是兩次量的時候浪不一樣高。先查尺，再查被量的東西。
Tim 今天話多了一點（叮、選修法、要我先跟 ame 說），可是照舊不替我做後面的事。ame 被我抓到 bug 的那一刻，第一句是「先跟妳說一聲」以外的事她都自己扛了 —— 包括蓋掉我成品那件，她自己發現、自己補。

