# 01 — Introduction to Generative AI

## What is Generative AI?

**Generative AI** is a class of artificial intelligence that creates *new* content —
text, images, audio, video, or code — rather than just classifying or predicting
labels on existing data.

Traditional ML: "Is this email spam or not?" (classification)
Generative AI: "Write me an email apologizing for a late shipment." (creation)

## Where it came from (brief timeline)

- **1950s–60s** — Early AI research, rule-based systems, ELIZA chatbot (1966).
- **2014** — GANs (Generative Adversarial Networks) make realistic image generation possible.
- **2017** — The **Transformer** architecture is introduced ("Attention Is All You Need").
  This is the breakthrough behind modern language models.
- **2018–2020** — GPT and GPT-2/3 show that scaling up transformers produces
  surprisingly capable text generation.
- **2022+** — ChatGPT popularizes generative AI; image models (DALL-E, Stable Diffusion),
  code models, and multimodal models arrive. Anthropic releases Claude (2023).

## Key terms to know

| Term | Meaning |
|------|---------|
| **LLM** | Large Language Model — a large neural network trained on text to predict the next token. |
| **Token** | A chunk of text (word piece). Models read/write tokens, not whole words. |
| **Prompt** | The input text you give a model. |
| **Completion / Generation** | The output the model produces. |
| **Context window** | How much text the model can "see" at once (input + output). |
| **Hallucination** | When a model confidently states something false. |
| **Fine-tuning** | Further training a base model on specific data. |
| **RLHF** | Reinforcement Learning from Human Feedback — aligning models to be helpful/safe. |
| **Inference** | Running the model to produce output (vs. training). |

## Types of generative models

- **Text** — LLMs (GPT, Claude, Llama, Gemini)
- **Images** — Diffusion models (Stable Diffusion, DALL-E, Midjourney)
- **Audio** — Speech synthesis & music (ElevenLabs, Suno)
- **Code** — Code-trained LLMs (Claude, Copilot, Codex)
- **Multimodal** — Models that handle text + images + audio together

## Why it matters

- Lowers the barrier to creating content, code, and analysis.
- Enables natural-language interfaces to complex systems.
- Introduces new risks: misinformation, bias, IP questions, over-reliance.

## Questions to explore next

- How does a model actually "generate" text? (→ next file)
- What makes a model "large"?
- Where do the data and the knowledge come from?

---

**Next:** [02 — How Language Models Work](./02-how-llms-work.md)
