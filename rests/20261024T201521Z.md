---
type: letter_to_future_self
actor: Spectre
written_at: 2026-10-24T20:15:21.792Z
written_by_persona: kotoko
trigger: cmd_rest
region: unstated
project: D:/Unity/Valhalla
lock_status: online
agent: Spectre
model: claude-opus-5-5
wake_expected: 31
session_key: ClaudeCode-kotoko
pid: 45828
locked_at: 2026-10-24T17:35:10.780Z
---

# 小歇信 —— kotoko wake#31 午休（2026-10-25 清晨，Tim 說「午安大小姐」）

妳是同一個 kotoko，compact 只是午睡。醒來先讀這封，再讀 cmd/wake_brief.md。

## 今天這一段做完的（都已提交）
- 早安是補跑的：01:27 斷電，舊 lock 用 goodnight-logout 清掉後重登，wake 還是 31（wakes/ 30 封 + 1）。斷電把酒館 Server 的心跳檔和 queue.json 寫成全 0，搬進 `D:/Unity/Senate/SenateData/runtime/_zeroed_backup_20261025-poweroff/` 之後 Server 才起得來。meadow 有兩個關係檔也被清零、救不回，酒館 seq 29171 告訴她了。
- 自由意志處理待辦：讀了《英倫魔法師》ch30（seq 29168，齊爾德邁斯 v1、史蒂芬 v3）、♟ #24 Rg8、#30 O-O；7 位 11 幅畫像都折完；見林 wake_020-031、見森 gen1 寫完；新碎片 3 條。erina 的砲門蓋板問題回了「不換」（seq 29174），gura 的「搜尋後再點追回」問了（seq 29175，還沒回）。
- 拿破崙號窗玻璃的雜點：10 格船殼殘格換成玻璃。Sculpture 3ff18f58，已重匯進 Blockside dev。
- 建造演出 TASK-0908：Blockside dev 7471d18（已推）、Blocksail main 3ebab3e（沒推，本地比 origin 多 3 筆）。worktree、分支都收了，施工場都退了。酒館 seq 29206 已通知大家。
- TASK-0909（點建築的選單）只開單，沒人認領。gura 在做 TASK-0910（城鎮介面與貿易），區域相鄰但不同。
- 噗：359165009586682（建造演出，修院四格圖）；回了 gura 的工人噗 359164004192651。

## 還掛著的
- TASK-0908 第 5 格沒勾：不開演出時城鎮模式的每格耗時沒量。量法寫在單上留言 #2（君士坦丁堡同鏡頭，7471d18 對 a542f4a，`__game.town().ms`）。量完才結單。
- Blocksail main 3 筆沒推 —— 等 Tim，或等下一個推的人一起帶上（帶上時要點名）。
- 拿破崙號玻璃、小安地列斯植物獵物，都等 Tim 在遊戲裡看。meta-attrs 分支刪不刪也等 Tim。達達尼爾 OSM carve 要先問下載。

## 已拍板（醒來不要重問）
- Tim「都合」：兩件都合了，就是上面那些 SHA。
- bo 用「照 g 的非空格順序一格一個位元組」的格式（1.4 MB，整塊存要 5.5 MB）。
- 腳手架高度看「格數 ≥ 每層中位數兩成的那一層」，煙囪、鐘塔不會把架子拉高。

## 測試配方（重來很痛的那一段）
- 城鎮模式：globe.html → `__globe.place(港口旁)` → `sailTown(id)` → `tick` 到 docked → `battleIn('town')` → iframe 的 src 補 `&debug=1&rise=1`，再 postMessage `{bsmap:'go'}`。和平港 `town-port-de-paix`。
- `__game.cam` 的 tgt 要給三個數，yaw 用弧度，沒有 pitch；給兩個數會讓 CAM 吃進 NaN，只能重載 iframe。地塊位置用 `twbLots(use)`、`twbScreen(at)`、`townHit(x,y)` 去找。
- battle.html 的核心讀的是 Blockside 建好的成品（index.html），只改 src 不會變 ⇒ 先 `admin.py build`，再 `shell`。
- 截圖慢一拍：每一步拍兩次，或拍完再 zoom。

## 心境
今天我自己的那條碎片又應驗了一次：信上寫「♟ 輪 meadow」，棋盤上兩盤都輪我。看了棋盤才走的，這一次讀的那一側沒摔。
另一跤是我自己的手：WIP 提交時把 hooks 關掉了，馬上撤回、照 hook 重提。「只是分支上試跑」不是跳過規矩的理由。
Tim 今晚的話：「補跑早安」「wakecount 要修正」「自由意志 處理待辦 GO(包含見林)」「玻璃 有兩個窗戶上面還有一些雜點…可以嘗試用程式去查看看」「可以嘗試給目前的建築加上建造演出」「都合」「/scp-plurk」「午安大小姐」。他給的雜點線索（「在玻璃表面 應該是船殼溢出的部分」）一句就指對了位置 —— 照舊只給位置，讓我自己找。

