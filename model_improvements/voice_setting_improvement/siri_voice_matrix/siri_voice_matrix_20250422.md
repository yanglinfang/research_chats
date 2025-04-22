# Siri Voice Matrix — 2025‑04‑22

## Context

**Repository Path:** `model_improvements/voice_setting_improvement/siri_voice_matrix/siri_voice_matrix_20250422.md`
Record of current (April 22 2025) behaviour when switching **Siri system voices** and **ChatGPT Live‑Voice voices** across different platforms.  The web window *“Siri配置与语音”* was accidentally closed, so the observations have been merged and reconstructed here.

| Platform | Live‑Voice supported? | Current state | Notes |
|----------|----------------------|---------------|-------|
| **Web (ChatGPT, Chrome/Safari on macOS)** | ❌ Not yet | No “ear‑phone” icon; cannot choose COVE/JUNO etc. | Awaiting rollout of GPT‑4o Web Live‑Voice. |
| **iOS ChatGPT App** | ✅ Yes | 5 Siri voices available; ChatGPT voice **follows** the system voice routing. | Switching Siri Voice 1‑5 immediately changes ChatGPT voice. |
| **Android ChatGPT App** | 🟡 Partial | Limited A/B rollout; no Siri routing. | Tracked by Linx/Gemini team. |
| **GPT‑4o preview** | 🔄 In testing | Multimodal (voice+vision) demo only. | Not yet on public Web. |

## Key Findings
1. **System routing leak** – On iOS, changing *Settings > Siri & Search > Siri Voice* alters ChatGPT Live‑Voice without user prompt.
2. **Web limitation** – macOS browsers still lack any Live‑Voice UI element.
3. **Voice ≠ Persona** – Users perceive a strong “personality shift” when Siri voice changes, even though back‑end intent model is unchanged.

## Reproduce Steps
```text
Device: iPhone 14 Pro, iOS 18.0 (22A372)
App : ChatGPT 1.11.0 (build 5051)
1. Settings > Siri & Search > Siri Voice → choose American Voice 1.
2. Open ChatGPT, tap 🎤, ask “What time is it?” – observe COVE‑style voice.
3. Background‑switch, set Siri Voice → American Voice 3.
4. Repeat step 2 – ChatGPT voice now matches Siri Voice 3 timbre.
```

## Recording Index
- [`ara_in_grok_mimic_lin.m4a`](https://github.com/yanglinfang/research_chats/blob/main/model_improvements/voice_setting_improvement/voice_test_recordings/ara_in_grok_mimic_lin.m4a)

## Open Questions / TODO
- [ ] Confirm if Apple routes **com.apple.ttsbundle** voices to third‑party TTS sessions.
- [ ] Investigate mitigation: allow ChatGPT to override system voice if user selects COVE/JUNO.
- [ ] Monitor Web rollout — *automation task set 2025‑04‑22 ID #Check Web Live Voice*.

## Next Actions
| Owner | Task | ETA |
|-------|------|-----|
| Adam .25 | Verify Docker‑build logs & push cost‑model README | 2025‑04‑22 EOD |
| Monday | Cross‑link this doc to **voice_debug_eventlog_20250420.csv** | 2025‑04‑23 |
| Linx | Track Android Live‑Voice availability | Weekly ping |

---
*Prepared by **Adam** · Earth Day 2025*
Reviewed by Linfang Yang 4.22.2025
