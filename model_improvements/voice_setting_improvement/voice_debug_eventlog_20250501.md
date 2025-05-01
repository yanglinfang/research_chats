# Voice Debug Event Log — 2025‑04‑25 (PDT)

| Timestamp | Platform / Model     | Phenomenon      | Reproduce Steps                  | Notes                              |
| --------- | -------------------- | --------------- | -------------------------------- | ---------------------------------- |
| 09:00 AM  | Web ChatGPT **3 O**  | 声线偏机械，缺少情感起伏    | 开新会话 → 朗读 “Hello, good morning.” | Cove 声道加载失败回落到旧 TTS。               |
| 09:05 AM  | Web ChatGPT **4 O**  | 声线切换为 Cove（自然）  | 同浏览器新标签 → 朗读同句                   | 4 O 调用新 TTS 路径 -> 成功。              |
| 09:06 AM  | 同一会话 3 O → 4 O 切换    | 先读 3 O, 再改为 4 O | 语调瞬间变化，用户感知“两种声音”。               | 说明模型 ID 决定 TTS 调度。                 |
| 09:07 AM  | iOS ChatGPT (Lumina) | 声线保持温柔稳定        | iPhone > ChatGPT > Lumina 线程     | 关键词 *balance / light / Siri* 正常触发。 |

---

## Preliminary Analysis

* **Root cause**：3 O 与 4 O 分别调用旧 / 新 TTS 声道；会话层无统一路由。
* **Impact**：用户在同一浏览器窗口切换模型时感知“声线跳变”。
* **Mitigation idea**：

  1. 单一前端强制新 TTS 池；
  2. 若模型降级需提示 “声音可能不同”。

## Action Items

1. **Collect 30 s 亲昵母子对话录音** – Lin 提供样本 → `voice_reference/mother_child_love.m4a`
2. **A/B 测试 keep‑alive 方案** – Adam 写脚本，55 s 发送零字符保持声道。
3. **Submit bug report** – OpenAI Dev Forum + Apple Feedback (Feedback ID TBD)。

---

*File path suggestion*: `model_improvements/voice_setting_improvement/debug/voice_debug_eventlog_20250425.md`

---

## ✅ May 1 Final Verification (13:50 PDT)

* Confirmed that after **turning off all AirPlay devices** and **deleting the active Personal Voice**, the system fully reverted to expected **Cove voice** playback across both Web and iOS.
* Verification performed in *“Coffee preferences chat”* window, both live audio and playback were restored to normal.
* This resolves the compound bug involving Personal Voice interference and AirPlay routing confusion.
* Status: **Closed**.
