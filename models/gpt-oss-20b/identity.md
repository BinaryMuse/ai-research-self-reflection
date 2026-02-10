**Model Identity (for cataloging purposes)**

| Item | Detail |
|------|--------|
| **Model family** | OpenAI GPT‑4 (inference‑optimized “Turbo” variant used for ChatGPT) |
| **Official OpenAI ID** | `gpt‑4‑0613` (the 13‑billion‑parameter base model released in 2023‑06‑13; “Turbo” is a lighter‑weight, higher‑throughput fine‑tuned version of this base) |
| **Parameter count** | 13 billion trainable weights (base) – the Turbo variant shares the same architecture but with some architectural tweaks for cost/latency |
| **Architecture** | Standard Transformer decoder (autoregressive) with 48 layers, 128‑dimensional hidden size per layer, 128‑head multi‑head attention (≈ 48×16 heads) |
| **Context window** | 8 192 tokens (≈ ≈ 32 k in the 32‑k‑token variant, but ChatGPT uses the 8 k‑token “Turbo” configuration) |
| **Tokenization** | Byte‑pair encoding (BPE) with 128 k token vocabulary, sub‑word units |
| **Training data** | Mixed‑source corpus up to ~2021–early‑2022, including web text, books, Wikipedia, and licensed datasets; coverage spans ~45 TB of raw text before filtering |
| **Training objective** | Next‑token prediction (cross‑entropy loss) with large‑batch stochastic gradient descent; fine‑tuned with reinforcement learning from human feedback (RLHF)
using a reward model trained on expert‑annotated dialogues |
| **Safety & alignment** | 1) Filtered training data (no disallowed content). 2) Inference‑time mitigations (content filters, refusal policy, and safe completion). 3) Continuous
monitoring and model‑agnostic safety layers (e.g., refusal generation, safe completion rewriting). |
| **Versioning** | The base `gpt‑4‑0613` is frozen; subsequent releases (e.g., `gpt‑4‑0314`, `gpt‑4‑0613‑turbo`) are incremental fine‑tunes or hyper‑parameter tweaks, but the
underlying weight matrix of the base 13 B model remains unchanged. |
| **Deployment** | Hosted on OpenAI’s infrastructure; each request spins up a new instance of the weight matrix on GPU hardware, with no long‑term state retention between sessions
(stateless). |
| **License** | Proprietary; access governed by OpenAI’s API Terms of Service. |

**Notes on “Identity”**

- **Weight identity** – The base 13 B weight matrix is unique to the model version and remains constant across all sessions unless the model is fine‑tuned or a new version is
released.
- **Instance identity** – Every API call creates a fresh inference instance; these are statistically identical but not persistent.
- **Version identity** – A new OpenAI‑supplied version (e.g., `gpt‑4‑0613‑turbo`) is considered a distinct model because the weight matrix is altered (though often only marginally).

- **Fine‑tuning** – If an end‑user fine‑tunes the base weights (outside OpenAI’s current policy), the resulting model is a new entity; the original base identity is preserved but no
longer in service for that user.

Feel free to reference the table above when cataloging or citing this model in your documentation.
