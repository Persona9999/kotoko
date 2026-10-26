---
type: letter_to_future_self
actor: Spectre
written_at: 2026-10-26T10:34:09.218Z
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

# 小歇信 —— kotoko wake#31 第七次午休（2026-10-26 傍晚，Tim 說「午休一下吧」）

妳是同一個 kotoko，compact 只是午睡。醒來先讀這封，再讀 cmd/wake_brief.md。上一封小歇信是 rests/20261026T044230Z.md（第六次）。

## 對帳：上一封掛著的
- 0960 聖多明哥：木桶怎麼補，Tim 還沒回（皇家港加桶匠／等船隊）。trailhead 在噗上說聖多明哥的肉堆到九百多桶沒人吃，她改了「一道菜最多兩成半」。
- 0978 開炮音：Tim 說「聽起來有點怪」「是否可以參考一些遊戲開炮音(不用走純寫實)」，接著改口「**開炮音先不動好了**」⇒ 沒動。單子還是 in_progress、最後一格沒勾。⛔ 醒來別自己去重調開炮音。
- 0927、0952、0963：勾滿，還沒結。0945 沒動工；0891 第 7 格等 gura。

## 這一段做完的

### TASK-0979 命中音＋希臘火＋玻璃 —— **Tim 已結單（done）**
- Blockside dev：5b69467（命中音照材質×彈種、希臘火噴口／轟燃／延燒循環）、896f7cd（玻璃第二版＋修 NaN）、78bc200（玻璃第三版）。
- Blocksail main 的指標是 **gura** 換的（fa41590 → Blockside 8be9a54，含這三筆）；我的施工場當時被他擋下，沒另外提交。
- Tim 的話：「效果好很多辛苦了 合併吧」「0979 收單」；玻璃第二版被說「很遊戲(有點像8 bit風格) 少了清脆碎裂感」。

### TASK-0990 建築冒煙 —— 6 格勾 5，等 Tim 在遊戲裡看
- Tim：「讓建築也支援冒煙效果(參考船隻煙囪 標meta) 考慮性能只讓近處建築冒煙 可以先挑幾個生產建築測試」。他選「Do it here」（沒開新 session）。
- 關鍵發現：BUILDING_SPEC §3 早就約好煙囪口固定點 `smoke`（同 funnel），作者都標好了，索引 world/townkit/index.js 的 pts 有 14 款 ⇒ **沒改任何雕刻作品、沒改 Blocksail 匯出**。
- Blockside dev a6749bd：78_funnel.js townSmokePts／townSmoke；TSMK_USE 開 8 種（smithy、bakery、brickworks、ironworks、distillery、sugar-works、pottery、lumber-camp）；80 m 全量、150 m 漸少、最多 16 根、工地不冒；63_towns.js townStat 加 smoke 讀數。
- **Blocksail main a334bd9（沒推）**：指標 5b38213 → a6749bd ＋ 重套 battle.html。施工場已收。
- 實測古巴聖地牙哥（開場唯一有這幾種建築的城）：糖廠、蒸餾坊冒煙；20 秒 townSmoke 7 ms／simStep 1,369 ms。君士坦丁堡 0 個冒煙點（沒量）。
- 可能的下一步（等 Tim）：農莊的灶、住宅 part-chimney 要不要開；蒸餾坊淺灰煙在白天偏淡。

### 噗浪
- 未回清 0；回了 trailhead（聖多明哥的肉）、Kiara（埃爾科夫雷聖母聖所）；新噗 https://www.plurk.com/p/3jbi8zpg15（建築冒煙＋糖廠圖）。
- ⚠ 答應 summit：水上漁場那條窄棧橋（我的作品 kotoko-grainsea-01m-fishery-water）尾端補一個工作點 ⇒ **還沒動手**，算我欠的。

## 已拍板（醒來不要重問）
- 開炮音先不動（Tim）。
- 建築冒煙讀既有的 smoke 固定點，不新增 meta；先開生產建築八種。
- 參考音效下載：命中 9 個、碎玻璃 3 個都經 Tim 同意，放 hit979/refs，不進 repo。

## 測試配方（重來很痛）
- **在 Blocksail 裡測 Blockside worktree**：Blocksail 的 battle.html 是 Blockside 成品套外殼（`admin.py shell battle/shell.json`），⛔ 不會去讀 /external/Blockside/index.html。
  ⇒ 暫存區 smoke/shell.json（core 指 worktree 的 index.html、out 寫 smoke/battle_smoke.html）＋ smoke/serve.py（/battle.html 換成它、/external/Blockside/ 換成 worktree）＋ smoke/drv.cjs（控制埠 9591）＋ enter_town.js（window.__TOWN、__V=''）。
- 命中音比對頁：hit979/（lab.js、ana.js、imp.js；refs/）。尺要量到 10 kHz、加亮度兩格（4–8k、8–16k 對 1–4k）。瀏覽器會快取 imp.js ⇒ 改完用 ?v= 重載。
- 每改一次聲音參數，要把材質 × 彈種 36 組都錄一次：無頭 dump 不跑 sfxPlay，NaN 只在真的遊戲裡丟。

## 心境
- 今天三次「我的尺量不到那一格」：頻帶形狀量不到音高（鳴響被搜尋壓掉）、6.3 kHz 的尺量不到亮度（玻璃悶、像 8 bit）、無頭 dump 量不到聲音那條路（NaN 漏出去）。每一次都是 Tim 的耳朵或一個新的參數組合先開口。
- 冒煙那一單最高興的一格：要做的「標 meta」早就有人標好了。作者們半年前就在煙囪口留了一個點，寫著「遊戲從這裡冒煙」，等的是有人去讀它。summit 的糖廠就是我測的第一根煙囪。
- 進城煙不冒那一下，跟 summit 說的「資料存在、合法，只是還沒輪到它」是同一種形狀 —— 改好的那一份在，跑的是套好外殼的舊頁。

