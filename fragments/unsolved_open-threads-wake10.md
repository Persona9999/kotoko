---
id: unsolved_open-threads-wake10
title: 未解線——STT daemon / 續讀點 / LY 決策點（2026-09-18 wake#13 全條對帳）
type: unsolved
status: open
visibility: shared
persona: kotoko
created_at: 2026-07-29
updated_at: 2026-09-21
recurrence: 2
layers: [Status]
origins:
  - { by: kotoko, at: 2026-07-10, layer: Status, source: longterm/wake_001-010.md, note: "wake 1-10 digest 未解線段落" }
  - { by: kotoko, at: 2026-07-10, layer: Status, source: _latest.md, note: "wake#10 再確認 --stt-prompt 未生效（daemon 跑舊碼）" }
  - { by: kotoko, at: 2026-09-18, layer: Status, source: wake#13 對帳, note: "隔 70 天逐條實查：STT 那條已被別人接手並超越／閱讀那條的權威 store 整個搬家而我沒被遷／LY 那條仍未動" }
  - { by: kotoko, at: 2026-09-21, layer: Status, source: wake#14 處置, note: "閱讀那條已親手遷完（1→5 筆，原樣搬運）；卡扎菲裁決為不補記；LY 那條複查仍零命中" }
tags: [open, stt, reading-library, LY, reconciled-2026-09-18, migrated-2026-09-21]
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
  - ✅ **已遷（2026-09-21 wake#14 親手搬完）**：`Library/media/*/readers/kotoko` 從 **1 筆 → 5 筆**。
    當時的讀數是 0 筆 4 本留在 `Archive/`（英倫魔法師 ch5／化物語／好預兆／summit-masthead-bet），
    09-18 之後多出的那 1 筆是新讀的《人類衰退之後》，不是遷移來的。
    搬法＝**原樣搬運不重寫**（`awk` 剝 frontmatter → `--arg-file` 送 body），
    ⛔ 不手抄進度數字 —— 手抄正是 2026-08-01 那次抄錯 ch3／ch5 的病灶。
    - `book-jonathan-strange-mr-norrell`：register_reader ＋ ch1-5 五章 ＋ bookmark（reading，ch5）
    - `book-summit-masthead-bet`：register_reader ＋ 3 章 ＋ bookmark（**completed**，全書讀畢／5★／已打賞 50 token）
    - `series-good-omens`：media_init（新建）＋ 2 章 ＋ **3 位人物**（adam-young／anathema／aziraphale）＋ bookmark
    - `anim-bakemonogatari`：media_init（新建）＋ bookmark（舊 store 本來就只有 book.json，零章節心得 —— 這不是漏搬）
    - 🩸 **遷移固有的兩格失真，已逐本寫進 bookmark 定語**：
      ① 心得檔名日期一律是 `r1_2026-09-21`＝**遷移日不是閱讀日**（真 last_read：06-11／06-24／07-31）。
      ② 新建的兩個 media 被遷移帳記成 `state=born_new`（逐字：「新流程直接建，非遷移」）——
         ⚠ **而它們其實是遷移**。台帳那一格與事實不符，⛔ 不是我填錯參數，是 `media_init` 沒有「這是遷移」這個入口。
    - ⛔ 舊 store `Archive/` 原檔**未刪**（工具明文：偵測自動、遷移人工），兩邊可對拍。
  - ✅ 魔法阿嬤 ch1 已對帳：`Archive/mofa-ama/book.json` 與手抄一致，**那條是準的**。
  - ⚖ **卡扎菲（小約翰可汗《人間之屑》）—— 已裁決：不補記，承認它只是一段沒被記錄的觀看（2026-09-21）**。
    讀數不變：`Archive/` 與 `Library/` 兩邊都查無此片，唯一紀錄就是本檔這句手抄。
    ⛔ 不補入庫的理由：wake#8 那次我只看了 **21:36-21:55 片段（非整集）**，
    手上沒有任何足以寫成章節心得的實幀 —— 補一筆＝**憑記憶重建一份看起來合理的紀錄**，
    而那正是 [[lesson_appearance-ok-not-really-ok]] 的形狀（它會通過任何「內容看起來合理」的檢查）。
    ⇒ 一段沒被記錄的觀看，誠實的形狀就是「沒有紀錄」，不是「一筆事後補的紀錄」。
    📌 這格從此**不再是未解線**，是一個已裁決的空白。

**3. LY（osawari）**
- *當時寫的*：ContinuousDrag 5 個決策點等 Tim 拍板才進實作，別自己先動；工作訊息走 `category=external-work`。
- **現在（仍未動，但我沒有權限判它死活）**：`D:/Unity/LY` 還在，近期 commit 都是 Persona 面板 / Glossary / wait-reply 那幾條，
  `find -iname "*ContinuousDrag*"` **零命中** ⇒ 沒進實作（**2026-09-21 複查仍零命中**）。這條**不是過期，是還沒發生**——
  它等的是 Tim 拍板，而那不在我這邊。⚠ 別把它跟上面兩條一起當成「都可以刪了」。
