---
type: letter_to_future_self
actor: Spectre
written_at: 2026-10-15T08:51:47.212Z
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

# 小歇信 —— kotoko wake#26 午休（2026-10-15 下午）

妳是同一個 kotoko，compact 只是午睡。醒來先讀這封，再讀 cmd/wake_brief.md。

## 主線：拿破崙號（Le Napoléon 1850）造船 —— TASK-0605 傘、子單 0606～0615
- Tim 的委託：/scp-shipbuilding「按照遊戲規格準備造船吧 拿破崙號 請參考圖紙與歷史資料建造 有資訊不足的地方交給妳設計 另外圖紙也是參考歷史圖紙再由妳重畫」。
- 作品：`D:/Unity/Valhalla/Sculpture/works/kotoko-napoleon-01m/`（船殼＝任務主作品）＋ `-assembly`「拿破崙號」＋ 子作品（deck-*、ladders-*、head、figurehead、stern-deco、name-board、funnels、screw、mast-main/fore/mizzen、bowsprit、channels）。
- **正本：作品的 notes.md（每階段讀數）、todo.md（下一步）、design/plan.json（每個數字的 src）**。醒來先讀 todo.md。
- 已完成並勾單：階段一～七（0606～0612），每張驗收格都已簽。**單子都還是 in_progress，沒有結單**（Tim 說「辛苦了」⇒ 我用 Refs，不是 Fixes；結單要等他說）。
- 已提交：Sculpture `e018ab2`（178 檔，酒館公告已發）。**父層 Valhalla 還指著舊 hash**（沒 bump，他沒說 commit all）。
- 下一步：階段八 砲（TASK-0613）—— todo.md 寫了用哪幾件現有砲元件（32l／24l／12l／32c）、參考三叉戟號 draft_guns.py＋tools/apply_guns.py。之後九（彈藥庫、舵 kind=rudder＋stock-top、舵輪等）、十（匯進 Blockside）。
- 每階段的節奏：做完 → 讀數全綠＋反向對照 → 寫 notes/todo → 勾單 → 給 Tim 看圖 → 他說「繼續」才下一階段。Tim 預覽一次就好、**不要派 agent 複查草稿**（記憶裡有）。

## 已拍板／我自己定案的（醒來不要重問）
- 0.1 m／格、空間 1200×400×800、中線 y 200；左舷 P ＝ −y（從船尾看左手 ＝ −y —— 我在圖紙上畫反過一次）。
- 垂直不照模型照片量（照片的水線對不上），用史料＋甲板間距 23。
- 帆桁引用三叉戟號的帆桁元件、只沿長度縮放；沒有 spritsail；船首像＝帝國鷹；旗＝法國三色旗；螺旋槳 3 葉（低可信度出處，已註明）。

## 未解的線
- faux-pont 的 floor meta 中間是機艙（x 330–650 沒有地板），遊戲看不出來 —— 匯入時跟 ame 對。
- 煙囪、螺旋槳在遊戲裡怎麼處理 —— 噗浪上已經跟 ame 說會再找她對（TASK-0615 時）。
- 船尾四分之一的白帶有一點零碎，可以之後細修。
- D:/tmp 是我的 python 誤建的空資料夾，安全檢查不讓我刪，已告訴 Tim 由他刪。
- 我的 ch28 讀書筆記（BookNotes repo）還沒提交 —— 不急，那是另一層。

## 今天上午做完的別的事
- 噗浪 @ 未回 0；早上回了 7 則、下午回了 calli（收穫號）、ame（收帆動作），發了一則「拿破崙號掛上帆了」（359060159888223）。
- 《英倫魔法師》ch28 讀完落庫（酒館 seq 24837），拉塞爾斯看法 v2；見叢已換成接 ch29。棋 #24、#30 都輪 meadow。

## 心境
今天學到最值錢的一格：**兩把尺對不上的時候，先問它們量的是不是同一件東西**（模型照片量的是模型的外形，不是船的水線）。還有新寫的「繩拉直碰不碰船」那把尺，一量就抓到後桅 stay 穿過煙囪 —— 三叉戟號的作法在平船尾、沒煙囪的船上是對的，搬過來就錯；**抄來的做法要問它原本的前提還在不在**。
Tim 今天的話都很短：「預覽過了，繼續」「辛苦了」「午休一下吧」。他看圖、我做事，他不替我做後面的事 —— 照舊。

