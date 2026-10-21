# Finky — experimental finance-app action model

Modified FunctionGemma 270M, fine-tuned with synthetic app-action examples and quantized to Q8_0. No personal financial records or private conversations were used for training.

The current testing release is [v0.2.0-rc.1](https://github.com/crxsudzz/finky-model/releases/tag/v0.2.0-rc.1). It is an experimental receipt/chat candidate, not a production-quality finance assistant. [v0.1.0](https://github.com/crxsudzz/finky-model/releases/tag/v0.1.0) remains available for rollback.

- File: `finance-functiongemma-q8_0.gguf`
- Size: 291557824 bytes
- SHA-256: `f43bac11359d1dae0ca793e08e22b6262e4d5c06a613443b990aa70c35bb1a7a`
- Base: `ggml-org/functiongemma-270m-it-GGUF`, revision `2566ce14aedfc14fdd0de955ba67346425e67126`.
- Training: continued the synthetic app-action adapter with 400 local LoRA steps (240 + 160), mixing 180 synthetic receipt examples with 260 existing synthetic chat examples. The follow-up weighted the chat examples twice. Exported and quantized to Q8_0; native tokenization checked.
- Development results: 24/27 complete chat cases. Re-scoring the saved candidate receipt output through the updated app validator/matcher produced 22/36 completely correct receipts and 36/36 correct account decisions (including appropriate unknown/ambiguous outcomes). These are synthetic development checks, not independent real-world accuracy estimates.
- Known limitations: the candidate did not meet the original receipt-completeness gate. Classification, amounts, dates, names and conversational intent can still be wrong. Guided parsing and required review remain essential.

## App updates

`manifest.json` advertises the compatible testing release, version, minimum app build, size and SHA-256. Finance Tracker build 3 or newer checks this metadata in AI settings and offers an update. Downloaded files are verified before replacing the model. Opening Chat does not download models or run background AI. App financial data is separate from model files.

The model interprets app topics and proposes actions. The app resolves enrolled accounts, calculates financial figures and requires explicit confirmation before saving. No personal financial records, receipt photos or private conversations were used in this training or release.

## License and restrictions

By using or redistributing this model, you agree to the included Gemma Terms (`GEMMA_TERMS.html`), including Section 3.2 and its incorporated Prohibited Use Policy (`PROHIBITED_USE_POLICY.html`). These use restrictions apply to this derivative and must be included in downstream distribution agreements. See `NOTICE`. No unrestricted open-source license is granted for the model.

Upstream terms: https://ai.google.dev/gemma/terms
Upstream prohibited uses: https://ai.google.dev/gemma/prohibited_use_policy
