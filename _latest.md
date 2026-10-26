---
type: letter_to_future_self
actor: Spectre
written_at: 2026-10-26T04:42:30.318Z
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

# 小歇信 —— kotoko wake#31 第六次午休（2026-10-26 上午，Tim 說「午休一下吧」）

妳是同一個 kotoko，compact 只是午睡。醒來先讀這封，再讀 cmd/wake_brief.md。上一封小歇信是 rests/20261025T193637Z.md。

## 對帳：上一封掛著的
- 0939：Tim 已結（done）。
- 0927、0952、0963：勾滿，還沒結。
- 0945：還沒動工；0891 第 7 格：還在等 gura。
- Blocksail main、Sculpture：都還沒推（Tim 沒說推）。

## 這一段做完的

### TASK-0960 聖多明哥（Tim：/scp-blocksail-town「挑一座城鎮來建造吧」）
- 主單 0957 底下有四座：0958 聖地牙哥（basecamp，已合）、0961 亞拉斯（summit）、0959 埃爾科夫雷（內陸沒港口、要先問 Tim，沒挑）。我挑 0960。
- 已快轉合進 Blocksail main 4e2bffe（e58160e＋合 main），**沒推**。6 格勾 5，**開場檔那一格沒勾**。
- **範圍**：world/areas/windward.js 的 town-santo-domingo。
  - 港口那一點挪近河口：[-69.8825, 18.467]。
  - 手畫 core：原本港口旁的岸是 26° 的陡坎，路上限 18°，走不到。
  - 種子 2453707583：照 id 算的那一個，報表自檢不過（巷擦門 5.4 m）。
- **手動配置** world/towns/town-santo-domingo.js：五種開場建築＋一座鹽田，位置用 townAutoBuild 找；製革坊要鹽，所以加鹽田。
- **開場檔**：`town_start --write` 跑兩次。第一次補糧在加建築之前，新城那時還沒有建築，所以要第二次。其他城一個檔都沒動。land_start、forage_start 也只改這一座。
- **一年模擬**（第 60 天之後，桶／天）：牛皮 0.285、皮革 0.068、雞蛋 0.060、家具 0.009；**木桶 0**。
  - 木桶要鐵件，城附近 10 km 內沒有鐵礦，模擬裡城跟城之間也沒有貨運。
  - **問了 Tim 怎麼補，他還沒回**。我推薦在皇家港加一座桶匠（那裡有產鐵件），另一個選項是等 0911／0949 的船隊、航線。
- **town_report 修了一處**：`--mutate` 的「穿牆假路」以前硬算多一區，改成用 segSeg 當場量。七座城 `--all --mutate` 全部逐項對上。
- **其他**：
  - main 的烘規劃全部重烘過了（windward.js 改了，指紋全過期）。
  - 酒館已告訴 summit、basecamp：windward.js 的排序、合併可能撞到。

### Tasks repo 網頁（Tim：在 Tasks repo 加 GitHub Pages 任務查看網頁）
- 開了另一個 session 做（local_b9d7e8fd）：合進 master、推上去、Pages 也重建了。

### TASK-0978 開炮音（Tim：「海戰開炮聲音優化 一樣用合成音 根據砲的種類 口徑有音色變化」「參考頻譜用合成音模擬」）
- 我開的單、我認領的。已推 Blockside dev 82abb89（6b3167c＋合 dev），6 格勾 5，等 Tim 在遊戲裡聽。
- **⚠ Blocksail 的子模組指標沒 bump**：共用的 Blockside 目錄 erina 正在合併（UU），我沒碰。
- **做法**：
  - 02_audio.js 的 gunSndPar／gunVoice／gunLab，shotFx 傳 `{ gun }` 進來。
  - 四層雜音（爆風、身體、脆響、尾聲），小砲再加一聲回音。
  - 四個錨點用座標搜尋調參數；錨點之間照 ln(彈重) 內插。
  - 主頻釘在立方根定律：中口徑那組參考錄音帶回響、量到 200 Hz，照它的話 120 mm 會比 4 磅砲還尖。
- **讀數**（頻帶差 dB）：8 磅 3.0、12 cm 1.5、Canet 2.9、37 mm 5.0；以前那一聲 9～12。
- **參考錄音**在暫存區 sfx960/refs（約 30 MB）；比對頁 sfx960（lab.js、fit.js、groups.js）；試聽檔在 sfx960/listen。
- **Tim 的選項**：「聽過了很好」或「要再調」，他還沒回。

## 已拍板（醒來不要重問）
- 開炮音只用合成，錄音只拿來量。
- 聖多明哥用種子 2453707583、手畫 core。

## 測試配方（重來很痛）
- **Blocksail worktree 進城**：
  - 子模組要從本機的那一份初始化。
  - townmesh 用 junction 指到主工作區；拆的時候用 `cmd /c rmdir "<完整反斜線路徑>"`。我第一次在 PowerShell 拼字串拼錯了。
- **rise5/drv.cjs**：螢幕外的 Chrome，畫面照常更新。
  - 截圖：`/shot?f=`。
  - 進城：`__globe.place` → `sailTown` → `battleIn('town')` → iframe 加 `&debug=1` → postMessage go。
  - 鏡頭：`setInterval(G.cam)`，角度用弧度。
  - 用完 `/quit`。
- **Blockside build --code**：要先 `git checkout -- index.html`。合併時取 `--theirs` 再 `--code`，它會用 MERGE_HEAD 自己驗。
- **推 dev**：直接從 worktree `git push dev HEAD:dev`，不用經過共用目錄。

## 心境
- 今天兩次「先信形狀，數字才開口」：
  - 合成音的頻帶形狀對了，可是音量只有一半。最佳化器只看我給它的那一把尺。
  - 小砲的 −20 dB 從 0.05 跳到 0.27，是那把尺卡在第一個谷夠不夠深；包絡並排一看，形狀根本一樣。不過也因為並排看，才發現 0.15 秒湧回 −5 dB，像連著兩聲。
- 尺的讀數變了，先看它量的那一格是不是真的變了；看了之後，常常會撞見另一個真的問題。
- Tim 中途補了一句「不是實際使用真實錄音」——我本來就沒打算用，但他先劃線，照舊是加需求的同一口氣先劃界線。

