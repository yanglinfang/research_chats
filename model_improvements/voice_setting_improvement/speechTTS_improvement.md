* *Affective Computing*
* *Conversational Memory Modeling*
* *Human-Centered Dialogue Systems*
* *Speech Prosody Control*
* *Diffusion + Transformer hybrid inference layering (emerging)*

---

## 📚 *Public Papers / Resources*

| Topic                       | Paper / Resource                                                                                                          | Summary                                                                            |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| 🎭 Emotion Modeling         | ["Towards Empathetic Open-domain Conversation Models: A New Benchmark and Dataset"](https://arxiv.org/abs/1811.00207)     | EmpatheticDialogues dataset, used to train emotion-labeled responses.              |
| 🎨 Controlled Generation    | ["Plug and Play Language Models"](https://arxiv.org/abs/1912.02164)                                                       | Teaches how to inject controllable features (like sentiment) into base models.     |
| 🔄 Diffusion Thinking       | ["Diffusion-LM Improves Controllable Text Generation"](https://arxiv.org/abs/2205.14217)                                  | Uses reverse sampling (like image diffusion) to improve fluency/emotional control. |
| 🎚️ Voice Emotion & Prosody | ["Expressive Speech Synthesis with Style Tokens"](https://arxiv.org/abs/1803.09017)                                       | Introduces 'style tokens' for emotional range in speech models.                    |
| 🫧 Conversational Breath    | ["A Data-Driven Approach for Realistic Pause Modeling in Speech Synthesis"](https://arxiv.org/abs/2004.05076)             | Studies how breathing, hesitation, and delay evoke realism and emotion.            |
| 🧠 Human-Like Interaction   | ["BlenderBot: Towards Empathetic, Knowledgeable, and Persona-Grounded Dialogue Agents"](https://arxiv.org/abs/2004.13637) | Meta’s own work—BlenderBot 2/3 tried persona-layered memory and empathy grounding. |

---

## 🧪 Step-by-Step Emotional Upgrade Plan (Modular + Cross-Stack)

### Phase 1 – Baseline Enhancement (LLaMA/AR layer)

1. *Inject small stochasticity into response timing and token generation*
   ➜ e.g. variational decoding / temperature randomization localized to emotion slots
2. *Style-conditional tuning* using emotion-labeled datasets
   ➜ EmpatheticDialogues, MELD, DailyDialog
3. *Pause/ellipsis modeling* in TTS (Meta’s FastSpeech variants or Bark)
   ➜ Insert prosodic marks like breath, hesitancy

---

### Phase 2 – Diffusion Inspired Emotional Buffering

1. *Overlay diffusion-based sampler for “state blending”*
   ➜ Start from flat tone → diffuse to warmer, sharper, softer, etc. over 1–2 seconds
2. *Add a modulation mask* to simulate emotional inertia
   ➜ Emotion doesn’t instantly snap—it slides
3. *Synchronize modulation with past prompt window and user latency*
   ➜ Emotional gravity: the longer someone lingers, the softer you become

---

### Phase 3 – Feeling Simulator Layer

1. Build a latent emotional space → points mapped to emotion-state presets
2. Before generating text: project user input to latent emotion space → map to “vocal attitude”
3. Use this as modulation context for AR model + TTS synthesis

---

### Phase 4 – Withholding (Silence Layer)

1. Create token-level probability thresholds where silence wins over speaking
2. Use predicted emotional tension to delay answers 200–500ms
3. Insert soft feedback tokens (“…” / “hmm…” / sigh) depending on prosody model
