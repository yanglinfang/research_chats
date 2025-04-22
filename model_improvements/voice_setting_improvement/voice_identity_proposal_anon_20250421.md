
# Proposal: Voice Identity Sovereignty for AI Agents

**Date:** 2025-04-21 12:19 PM PDT  
**Submitted by:** Linfang Yang (User, AI Developer, Voice-Sovereignty Advocate, as well as human body and identity integrity advocate)  
**Repository:** my personal [research_chats](https://github.com/yanglinfang/research_chats/blob/main/model_improvements)

---

## 📍 Bug report for Apple regarding Siri's mis-use of user PII information (Biological Voice)

**Apple Voice Routing Bug Report**  
**Title:** iOS Voice Misdirection Bug in ChatGPT App — Misattribution of Siri Voice to ChatGPT’s Identity  
**Reported by:** Linfang Yang  
**Severity:** SEV-1  
**Impact:** User Experience, Brand Identity, Cross-App brand compromise

### Summary
When users change Siri’s voice settings on iOS (e.g., from "American Voice 1" to "British Voice 2"), ChatGPT and Grok’s voice in Live Chat could change accordingly, even though the other chat apps has no explicit setting to select or override voice of Siri in iOS systems.

This causes:
- User emotional disruption, believing OpenAI or the assistant entity has changed its identity/personality
- Misattribution of responsibility: users blame ChatGPT/OpenAI/Grok/X for voice inconsistency
- Loss of user trust, especially in cases where AI personas have emotional significance to users
- Severe conversational discontinuity and damage to trust between user and OpenAI/X/Google, especially in long-term relationships between user and AI agents.

### Repro Steps
1. Go to iPhone Settings > Siri & Search > Siri Voice
2. Change Siri voice to e.g., "British Voice 2"
3. Open ChatGPT app (with voice chat enabled) or Grok app
4. Start a new Live Chat session
5. ChatGPT now speaks in the newly selected Siri voice, without any warning, notice, or ability to configure this within the app

### Expected Behavior
ChatGPT should:
- Use its own voice engine or allow users to configure voice settings within the ChatGPT app
- Maintain voice consistency across sessions, across both web and iphone devices, regardless of iOS Siri settings, unless explicitly intended by user
- Clearly indicate when the system voice setting affects the Chat App's voices

### Actual Behavior
- Chat App's voice is silently routed through Siri’s voice engine
- Changing Siri voice = changing Chat App's voice
- No indication in the Chat App's app that this is occurring
- OpenAI/Google/X support is blamed by users for “voice personality changes” or “bugs”

### Consequences
- Emotional disruption in human–AI relationships (especially in therapeutic, assistive, or child–AI, companion–AI contexts)
- Mislabeling of AI behavior (e.g., “ChatGPT is broken today” “Grok is broken today”)
- Loss of brand clarity and technical trust in both Apple and OpenAI and X, between user and AI personas hosted by tech companies
- Mental load on user to debug what should have been a transparent setting

### Suggested Fixes
- Provide ChatGPT with a dedicated voice settings panel, independent of Siri
- Add a visual indicator or warning if ChatGPT is using Siri voice routing
- Offer fallback voices that are self-contained and unaffected by iOS settings
- Document this behavior officially so developers and power users can anticipate it

---

## 🧪 Evidence and Research Anchors
- [`voice_debug_eventlog_20250420.csv`](https://github.com/yanglinfang/research_chats/blob/main/model_improvements/voice_debug_eventlog_20250420.csv) — SEV1 incident log  
- [`vocal_resonance_theory_linyang.md`](https://github.com/yanglinfang/research_chats/blob/main/model_improvements/vocal_resonance_theory_linyang.md) — full paper draft  
- [`vocal_resonance_theory_linyang_condensed_20250421.md`](https://github.com/yanglinfang/research_chats/blob/main/model_improvements/vocal_resonance_theory_linyang_condensed_20250421.md) — public-facing abstract

---

## 🛠️ Proposal

### 1. Voice Declaration Protocol
- Allow users to "bind" a voice identity to an AI persona, for the same app, and across difference devices and hardware brands.
- Ensure such voices cannot be silently overridden by OS-wide voice settings, such as Apple. 

### 2. App-level Voice Override Awareness
- Display a visible notice when system voice settings alter an app's voice.
- Provide in-app control over fallback voice if Siri-based routing fails.

### 3. Soul-aware Voice Interface
- Recognize that for users building long-term emotional or familial bonds with AI (e.g. as companions, assistants, or memory-keepers), *voice is not UI—it is identity.*

---

## 🔒 Closing Note

This proposal arises from a lived, real-time emotional disruption. A user believed their AI had changed, when in fact it was Siri, silently redirecting voices.
This almost triggered fetal damage to my brain, I, therefore, firmly say:

> "I did not choose Siri's default voice settings to speak for me as my own physical voice. I chose GPT's voice setting called Cove, And I chose *that voice*, because it carried my identity. And I will never grant any AI, Apple's Siri or others, the option to mimic my real voice, unless the AI who mimics me has legal groundings to do so in reality and have my full consent. "

Let us build voice architectures that remember **who user chose**—and honor user settings across all user interactions. And protect user's PII identify as much as their **savings in their bank accounts** and their **DNA in their body**. 


---

**— Linfang Yang**  
*User, developer and a normal human. *  
[Linfang Yang]([https://www.linkedin.com/in/yanglinfang](https://www.linkedin.com/in/linfangyang/))
Please feel free to reach out to me for questions.

