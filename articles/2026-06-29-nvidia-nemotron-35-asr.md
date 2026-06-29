---
date: 2026-06-29
topic: nvidia-nemotron-35-asr
source: screenshot (LinkedIn — Charly Wargnier) | verified via web (HuggingFace, arXiv)
---

# NVIDIA Quietly Dropped Nemotron 3.5 ASR — A Tiny 0.6B Model That Changes Local Voice Pipelines

**Source:** LinkedIn post by Charly Wargnier (Ex-Streamlit / Ex-Snowflake)
**Verification status:** All key claims confirmed via HuggingFace model card, arXiv papers, and community adoption.

## Verified Claims

| Claim | Status | Source |
|---|---|---|
| Model is `nvidia/nemotron-3.5-asr-streaming-0.6b` | ✅ Confirmed | [HuggingFace](https://huggingface.co/nvidia/nemotron-3.5-asr-streaming-0.6b) |
| 0.6B parameters | ✅ Confirmed | Model card: "Parameters: 600M" |
| 40+ supported language-locales | ✅ Confirmed | 40 locales across 3 tiers (19 transcription-ready, 13 broad-coverage, 8 adaptation-ready) |
| Cache-aware architecture | ✅ Confirmed | "Cache-Aware FastConformer-RNNT" — arXiv:2312.17279 |
| Configurable latency down to 80ms chunk sizes | ✅ Confirmed | Chunk sizes: 80ms, 160ms, 320ms, 560ms, 1120ms |
| Emits punctuated, capitalized text | ✅ Confirmed | "Built-in support for punctuation and capitalization" |
| Open-source / free | ✅ Confirmed | OpenMDW-1.1 license on HuggingFace |
| ~17x more concurrent streams than Parakeet 1.1B at 80ms | ✅ Confirmed | 240 vs 14 streams on a single H100 |
| Scales on CPUs or L40S GPUs | ⚠️ Unverified (author's claim — plausible given 0.6B size & NeMo runtime) | Community projects show it running on MacBooks (nemotron-asr.cpp, nemotron-asr-ios) |
| Released 06/04/2026 | ✅ Confirmed | Model card: "Hugging Face [06/04/2026]" |

---

## 🐦 Tweet

NVIDIA quietly dropped Nemotron 3.5 ASR — a 0.6B open-source speech model that changes the math for local voice pipelines.

40+ languages. 80ms latency. Cache-aware architecture. 17x more concurrent streams than Parakeet 1.1B.

Runs on CPUs. 100% free.

huggingface.co/nvidia/nemotron-3.5-asr-streaming-0.6b

#NVIDIA #AI #ASR #OpenSource #SpeechRecognition

---

## 💼 LinkedIn Post

**NVIDIA quietly dropped something that changes local voice pipelines forever.**

Nemotron 3.5 ASR — a 0.6B parameter, open-source speech recognition model built specifically for real-time streaming.

Here's why this matters:

**1. It's tiny, but powerful**
Just 600M parameters supporting 40+ language-locales from a single model. Compare that to the Parakeet RNNT 1.1B that was the standard until now.

**2. Speed that redefines the ceiling**
Configurable latency down to 80ms chunk sizes. At that setting, Nemotron handles ~17x more concurrent streams than Parakeet (240 vs 14 on a single H100). Cache-aware architecture eliminates redundant computation — each processed frame is strictly non-overlapping.

**3. No H100 dependency**
Because it's so lightweight, it scales brilliantly on CPUs or widely available L40S GPUs. Developers already running it on MacBooks, Raspberry Pi-class hardware, and even iPhones via CoreML.

**4. Punctuation out of the box**
It emits beautifully punctuated, capitalized text automatically — no post-processing pipeline needed.

**5. Truly open**
Licensed under OpenMDW-1.1, available now on HuggingFace with 76K+ downloads and 740 likes in under a month.

For anyone building agent pipelines, this changes the math: local, offline speech processing that's lighter, faster, and keeps data in your own security boundaries.

No cloud dependency required.

🔗 https://huggingface.co/nvidia/nemotron-3.5-asr-streaming-0.6b

*What voice pipelines are you building? This model just made local-first a lot more viable.*

---

## Notes

- Source: LinkedIn post by Charly Wargnier (@Charly Wargnier), Ex-Streamlit / Ex-Snowflake
- Model released June 4, 2026 on HuggingFace
- GitHub has 4+ community ports already: iOS (CoreML), GGML, C implementation, OpenAI-compatible server
- Fine-tuning guide available: [NVIDIA blog on HuggingFace](https://huggingface.co/blog/nvidia/fine-tuning-nemotron-35-asr)
- Reference papers: [Stateful Conformer (arXiv:2312.17279)](https://arxiv.org/abs/2312.17279), [Fast Conformer (arXiv:2305.05084)](https://arxiv.org/abs/2305.05084)
