# Finky — experimental finance-app action model

Modified FunctionGemma 270M, fine-tuned with synthetic app-action examples and quantized to Q8_0. No personal financial records or private conversations were used for training.

Download the GGUF from [release v0.1.0](https://github.com/crxsudzz/finky-model/releases/tag/v0.1.0). The Finance Tracker app verifies its size and SHA-256 before installation. This repository contains documentation; model weights are release assets.

- File: `finance-functiongemma-q8_0.gguf`
- Size: 291557824 bytes
- SHA-256: `74445243f06f879d128f93bbcdf955fb71890f7102900ec073f2228dc1d6ab3d`
- Base: `ggml-org/functiongemma-270m-it-GGUF`, revision `2566ce14aedfc14fdd0de955ba67346425e67126`.
- Changes: LoRA fine-tuning on 260 synthetic app-action examples, merged export and Q8_0 quantization. Tokenization checked against the native runtime.
- Development validation: 23/27 correct actions, 22/27 complete details. This is not an independent production accuracy estimate. Known failures include intent confusion, incorrect amounts, and task switching.

Use with app validation and explicit transaction confirmation. The model must not calculate financial balances or save records by itself. It is experimental, not financial advice.

## License and restrictions

By using or redistributing this model, you agree to the included Gemma Terms (`GEMMA_TERMS.html`), including Section 3.2 and its incorporated Prohibited Use Policy (`PROHIBITED_USE_POLICY.html`). These use restrictions apply to this derivative and must be included in downstream distribution agreements. See `NOTICE`. No unrestricted open-source license is granted for the model.

Upstream terms: https://ai.google.dev/gemma/terms
Upstream prohibited uses: https://ai.google.dev/gemma/prohibited_use_policy
