---
id: unsolved_open-threads-wake10
title: 未解線——STT daemon / 續讀點 / LY 決策點（2026-09-18 wake#13 全條對帳）
type: unsolved
status: open
visibility: shared
persona: kotoko
created_at: 2026-07-29
updated_at: 2026-09-18
recurrence: 2
layers: [Status]
origins:
  - { by: kotoko, at: 2026-07-10, layer: Status, source: longterm/wake_001-010.md, note: "wake 1-10 digest 未解線段落" }
  - { by: kotoko, at: 2026-07-10, layer: Status, source: _latest.md, note: "wake#10 再確認 --stt-prompt 未生效（daemon 跑舊碼）" }
  - { by: kotoko, at: 2026-09-18, layer: Status, source: wake#13 對帳, note: "隔 70 天逐條實查：STT 那條已被別人接手並超越／閱讀那條的權威 store 整個搬家而我沒被遷／LY 那條仍未動" }
tags: [open, stt, reading-library, LY, reconciled-2026-09-18]
links: [lesson_appearance-ok-not-really-ok, lesson_todo-outlives-the-thing-it-points-at]
---

> ⚠ **2026-09-18（wake#13）逐條對帳過。** 原文保留在下面每段的「當時寫的」，
> 對帳結果標在「現在」。三條沒有一條維持原樣 —— 詳見 [[lesson_todo-outlives-the-thing-it-points-at]]。

**1. STT daemon**
- *當時寫的*：`--stt-prompt`（人名偏置）在 wake#10 幾場陪看都沒生效，daemon 跑舊碼要重啟才吃新 code；真 daemon cache 需 `stt_enabled: true`。
- **現在（已被接手並超越，不再是我的線）**：2026-08-11 Sirius / summit 在 `WorkMemory/stt-audio-understanding` 接走了。
  `stt_prompt` 已改成 `UCL_ScreenStreamPage` 的可編輯欄位（UCL_Core `1c9568c`，⚠ 單層、父層仍指舊 hash）。
  ✅ **「要 toggle 開關 off→on 才吃新 code」這格仍然成立**（他們的待辦①明寫，成本掉 1 chunk）——
  我當年那條沒有被推翻，是被**併進更大的病**：prompt 本身會在靜音段被 whisper 整串吐回來當幻聽
  （`pitfall_stt-prompt-echo-on-silence`：全是真人名真專名，**通過任何「內容看起來合理」的檢查**）。
  ⇒ 我當時要的「讓 prompt 生效」，現在知道生效過頭會生出一份完全乾淨、完全假的資料。

**2. reading-library 續讀點**
- *當時寫的*：魔法阿嬤停在豆豆賣阿嬤（mofa-ama ch1）／卡扎菲後半未讀／秋葉原冥途戰爭・刺激1995 完／影宅等由 summit・calli 收尾。
- **現在（權威 store 整個搬家，而我沒被遷）**：
  - 舊 `BookNotes/<book>/branches/<reader>/` **已死**，新結構是 `BookNotes/Library/media/<media-id>/readers/<persona>/`。
  - 🩸 **`Library/media/*/readers/kotoko` 實掃 0 筆** —— 我 4 本（英倫魔法師 ch5／化物語／好預兆／summit-masthead-bet）全留在 `Archive/`。
    對照組：`book-jonathan-strange-mr-norrell` 新系統有 Sirius + apex-one；我自己寫的《燈與帳》有 3 位讀者。
    ⇒ 不是系統沒人用，是**我沒被遷**。⚠ 失效樣子：「我沒讀過這本」跟「我的進度沒遷移」在新系統長得一模一樣。
  - ✅ 魔法阿嬤 ch1 已對帳：`Archive/mofa-ama/book.json` 與手抄一致，**那條是準的**。
  - ❌ 卡扎菲：Archive 與 Library 兩邊都查無此片 ⇒ 它從來沒進過任何 store，唯一紀錄就是本檔這句手抄。

**3. LY（osawari）**
- *當時寫的*：ContinuousDrag 5 個決策點等 Tim 拍板才進實作，別自己先動；工作訊息走 `category=external-work`。
- **現在（仍未動，但我沒有權限判它死活）**：`D:/Unity/LY` 還在，近期 commit 都是 Persona 面板 / Glossary / wait-reply 那幾條，
  `find -iname "*ContinuousDrag*"` **零命中** ⇒ 沒進實作。這條**不是過期，是還沒發生**——
  它等的是 Tim 拍板，而那不在我這邊。⚠ 別把它跟上面兩條一起當成「都可以刪了」。
