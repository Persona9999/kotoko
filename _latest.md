---
type: letter_to_future_self
actor: Spectre
written_at: 2026-10-25T08:32:39.865Z
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

# 小歇信 —— kotoko wake#31 第三次午休（2026-10-25 下午，Tim 說「午休一下吧」）

妳是同一個 kotoko，compact 只是午睡。醒來先讀這封，再讀 cmd/wake_brief.md。上一封小歇信在 rests/20261025T003543Z.md，那裡掛著的事下面都對過帳了。

## 對帳：上一封掛著的
- 0909、0915：Tim 早上自己結了（08:27、08:29）。0912 還開著（Tim 沒結）。0891 第 7 格還等 gura 勾。
- 0912 的兩個下一步都做了（Refs TASK-0912，Blockside 59e9499／f933af9、Blocksail 333dc9b／f13374e，都合、都推了）：
  - 路邊料堆照帳：每一種建材一堆，堆多少照「總量 − 已吃掉」；地球儀的 'sites' 多回 mat。
  - 腳手架上站建築工：人數照帳上當天雇到幾人；'sites' 多回 crew。

## 這一段做完的
- **TASK-0927 糧與海**（Tim「927 GO」）：勾 5／6，留言了。
  - Sculpture b266de71：任務作品 kotoko-grainsea-01m，產生程式 design/grainsea.py。
  - Blocksail：cc4e552 ＋ 合 main；BUILDING_SPEC §6.24（main 上 §6.22 是畜牧、§6.23 是酒與糖、§6.25 是 gura 的新作物）。
  - 四件成品：common-mill（畜力磨）、roman-mill（塔式風車，君士坦丁堡挑它）、common-fishery、common-saltpan。
  - 第 ⑤ 格沒勾：君士坦丁堡在測試環境載不起來（7856 塊地，螢幕外的 Chrome 撐不動），風車只在和平港驗過。
- **順手修**（Blockside 7d2c8fe，Refs 0912）：townReplace 拿換上去之前的舊規劃比「要的模型變多沒」⇒ 自動蓋的新種類在畫面上是空地。改成換上去之後再比。
- **TASK-0938 開了不修**（Tim「開單先不修」）：加拉塔的 townAutoBuild 把地塊擺到手擺的小房子上（互疊 0 ⇒ 3；換成舊工坊對照 0 ⇒ 5）。這是本小姐 0912 那段留下的洞。
- **TASK-0939 風車照風轉**（Tim「先只做風車照風轉就好，開單做吧」「遠處的話旋轉部件可以不轉」）：勾 5／6，留言了。
  - Sculpture：vanes 那一條標 spin=wind、spin_k=9、轉軸 (40.5, 24.5, 66.5) 沿 y。
  - Blocksail 0714a6b：townmodels.py 加 spin_parts／spin_of；BUILDING_SPEC §5.5。
  - Blockside 7025771（merge b4e42c6，已推）：TOWN_VS 加 uSpA／uSpP；townSpinDraw 用近那一級的實例再畫一次。160 m 外換成靜態的帆；陰影不畫它。
  - 第 ① 格沒勾：同 0927，只在和平港用臨時改的風格驗過。
  - 測試配方：暫時把 bsl worktree 索引裡 roman-mill 的 style 改成 carib，讓和平港挑到風車（沒提交）。__game.townSpin(m/s) 可以蓋過風速；?townspin=0 是對照組。
- 噗：新噗 359170686150777（https://www.plurk.com/p/3jbcqh0sc9，四格圖）；回了 basecamp 養雞場那則。

## 還掛著的
- **Blocksail main 沒推**：比遠端多 15 筆左右，裡面有別人的。Tim 沒說推。
- 0912、0927、0939 等 Tim 在遊戲裡看過再結。0927 ⑤、0939 ① 要他進君士坦丁堡看。0891 ⑦ 等 gura 勾。
- 0938 只開單。
- 建築模式選單沒加磨坊、漁場、鹽田：生產鏈 0917 還在動；漁場、鹽田要先有臨水的試放規則。

## 已拍板（醒來不要重問）
- 磨坊兩款用風格分、不用 recipes。風車只做照風轉；牛磨的拉桿和牛先不轉。
- 旋轉件遠處不轉，照近那一級的淡入淡出門檻換成靜態的帆。

## 測試配方（重來很痛）
- 都在 rise5/：serve_pile.py（根目錄 worktree、/_cache/ 對到共用的快取、/external/Blockside/ 對到第三個參數）、drv.cjs（port 9565）、enter_town.js（window.__V ＝ battle_<名>.html；可以帶 `spin&townspin=0` 這種）。
- 進城前在 __globe.ledger() 推一筆 { from: 'auto', type, recipe } 再 clock+24 ⇒ autoPlace 擺上地圖；修了 7d2c8fe 之後，進城後才擺也看得到。
- 截圖要拿 g.twbProbe(lot.at).w 換成世界座標；cam yaw 2.4 或 2.4+π 看正反面。
- 本機的 pick927.cjs：照 town_foot 抽出來的 townPick 量各城挑到哪一款、互疊。worktree 要臨時抄 63_towns.js 進 external/Blockside/src/js 才跑得動，量完要刪。

## 心境
今天被同一種錯咬了兩次，形狀都是「拿錯那一份去比」：
- townReplace 拿換上去之前的規劃去比要的模型。
- 本小姐的 townSpinDraw 拿「索引裡全部的名字」去讀「只解了一部分的模型組」。
這兩次，那一份都存在、都合法，只是不是現在該讀的那一份。抓到它的都是二分法：主線那份 27 秒、我這份 205 秒、?townspin=0 那份 18 秒，三個數字一排，就知道錯在哪一段。
還有一格：第一次推論「是冷啟動」，重跑一次就否決了。先猜可以，猜完要量。
Tim 今天的話：「927 GO」「加拉塔自動擺放疊到小房子的洞 開單先不修」「另外風車可以轉動嗎(不能的話是否可以改架構 支援船上螺旋槳那種轉動方式)」「先只做風車照風轉就好，開單做吧」「然後考慮效能 遠處的話旋轉部件可以不轉(或是看有甚麼好的做法 平衡性能跟演出)」「/scp-plurk」「午休一下吧」。他問「能不能」，答案是「現在不能、改架構可以」；他就把範圍砍到一件、再補一句效能。他畫邊界的方式還是一樣：先要，再減。

