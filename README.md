# Awesome Hugging Face Models

> A curated list of Hugging Face models for NLP, vision, audio, multimodal, embeddings, and tabular data. Clean links, clear use cases, evidence, and runnable code.

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![GitHub stars](https://img.shields.io/github/stars/JehoshuaM/awesome-huggingface-models.svg?style=social)](https://github.com/JehoshuaM/awesome-huggingface-models/stargazers)

This repo curates well-documented Hugging Face model checkpoints with clear task fit and evidence. Entries call out benchmark scope, model limits, and license constraints. Updated through October 2026.

---

## Table of Contents

- [NLP](#nlp)
  - [Large Language Models](#large-language-models)
  - [Reasoning Models](#reasoning-models)
  - [Text Classification](#text-classification)
  - [Named Entity Recognition](#named-entity-recognition)
  - [Question Answering](#question-answering)
  - [Summarization](#summarization)
  - [Translation](#translation)
  - [Code Models](#code-models)
  - [Embeddings](#embeddings)
  - [Reranking](#reranking)
- [Computer Vision](#computer-vision)
  - [Image Classification](#image-classification)
  - [Feature Extraction and Retrieval](#feature-extraction-and-retrieval)
  - [Image Generation](#image-generation)
  - [Image Editing](#image-editing)
  - [Video Generation](#video-generation)
  - [Video Editing](#video-editing)
  - [Object Detection and Grounding](#object-detection-and-grounding)
  - [Segmentation](#segmentation)
  - [Human Pose Estimation](#human-pose-estimation)
  - [Image Matting](#image-matting)
  - [Depth Estimation](#depth-estimation)
  - [Image Super-Resolution](#image-super-resolution)
  - [3D Geometry and Reconstruction](#3d-geometry-and-reconstruction)
  - [OCR and Document Parsing](#ocr-and-document-parsing)
  - [Video Understanding](#video-understanding)
- [Audio](#audio)
  - [Speech Recognition](#speech-recognition)
  - [Text-to-Speech](#text-to-speech)
  - [Audio Classification](#audio-classification)
  - [Music Generation](#music-generation)
- [Multimodal](#multimodal)
  - [Vision-Language](#vision-language)
  - [Audio-Text](#audio-text)
- [Tabular Data](#tabular-data)
  - [Model Selection](#tabular-model-selection)
  - [Tabular Code](#tabular-code)
- [Featured Models](#featured-models)
- [Recommended Picks (October 2026)](#recommended-picks-october-2026)
- [Snippets](#snippets)
- [Standalone Snippet Files](#standalone-snippet-files)
- [Common Mistakes](#common-mistakes)
- [Contributing](#contributing)
- [License](#license)

---

## NLP

### Large Language Models

| Model | Description | Size |
|-------|-------------|------|
| [openai/gpt-oss-120b](https://huggingface.co/openai/gpt-oss-120b) | General instruction following, tool use, and reasoning when multi-GPU/high-memory inference is available; Apache-2.0 | 117B |
| [openai/gpt-oss-20b](https://huggingface.co/openai/gpt-oss-20b) | Smaller open-weight instruction/reasoning option; quantization and context length determine local hardware fit | 21B |
| [deepseek-ai/DeepSeek-V3.2](https://huggingface.co/deepseek-ai/DeepSeek-V3.2) | General assistant and tool-use workflows; evaluate agent success and latency on your own tool stack | 671B MoE |
| [moonshotai/Kimi-K2-Instruct](https://huggingface.co/moonshotai/Kimi-K2-Instruct) | General instruction model for long-form generation and tool-use experiments; high serving cost | 1T MoE / 32B active |
| [zai-org/GLM-4.6](https://huggingface.co/zai-org/GLM-4.6) | General instruction, coding, and tool-use tasks; compare benchmark settings and runtime before selection | 355B MoE |
| [Qwen/Qwen3-235B-A22B-Instruct-2507](https://huggingface.co/Qwen/Qwen3-235B-A22B-Instruct-2507) | High-capacity multilingual generation and tool use; Apache-2.0, but multi-GPU serving required for practical throughput | 235B MoE / 22B active |
| [Qwen/Qwen3-30B-A3B-Instruct-2507](https://huggingface.co/Qwen/Qwen3-30B-A3B-Instruct-2507) | General multilingual assistant and tool-use model; actual memory fit depends on quantization, context, and runtime | 30B MoE / 3B active |
| [Qwen/Qwen3-32B](https://huggingface.co/Qwen/Qwen3-32B) | Dense multilingual instruction model for general reasoning and structured generation; Apache-2.0 | 32B |
| [meta-llama/Llama-4-Scout-17B-16E-Instruct](https://huggingface.co/meta-llama/Llama-4-Scout-17B-16E-Instruct) | Text and image instruction following with long-context support; gated Meta Llama license applies | 17B MoE |
| [meta-llama/Llama-4-Maverick-17B-128E-Instruct](https://huggingface.co/meta-llama/Llama-4-Maverick-17B-128E-Instruct) | Larger Llama 4 multimodal/assistant option; check the model card and serving requirements | 17B MoE |
| [meta-llama/Meta-Llama-3.3-70B-Instruct](https://huggingface.co/meta-llama/Meta-Llama-3.3-70B-Instruct) | General text assistant for structured generation and instruction tasks; gated Meta Llama license applies | 70B |
| [meta-llama/Llama-3.1-8B-Instruct](https://huggingface.co/meta-llama/Llama-3.1-8B-Instruct) | Smaller text assistant for fine-tuning and constrained deployments; validate quantized output quality | 8B |
| [google/gemma-3-27b-it](https://huggingface.co/google/gemma-3-27b-it) | Higher-capacity text/image instruction following; Gemma terms apply | 27B |
| [google/gemma-3-9b-it](https://huggingface.co/google/gemma-3-9b-it) | Mid-sized text/image instruction model for local or hosted inference after hardware validation | 9B |
| [google/gemma-3n-E4B-it](https://huggingface.co/google/gemma-3n-E4B-it) | On-device-oriented multimodal assistant; benchmark on the target mobile/edge runtime | ~4B active |
| [mistralai/Mistral-Small-3.1-24B-Instruct-2503](https://huggingface.co/mistralai/Mistral-Small-3.1-24B-Instruct-2503) | Text and image instruction following in a mid-sized checkpoint; compare with current VLMs for visual tasks | 24B |
| [mistralai/Mistral-7B-Instruct-v0.3](https://huggingface.co/mistralai/Mistral-7B-Instruct-v0.3) | Compact text instruction baseline for fine-tuning or constrained inference |
| [microsoft/Phi-4](https://huggingface.co/microsoft/Phi-4) | Smaller dense model for math/science and general text tasks; evaluate domain and license fit | 14B |
| [CohereLabs/aya-expanse-8b](https://huggingface.co/CohereLabs/aya-expanse-8b) | Multilingual chat and generation in 23 languages, including Indonesian; research and non-commercial use only (CC-BY-NC-4.0) | 8B |

---

### Reasoning Models

| Model | Description | Size |
|-------|-------------|------|
| [deepseek-ai/DeepSeek-R1-0528](https://huggingface.co/deepseek-ai/DeepSeek-R1-0528) | Deliberative math, coding, and multi-step reasoning; compare against current baselines on your prompt set | 671B MoE |
| [Qwen/Qwen3-235B-A22B-Thinking-2507](https://huggingface.co/Qwen/Qwen3-235B-A22B-Thinking-2507) | High-capacity reasoning when latency and multi-GPU inference are acceptable | 235B MoE |
| [Qwen/Qwen3-30B-A3B-Thinking-2507](https://huggingface.co/Qwen/Qwen3-30B-A3B-Thinking-2507) | Lower-active-parameter reasoning model; hardware fit depends on quantization, context, and serving stack | 30B MoE |
| [microsoft/Phi-4-reasoning-plus](https://huggingface.co/microsoft/Phi-4-reasoning-plus) | Smaller reasoning-oriented checkpoint for math/science prompts; verify task-specific accuracy before deployment | 14B |

---

### Text Classification

| Model | Use Case |
|-------|---------|
| [cardiffnlp/twitter-roberta-base-sentiment-latest](https://huggingface.co/cardiffnlp/twitter-roberta-base-sentiment-latest) | Sentiment analysis |
| [facebook/bart-large-mnli](https://huggingface.co/facebook/bart-large-mnli) | Zero-shot classification |
| [unitary/toxic-bert](https://huggingface.co/unitary/toxic-bert) | Toxicity detection |
| [ProsusAI/finbert](https://huggingface.co/ProsusAI/finbert) | Financial sentiment |

---

### Named Entity Recognition

| Model | Language |
|-------|----------|
| [dbmdz/bert-large-cased-finetuned-conll03-english](https://huggingface.co/dbmdz/bert-large-cased-finetuned-conll03-english) | English CoNLL-2003 newswire entities |
| [FacebookAI/xlm-roberta-large-finetuned-conll03-english](https://huggingface.co/FacebookAI/xlm-roberta-large-finetuned-conll03-english) | English CoNLL-2003 fine-tune (the backbone is multilingual; this checkpoint is not multilingual NER) |
| [dslim/bert-base-NER](https://huggingface.co/dslim/bert-base-NER) | Lightweight English CoNLL-2003 PER/ORG/LOC/MISC tagging |

---

### Question Answering

| Model | Best For |
|-------|---------|
| [deepset/roberta-base-squad2](https://huggingface.co/deepset/roberta-base-squad2) | Extractive QA, English, strong baseline |
| [deepset/deberta-v3-base-squad2](https://huggingface.co/deepset/deberta-v3-base-squad2) | DeBERTa-v3 backbone, better long-context QA |

Use extractive QA when answers must be grounded in a supplied passage and the model should be able to return no answer. Use an instruction-tuned LLM for multi-document synthesis or open-ended reasoning, and evaluate factuality and citations on your own corpus.

---

### Summarization

| Model | Type |
|-------|------|
| [facebook/bart-large-cnn](https://huggingface.co/facebook/bart-large-cnn) | English CNN/DailyMail news-style summaries |
| [google/pegasus-xsum](https://huggingface.co/google/pegasus-xsum) | Short, highly abstractive English summaries in the XSum style |
| [sshleifer/distilbart-cnn-12-6](https://huggingface.co/sshleifer/distilbart-cnn-12-6) | Lower-latency CNN/DailyMail-style English summaries; check quality on longer or specialized documents |
| [allenai/led-large-16384-arxiv](https://huggingface.co/allenai/led-large-16384-arxiv) | Long-input scientific-paper summarization, fine-tuned on arXiv papers (English, up to 16K tokens); not a general-purpose current SOTA claim |

These checkpoints are task- and dataset-specific. For long scientific papers, see [LED arXiv](https://huggingface.co/allenai/led-large-16384-arxiv) below; for flexible formats, compare an instruction-tuned LLM using a factuality-aware evaluation set.

---

### Translation

| Model | Languages |
|-------|----------|
| [facebook/m2m100_418M](https://huggingface.co/facebook/m2m100_418M) | Direct multilingual translation among 100 languages; quality varies by language pair |
| [google/mt5-large](https://huggingface.co/google/mt5-large) | Multilingual text-to-text base model; task-specific fine-tuning is usually required for dependable translation |
| [facebook/nllb-200-distilled-600M](https://huggingface.co/facebook/nllb-200-distilled-600M) | Lightweight translation across supported language pairs; check pair coverage and benchmark quality |
| [facebook/nllb-200-3.3B](https://huggingface.co/facebook/nllb-200-3.3B) | Larger NLLB checkpoint for supported translation pairs; model card restricts use to research and humanitarian purposes |

---

### Code Models

| Model | Best For |
|-------|---------|
| [Qwen/Qwen3-Coder-480B-A35B-Instruct](https://huggingface.co/Qwen/Qwen3-Coder-480B-A35B-Instruct) | Large-scale code generation, repository-level tasks, and tool use; hardware and context length determine serving cost |
| [Qwen/Qwen3-Coder-30B-A3B-Instruct](https://huggingface.co/Qwen/Qwen3-Coder-30B-A3B-Instruct) | Smaller code assistant for local or hosted inference; memory depends on precision, context, and runtime |
| [Qwen/Qwen2.5-Coder-32B-Instruct](https://huggingface.co/Qwen/Qwen2.5-Coder-32B-Instruct) | Instruction-based code generation and editing across supported programming languages |
| [bigcode/starcoder2-15b-instruct-v2.0](https://huggingface.co/bigcode/starcoder2-15b-instruct-v2.0) | Code completion and infilling; not an agentic chat model |
| [microsoft/CodeBERT-base](https://huggingface.co/microsoft/CodeBERT-base) | Encoder for code search, similarity, and retrieval after task-specific scoring; not a code-generation assistant |

---

### Embeddings

| Model | Best For |
|-------|---------|
| [Alibaba-NLP/gte-modernbert-base](https://huggingface.co/Alibaba-NLP/gte-modernbert-base) | Fast, ModernBERT-based, long context, English |
| [nomic-ai/nomic-embed-text-v2-moe](https://huggingface.co/nomic-ai/nomic-embed-text-v2-moe) | Multilingual MoE, ~100 languages, open weights |
| [BAAI/bge-multilingual-gemma2](https://huggingface.co/BAAI/bge-multilingual-gemma2) | LLM-based, strong multilingual retrieval |
| [BAAI/bge-m3](https://huggingface.co/BAAI/bge-m3) | Multilingual dense, sparse, and multi-vector first-stage retrieval for long documents (up to 8K tokens); not a reranker |
| [intfloat/multilingual-e5-large-instruct](https://huggingface.co/intfloat/multilingual-e5-large-instruct) | Solid multilingual baseline |
| [sentence-transformers/all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2) | Tiny, fast, still great for cheap RAG |
| [dunzhang/stella_en_v5_instruct](https://huggingface.co/dunzhang/stella_en_v5_instruct) | English, instruction-tuned, top MTEB scores |
| [Alibaba-NLP/gte-Qwen2-1.5B-instruct](https://huggingface.co/Alibaba-NLP/gte-Qwen2-1.5B-instruct) | Longer-context multilingual embeddings; use query instructions and compare the card's dated MTEB/C-MTEB scores against your language/domain |

Choose an embedding model using language, document length, hardware, and retrieval evaluation. MiniLM is a compact English option; GTE-Qwen2-1.5B adds multilingual long-context embeddings at higher cost. BGE-M3 can produce dense, sparse, and multi-vector retrieval representations. Model-card benchmark scores are not a substitute for evaluation on your own corpus.

---

### Reranking

| Model | Best For |
|-------|---------|
| [BAAI/bge-reranker-v2-m3](https://huggingface.co/BAAI/bge-reranker-v2-m3) | Multilingual cross-encoder relevance scoring after candidate retrieval; pairwise inference cost grows with candidate count |
| [Alibaba-NLP/gte-multilingual-reranker-base](https://huggingface.co/Alibaba-NLP/gte-multilingual-reranker-base) | Cross-encoder reranking for multilingual query-document candidates; validate on the target language |
| [nvidia/nv-rerankqa-mistral4b-v3](https://huggingface.co/nvidia/nv-rerankqa-mistral4b-v3) | Higher-compute question-answer relevance reranking when latency budget allows |
| [mixedbread-ai/mxbai-rerank-large-v1](https://huggingface.co/mixedbread-ai/mxbai-rerank-large-v1) | English query-document reranking |

Rerankers reorder retrieved candidates; they cannot recover documents that retrieval missed. Measure retrieval recall, ranking quality, and latency together before choosing a candidate count.

---

## Computer Vision

Choose the model by the output you need. A supervised classifier predicts from its trained label set; a vision-language model ranks text labels without training; a self-supervised encoder needs a probe or task head. ImageNet scores below are reference results for the named checkpoint and do not predict accuracy on a different domain.

### Image Classification

| Model | Type and intended use | Evidence and limits |
|-------|----------------------|--------------------|
| [EVA-02 Small](https://huggingface.co/timm/eva02_small_patch14_336.mim_in22k_ft_in1k) / [Large](https://huggingface.co/timm/eva02_large_patch14_448.mim_m38m_ft_in22k_in1k) | Supervised ImageNet-1K classifier; use Small for a practical high-accuracy starting point and Large when inference cost is acceptable. Both can be fine-tuned for a new fixed label set. | The exact checkpoints report about 85.7% top-1 at 336px and 90.1% at 448px on ImageNet-1K validation. MIT weights; the Large checkpoint has 305M parameters. See the [EVA-02 paper](https://arxiv.org/abs/2303.11331) and [timm model docs](https://huggingface.co/docs/timm/main/models/eva). |
| [ConvNeXt Base](https://huggingface.co/timm/convnext_base.fb_in22k_ft_in1k) | Strong convolutional alternative for supervised classification and transfer learning when you want a non-transformer backbone. | The exact Hub checkpoint reports 86.3% ImageNet-1K top-1 at 288px; Apache-2.0. This is an established CVPR 2022 model and a useful CNN reference, not the newest architecture. [Paper](https://arxiv.org/abs/2201.03545). |
| [RepViT M2.3](https://huggingface.co/timm/repvit_m2_3.dist_300e_in1k) | Efficient supervised classifier for mobile and edge workloads; use when latency and model size matter more than the highest ImageNet score. | The 300-epoch checkpoint reports 83.5% ImageNet-1K top-1 at 224px, 23.7M parameters, and 4.6 GMAC; Apache-2.0. Paper and official `timm` docs report mobile-oriented structural re-parameterization. [CVPR 2024 paper](https://arxiv.org/abs/2307.09283) · [docs](https://huggingface.co/docs/timm/main/models/repvit). |
| [SigLIP 2 Base](https://huggingface.co/google/siglip2-base-patch16-224) | Zero-shot classification by comparing an image with candidate class names or descriptions; useful when the label set changes or labeled training examples are unavailable. | The paper reports 78.2% zero-shot ImageNet-1K top-1 at 224px. Apache-2.0; multilingual pretraining does not guarantee equal accuracy in every language. Prompt wording and candidate set affect results, and scores are not calibrated probabilities. [Paper](https://arxiv.org/abs/2502.14786) · [Transformers docs](https://huggingface.co/docs/transformers/en/model_doc/siglip2). |
| [MobileCLIP2-S2](https://huggingface.co/apple/MobileCLIP2-S2) | Mobile-oriented image-text model for prompt-based zero-shot labels and image-text retrieval. Choose it for lower compute budgets, not as a fixed-label classifier. | Apple reports 77.2% zero-shot ImageNet-1K top-1 and 64.1 average over 38 datasets for this exact variant. The weights use Apple's research/academic non-commercial terms; the MIT code license does not change the model-weight terms. [TMLR 2025 paper](https://arxiv.org/abs/2508.20691) · [official implementation and results](https://github.com/apple-aiml-research/ml-mobileclip). |
| [Perception Encoder Core L14](https://huggingface.co/facebook/PE-Core-L14-336) | Prompt-based zero-shot classification for changing labels, including robustness-oriented evaluation; score the image against concise candidate descriptions. | The NeurIPS 2025 paper/card reports 83.5% ImageNet-1K, 77.9% ImageNet-v2, 89.0% ImageNet-A, and 84.7% ObjectNet. Apache-2.0. CLIP-style scores are relative to the prompt set, not calibrated probabilities. Use Meta's official `perception_models` package; this checkpoint does not have a documented Transformers image-classification loader. [Paper](https://papers.neurips.cc/paper_files/paper/2025/file/57bc0a850255e2041341bf74c7e2b9fa-Paper-Conference.pdf) · [official code](https://github.com/facebookresearch/perception_models). |
| [TransNeXt Base 384](https://huggingface.co/DaiShiResearch/transnext-base-384-1k-ft-1k) | Fixed-label ImageNet-1K classification when a high-resolution hierarchical vision transformer is acceptable; fine-tune for a new closed label set. | The exact 384px checkpoint reports 86.2% ImageNet-1K top-1, 77.0% ImageNet-v2, 61.6% ImageNet-A, 57.7% ImageNet-R, and 44.7% Sketch. Apache-2.0. Loading requires the project's source registration and an older pinned `timm` stack, so it is less plug-and-play than the Transformers/timm checkpoints above. [CVPR 2024 paper](https://openaccess.thecvf.com/content/CVPR2024/html/Shi_TransNeXt_Robust_Foveal_Visual_Perception_for_Vision_Transformers_CVPR_2024_paper.html) · [official classifier instructions](https://github.com/DaiShiResearch/TransNeXt/blob/main/classification/README.md). |
| [BioCLIP-2](https://huggingface.co/imageomics/bioclip-2) | Domain-specific zero-shot species classification for biodiversity images; compare candidate taxa or species descriptions, not arbitrary generic labels. | The NeurIPS 2025 paper reports a mean 55.6 across ten zero-shot species benchmarks versus 37.6 for BioCLIP. Do not conflate this with the broader 57.5 biology score, which combines different evaluation protocols. MIT. [Paper](https://proceedings.neurips.cc/paper_files/paper/2025/file/94da80cbfe870c1db958c88a8a27018c-Paper-Conference.pdf) · [official code](https://github.com/Imageomics/bioclip-2). |

### Feature Extraction and Retrieval

| Model | Best use |
|-------|----------|
| [facebook/dinov3-vitb16-pretrain-lvd1689m](https://huggingface.co/facebook/dinov3-vitb16-pretrain-lvd1689m) | Frozen visual features for nearest-neighbor search or a linear/logistic-regression probe on your labeled images. This is not a ready-made class predictor. Its ViT-B results include ImageNet-ReaL, ImageNet-R, and ObjectNet protocols; do not attribute the paper's ViT-7B headline to this checkpoint. Gated access and Meta's DINOv3 license apply. [Paper](https://arxiv.org/abs/2508.10104) · [Transformers docs](https://huggingface.co/docs/transformers/model_doc/dinov3). |
| [facebook/dinov2-base](https://huggingface.co/facebook/dinov2-base) | Frozen visual features for nearest-neighbor retrieval, linear probes, or downstream segmentation; add a task head for predictions. [Paper](https://arxiv.org/abs/2304.07193). |
| [google/siglip2-so400m-patch16-naflex](https://huggingface.co/google/siglip2-so400m-patch16-naflex) | Image-text embeddings for semantic retrieval and variable-aspect-ratio images; compare normalized image and text embeddings. It can also rank candidate class descriptions, but is not a calibrated classifier. [Model docs](https://huggingface.co/docs/transformers/en/model_doc/siglip2). |

### Image Generation

| Model | Description |
|-------|-------------|
| [black-forest-labs/FLUX.1-dev](https://huggingface.co/black-forest-labs/FLUX.1-dev) | High-quality open-weight text-to-image; gated and non-commercial license, large hardware footprint. Avoid blanket “best” claims; results vary by prompt and evaluation set. |
| [black-forest-labs/FLUX.1-schnell](https://huggingface.co/black-forest-labs/FLUX.1-schnell) | Fast 1–4 step generation for drafts and iteration; Apache-2.0 license on the Hub card |
| [stabilityai/stable-diffusion-3.5-large](https://huggingface.co/stabilityai/stable-diffusion-3.5-large) | High-capacity text-to-image for detailed prompts; review Stability AI Community License terms before commercial use |
| [stabilityai/stable-diffusion-3.5-medium](https://huggingface.co/stabilityai/stable-diffusion-3.5-medium) | Smaller SD3.5 option when memory is constrained; quality and hardware needs depend on precision/runtime |
| [Qwen/Qwen-Image-2512](https://huggingface.co/Qwen/Qwen-Image-2512) | Text-to-image generation with a documented strength in rendering text and complex layouts. Apache-2.0. The 2512 variant has no separate peer-reviewed paper; the linked report covers the Qwen-Image family, so treat variant-specific results as model-card evidence. [Family report](https://arxiv.org/abs/2508.02324). |

### Image Editing

| Model | Description |
|-------|-------------|
| [black-forest-labs/FLUX.1-Kontext-dev](https://huggingface.co/black-forest-labs/FLUX.1-Kontext-dev) | Reference-image editing with text instructions; identity and object consistency can vary, and the dev weights are non-commercial |
| [Qwen/Qwen-Image-Edit-2511](https://huggingface.co/Qwen/Qwen-Image-Edit-2511) | Instruction-based single- and multi-image editing, with improvements to subject consistency and image drift. Apache-2.0. The 2511 variant has no separate paper; its model card links to the Qwen-Image family report. [Family report](https://arxiv.org/abs/2508.02324). |

### Video Generation

| Model | Description |
|-------|-------------|
| [Wan-AI/Wan2.2-TI2V-5B](https://huggingface.co/Wan-AI/Wan2.2-TI2V-5B) | Text- or image-conditioned 720p video generation in a smaller 5B checkpoint; check VRAM and generation speed on target hardware |
| [Wan-AI/Wan2.2-T2V-A14B](https://huggingface.co/Wan-AI/Wan2.2-T2V-A14B) | Higher-capacity text-to-video generation; substantial compute/storage requirements |
| [Lightricks/LTX-2.5](https://huggingface.co/Lightricks/LTX-2.5) | Current open-weight text/image-to-video with synchronized audio; competitive in the open-weight human-preference leaderboard, but the linked paper evaluates the earlier LTX-2 version. Gated community license and large storage/GPU needs. |

### Video Editing

| Model | Use case |
|-------|----------|
| [Wan-AI/Wan2.1-VACE-14B](https://huggingface.co/Wan-AI/Wan2.1-VACE-14B) | Video-to-video editing, masked inpainting/outpainting, reference-to-video, and pose/depth/layout control. Apache-2.0. The 14B checkpoint is large; full V2V workflows use the [official VACE repo](https://github.com/ali-vilab/VACE), preprocessing, and annotators. Its ICCV 2025 paper reports parity with specialist systems on selected VACE benchmark tasks, not universal SOTA. [Paper](https://arxiv.org/abs/2503.07598). |

### Object Detection and Grounding

| Model | Task and evidence |
|-------|------------------|
| [ustc-community/dfine-xlarge-coco](https://huggingface.co/ustc-community/dfine-xlarge-coco) | Fixed-label COCO object detection. The paper reports 55.8 COCO AP and 78 FPS on an NVIDIA T4 for the X variant; hardware-specific figures. Apache-2.0. Use the Transformers `DFineForObjectDetection` API, not the card's stale tokenizer example. [Docs](https://huggingface.co/docs/transformers/model_doc/d_fine) · [paper](https://arxiv.org/abs/2410.13842). |
| [PekingU/rtdetr_v2_r50vd](https://huggingface.co/PekingU/rtdetr_v2_r50vd) | Real-time, closed-set object detection for the checkpoint's trained classes. Compare latency/accuracy against models on your hardware and data. [Paper](https://arxiv.org/abs/2407.17140). |
| [IDEA-Research/GroundingDINO](https://huggingface.co/IDEA-Research/GroundingDINO) | Text-conditioned boxes for open-vocabulary localization. Prompt wording and domain shift affect recall; it is not a calibrated detector. [Paper](https://arxiv.org/abs/2303.05499). |

### Segmentation

| Model | Task and limits |
|-------|-----------------|
| [shi-labs/oneformer_coco_swin_large](https://huggingface.co/shi-labs/oneformer_coco_swin_large) | One checkpoint performs semantic, instance, or panoptic segmentation by selecting a task token. This exact checkpoint is closed-set COCO, not open-vocabulary, and uses a large Swin-L backbone. MIT. The CVPR 2023 paper evaluates the unified model against task-specific alternatives across COCO, ADE20K, and Cityscapes. [Transformers docs](https://huggingface.co/docs/transformers/model_doc/oneformer) · [paper](https://openaccess.thecvf.com/content/CVPR2023/html/Jain_OneFormer_One_Transformer_To_Rule_Universal_Image_Segmentation_CVPR_2023_paper.html). |
| [facebook/sam3](https://huggingface.co/facebook/sam3) | Promptable concept segmentation and video tracking: text prompts find all matching instances; points/boxes refine a specific mask. It is not a fixed-label detector. Gated access and Meta's custom SAM license apply. Its paper's human-comparison claims are limited to the SA-Co promptable concept segmentation benchmark. [Transformers docs](https://huggingface.co/docs/transformers/model_doc/sam3) · [paper](https://arxiv.org/abs/2511.16719). |
| [facebook/sam2.1-hiera-large](https://huggingface.co/facebook/sam2.1-hiera-large) | Prompted image/video object masks from points, boxes, or an initial mask; useful for tracking a selected object, not semantic class labeling or open-vocabulary detection. [Paper](https://arxiv.org/abs/2408.00714). |
| [nvidia/segformer-b5-finetuned-ade-640-640](https://huggingface.co/nvidia/segformer-b5-finetuned-ade-640-640) | Closed-set semantic segmentation on ADE20K labels. Fine-tune or validate before applying another label map. |

### Human Pose Estimation

| Model | Task and limits |
|-------|-----------------|
| [usyd-community/vitpose-plus-base](https://huggingface.co/usyd-community/vitpose-plus-base) | Top-down 17-keypoint COCO body pose estimation. Detect person boxes first; this checkpoint combines six dataset experts, so set `dataset_index=0` for COCO. The ViTPose++-B paper reports 77.0 AP / 82.6 AR on COCO val at 256×192 in its multi-task evaluation; do not attribute the Hub card's generic 81.1 AP headline to this exact Base checkpoint. Apache-2.0. [Transformers docs](https://huggingface.co/docs/transformers/model_doc/vitpose) · [official results](https://github.com/ViTAE-Transformer/ViTPose) · [TPAMI paper](https://arxiv.org/abs/2212.04246). |

Pose models return keypoints for supplied detections; they do not detect people, track identities across frames, or classify actions by themselves.

### Image Matting

| Model | Task and limits |
|-------|-----------------|
| [hustvl/vitmatte-base-composition-1k](https://huggingface.co/hustvl/vitmatte-base-composition-1k) | Estimates a foreground alpha matte from an RGB image and an aligned trimap; it does not automatically find the foreground or generate the trimap. The official results report SAD 20.33 on Composition-1k and 17.05 on Distinctions-646 (lower is better). **Use weights only non-commercially:** the Hub card says Apache-2.0, but the upstream Adobe Composition-1k license restricts derived ML models to non-commercial use and requires attribution. [Official results](https://github.com/hustvl/ViTMatte) · [Transformers docs](https://huggingface.co/docs/transformers/model_doc/vitmatte) · [paper](https://arxiv.org/abs/2305.15272) · [upstream dataset license](https://github.com/adobe-research/Deep_Image_Matting_Dataset/blob/main/LICENSE.md). |

### Depth Estimation

| Model | Task and limits |
|-------|-----------------|
| [depth-anything/Depth-Anything-V2-Small-hf](https://huggingface.co/depth-anything/Depth-Anything-V2-Small-hf) | Relative monocular depth for a single image. It produces a useful depth ordering/map, not calibrated metric distance. Apache-2.0; 24.8M parameters. [Transformers docs](https://huggingface.co/docs/transformers/model_doc/depth_anything_v2) · [paper](https://arxiv.org/abs/2406.09414). |

### Image Super-Resolution

| Model | Task and limits |
|-------|-----------------|
| [caidas/swin2SR-realworld-sr-x4-64-bsrgan-psnr](https://huggingface.co/caidas/swin2SR-realworld-sr-x4-64-bsrgan-psnr) | Real-world photo upscaling at 4× with the BSRGAN-PSNR checkpoint. The official repo evaluates this checkpoint on RealSRSet+5images; its paper's AIM top-five compressed-input SR result is for a different model/task and should not be reused here. Apache-2.0. Treat reconstructed fine detail as plausible, not ground truth. [Transformers docs](https://huggingface.co/docs/transformers/model_doc/swin2sr) · [official evaluation](https://github.com/mv-lab/swin2sr) · [paper](https://arxiv.org/abs/2209.11345). |

### 3D Geometry and Reconstruction

| Model | Task and limits |
|-------|-----------------|
| [facebook/VGGT-1B](https://huggingface.co/facebook/VGGT-1B) | Feed-forward multi-view geometry from several images: camera parameters, per-view depth, point maps, and optional point tracks. CVPR 2025 Best Paper; the paper evaluates camera pose, multi-view depth, dense reconstruction, and tracking. It is a 1B-parameter model with roughly 5 GB weights and practical GPU requirements. The original weights are CC-BY-NC-4.0; a separately gated [commercial checkpoint](https://huggingface.co/facebook/VGGT-1B-Commercial) has different terms. It produces camera-relative geometry, not a finished mesh, and its single-image mode was not quantitatively validated as general-purpose depth estimation. [Official code](https://github.com/facebookresearch/vggt) · [CVPR paper](https://openaccess.thecvf.com/content/CVPR2025/html/Wang_VGGT_Visual_Geometry_Grounded_Transformer_CVPR_2025_paper.html). |

### OCR and Document Parsing

| Model | Task and limits |
|-------|-----------------|
| [PaddlePaddle/PP-OCRv5_server_det](https://huggingface.co/PaddlePaddle/PP-OCRv5_server_det) + [PP-OCRv5_server_rec](https://huggingface.co/PaddlePaddle/PP-OCRv5_server_rec) | Production-oriented text-line detection plus recognition for scene text and difficult text (including handwriting, vertical and rotated lines). Apache-2.0. The documented recognition evaluation covers Chinese, Pinyin, English, and Japanese; it is not Indonesian-specific evidence. Install PaddleOCR with a compatible PaddlePaddle wheel. [Official docs](https://github.com/PaddlePaddle/PaddleOCR/blob/main/docs/version3.x/algorithm/PP-OCRv5/PP-OCRv5.en.md) · [CVPR 2026 paper](https://openaccess.thecvf.com/content/CVPR2026/html/Cui_PP-OCRv5_A_Specialized_5M-Parameter_Model_Rivaling_Billion-Parameter_Vision-Language_Models_on_OCR_Tasks_CVPR_2026_paper.html). |
| [PaddlePaddle/PaddleOCR-VL-1.6](https://huggingface.co/PaddlePaddle/PaddleOCR-VL-1.6) | Page-level document parsing: layout and reading order plus text, tables, formulas, charts, and seals. The authors report 96.33 on OmniDocBench v1.6. This is for document pages, not general scene OCR; use the PaddleOCRVL pipeline. Apache-2.0. [Docs](https://www.paddleocr.ai/main/en/version3.x/algorithm/PaddleOCR-VL/PaddleOCR-VL-1.6.html) · [paper](https://arxiv.org/abs/2606.03264). |
| [microsoft/trocr-base-printed](https://huggingface.co/microsoft/trocr-base-printed) / [microsoft/trocr-large-handwritten](https://huggingface.co/microsoft/trocr-large-handwritten) | Printed or handwritten word/line recognition after text regions have been cropped. TrOCR does not detect page layout or reading order. |

### Video Understanding

| Model | Best use and limits |
|-------|--------------------|
| [google/videoprism-base-f16r288](https://huggingface.co/google/videoprism-base-f16r288) | Video embeddings for action recognition, temporal understanding, and retrieval. The base checkpoint is an encoder; closed-set action labels need a task-specific classifier head. The text-aligned [LVT variant](https://huggingface.co/google/videoprism-lvt-base-f16r288) is the choice for text-video similarity and zero-shot label ranking. Apache-2.0. Public released weights are not identical to the paper's best model and do not lead every benchmark. [Transformers docs](https://huggingface.co/docs/transformers/model_doc/videoprism) · [ICML 2024 paper](https://arxiv.org/abs/2402.13217) · [official code/results](https://github.com/google-deepmind/videoprism). |
| [OpenGVLab/InternVideo2_5_Chat_8B](https://huggingface.co/OpenGVLab/InternVideo2_5_Chat_8B) | Long-video question answering and temporal-detail reasoning, not a fixed action classifier. The Apache-2.0 checkpoint uses custom code (`trust_remote_code=True`), decord, and FlashAttention 2; large GPU memory is needed. Published results are from the authors' technical report, so compare on your own video set. [Report](https://arxiv.org/abs/2501.12386). |

For general image/video conversations, see [Vision-Language models](#vision-language). Use task-specific detectors, segmentation, OCR, or video encoders when you need structured outputs rather than a generated description. The entries below separate closed-set recognition, open-vocabulary prompts, pixel masks, geometry, and document parsing because their outputs and evaluation protocols are different.

---

## Audio

### Speech Recognition

| Model | Description |
|-------|-------------|
| [Qwen/Qwen3-ASR-1.7B](https://huggingface.co/Qwen/Qwen3-ASR-1.7B) | Multilingual transcription and language identification across 52 listed languages/dialects, including Indonesian; authors' [report](https://arxiv.org/abs/2601.21337) evaluates open and internal benchmarks; validate local accents and noise |
| [openai/whisper-large-v3-turbo](https://huggingface.co/openai/whisper-large-v3-turbo) | Lower-latency Whisper transcription; speed/accuracy tradeoffs depend on hardware, chunking, language, and audio |
| [openai/whisper-large-v3](https://huggingface.co/openai/whisper-large-v3) | General multilingual ASR and speech translation baseline; compare language-specific error rates on your data |
| [distil-whisper/distil-large-v3](https://huggingface.co/distil-whisper/distil-large-v3) | Faster English Whisper-style transcription; not a multilingual replacement for Whisper large-v3 |
| [nvidia/parakeet-tdt-0.6b-v2](https://huggingface.co/nvidia/parakeet-tdt-0.6b-v2) | Fast English transcription; benchmark domain vocabulary, punctuation, and timestamps on target audio |
| [nvidia/canary-1b-flash](https://huggingface.co/nvidia/canary-1b-flash) | ASR and speech translation for English, German, Spanish, and French |
| [facebook/seamless-m4t-v2-large](https://huggingface.co/facebook/seamless-m4t-v2-large) | Speech/text translation across supported language pairs; check task direction and language coverage in the model card |

### Text-to-Speech

| Model | Description |
|-------|-------------|
| [microsoft/speecht5_tts](https://huggingface.co/microsoft/speecht5_tts) | Lightweight TTS, fine-tunable per speaker |
| [Qwen/Qwen3-TTS-12Hz-0.6B-CustomVoice](https://huggingface.co/Qwen/Qwen3-TTS-12Hz-0.6B-CustomVoice) | Multilingual TTS with preset voices and style instructions (10 supported languages; Indonesian is not listed); see the [technical report](https://arxiv.org/abs/2601.15621) and evaluate naturalness on target speakers |
| [Qwen/Qwen3-TTS-12Hz-0.6B-Base](https://huggingface.co/Qwen/Qwen3-TTS-12Hz-0.6B-Base) | Reference-audio voice cloning from a provided voice sample and transcript; use only with consented voice data |
| [suno/bark](https://huggingface.co/suno/bark) | Research/prototyping TTS with non-speech audio; assess intelligibility, latency, and license before deployment |
| [Sesame/csm-1b](https://huggingface.co/Sesame/csm-1b) | Conversational speech generation conditioned on dialogue context; read the model-specific license and evaluate speaker consistency |
| [nari-labs/Dia-1.6B](https://huggingface.co/nari-labs/Dia-1.6B) | Dialogue-style speech generation for research/education; not a general voice-cloning checkpoint |

### Audio Classification

| Model | Task |
|-------|------|
| [MIT/ast-finetuned-audioset-10-10-0.4593](https://huggingface.co/MIT/ast-finetuned-audioset-10-10-0.4593) | AudioSet sound-event labels; fine-tune or validate before applying to a different acoustic domain |
| [superb/wav2vec2-base-superb-er](https://huggingface.co/superb/wav2vec2-base-superb-er) | Four-class English utterance emotion classification on IEMOCAP; not general emotion recognition |

### Music Generation

| Model | Description |
|-------|-------------|
| [facebook/musicgen-large](https://huggingface.co/facebook/musicgen-large) | Research text-to-music generation from English prompts; model card restricts use to research and warns against unassessed downstream use (CC-BY-NC-4.0) |
| [facebook/musicgen-stereo-large](https://huggingface.co/facebook/musicgen-stereo-large) | Stereo text-to-music variant under the same research/non-commercial caveats; stereo output does not itself imply higher fidelity |

---

## Multimodal

### Vision-Language

| Model | Capability |
|-------|-----------|
| [Qwen/Qwen3-VL-235B-A22B-Instruct](https://huggingface.co/Qwen/Qwen3-VL-235B-A22B-Instruct) | High-capacity image/video/document reasoning; large multi-GPU serving footprint, benchmark results are model-card reported |
| [Qwen/Qwen3-VL-30B-A3B-Instruct](https://huggingface.co/Qwen/Qwen3-VL-30B-A3B-Instruct) | Lower-active-parameter image/video/document assistant; actual memory needs depend on quantization and context |
| [Qwen/Qwen3-Omni-30B-A3B-Instruct](https://huggingface.co/Qwen/Qwen3-Omni-30B-A3B-Instruct) | Unified audio/video understanding and speech/text responses; substantial runtime stack and hardware; [paper](https://arxiv.org/abs/2509.17765) reports results across 36 audio/AV benchmarks |
| [meta-llama/Llama-4-Scout-17B-16E-Instruct](https://huggingface.co/meta-llama/Llama-4-Scout-17B-16E-Instruct) | Image-plus-text assistant with long-context support; actual latency and memory depend on resolution and serving stack |
| [mistralai/Pixtral-12B-2409](https://huggingface.co/mistralai/Pixtral-12B-2409) | Image question answering, OCR-like content, and chart interpretation; evaluate document-specific accuracy |
| [mistralai/Pixtral-Large-Instruct-2411](https://huggingface.co/mistralai/Pixtral-Large-Instruct-2411) | Higher-capacity image/text reasoning when serving cost is acceptable |
| [Qwen/Qwen2.5-VL-72B-Instruct](https://huggingface.co/Qwen/Qwen2.5-VL-72B-Instruct) | Earlier Qwen visual-reasoning release for charts, documents, and video; compare with Qwen3-VL before choosing |
| [openai/clip-vit-large-patch14](https://huggingface.co/openai/clip-vit-large-patch14) | Image-text similarity, classic baseline |
| [Salesforce/blip-image-captioning-large](https://huggingface.co/Salesforce/blip-image-captioning-large) | Image captioning |
| [google/paligemma2-3b-pt-448](https://huggingface.co/google/paligemma2-3b-pt-448) | Fine-tunable VLM base, PaliGemma 2 |
| [microsoft/Phi-4-multimodal-instruct](https://huggingface.co/microsoft/Phi-4-multimodal-instruct) | Compact vision/audio/text instruction model; verify support and quality for each input modality |

### Audio-Text

| Model | Capability |
|-------|-----------|
| [laion/clap-htsat-unfused](https://huggingface.co/laion/clap-htsat-unfused) | Audio/text similarity and candidate-label ranking for retrieval or zero-shot classification; scores are not calibrated probabilities |
| [Qwen/Qwen3-Omni-30B-A3B-Instruct](https://huggingface.co/Qwen/Qwen3-Omni-30B-A3B-Instruct) | Audio/video understanding with text or speech responses; large MoE checkpoint and heavier runtime, for workflows that need multiple modalities in one model |

---

## Tabular Data

This section focuses on modern tabular architectures and foundation models for supervised classification and regression. It does not treat conventional algorithms as new architectures. TabPFN, TabICL, and TabDPT are pretrained in-context models; TabM and RealMLP are neural models trained on the task data; xRFM is a feature-learning kernel/tree model. Published advantages apply to their tested benchmark settings, so keep a leakage-safe holdout and evaluate with the metric that matches the task. For time-ordered or grouped data, use a time or group split.

### Tabular Model Selection

| Model | Best use case | Evidence and limits |
|-------|---------------|--------------------|
| [TabPFN v2 classifier](https://huggingface.co/Prior-Labs/TabPFN-v2-clf) / [regressor](https://huggingface.co/Prior-Labs/TabPFN-v2-reg) | First pretrained candidate for small-to-medium supervised tables; supports classification and regression without per-dataset hyperparameter search. | The peer-reviewed [Nature paper](https://www.nature.com/articles/s41586-024-08328-6) evaluates datasets up to 10,000 rows and 500 features and reports strong results against tuned baselines. Treat those as the measured scope; larger datasets increase resource needs. Check the [model card and Prior Labs License](https://huggingface.co/Prior-Labs/TabPFN-v2-clf), including attribution conditions. |
| [TabICLv2](https://huggingface.co/jingang/TabICL) | Pretrained classification and regression, including larger tables; the official `tabicl` package defaults to TabICLv2 checkpoints and handles common mixed feature types. | The [ICML 2026 paper](https://proceedings.mlr.press/v306/qu26a.html) reports untuned TabICLv2 outperforming tuned/ensembled RealTabPFN-2.5 on TabArena and TALENT, with million-row scale under 50 GB GPU memory. These are authors' benchmark results; docs center pretraining on 300–60K rows and caution performance can degrade outside tested ranges. [Official docs](https://tabicl.readthedocs.io/). |
| [TabDPT v1.3](https://huggingface.co/Layer6/TabDPT) | Pretrained in-context classification and regression on new tables, with a probabilistic-regression output option. Useful as another foundation-model candidate when numeric feature matrices fit its inference context. | The base model is peer-reviewed at [NeurIPS 2025](https://proceedings.neurips.cc/paper_files/paper/2025/hash/fc0e3f908a2116ba529ad0a1530a3675-Abstract-Conference.html). The v1.3 release and its benchmark table are maintainer-reported, not a separately peer-reviewed version; its real-data pretraining also creates possible benchmark overlap. [Official code, release notes, and examples](https://github.com/layer6ai-labs/TabDPT-inference). Apache-2.0. |
| [TabM](https://huggingface.co/papers/2410.24210) ([official implementation](https://github.com/yandex-research/tabm)) | Train-on-your-data neural architecture for classification or regression; use when you can spend time on preprocessing, validation, and fitting. It is an architecture, not a pretrained Hub checkpoint. | Accepted at [ICLR 2025](https://proceedings.iclr.cc/paper_files/paper/2025/hash/c1ba41c694834aeef91ae161711d4939-Abstract-Conference.html). The paper reports stronger performance than earlier tabular deep-learning models on its tested benchmarks, not universal wins over every model family or dataset. Apache-2.0 code; benchmark details in the [official repository](https://github.com/yandex-research/tabm). |
| [RealMLP](https://github.com/dholzmueller/pytabkit) | Task-trained MLP with meta-tuned defaults for medium-to-large tables when a practical training recipe is more important than zero-shot use. | The [NeurIPS 2024 paper](https://proceedings.neurips.cc/paper_files/paper/2024/hash/2ee1c87245956e3eaa71aaba5f5753eb-Abstract-Conference.html) evaluates 90 held-out meta-test datasets and reports a strong accuracy/time trade-off against neural and tree baselines. It is trained on your dataset, not a pretrained foundation checkpoint. PyTabKit is Apache-2.0; missing numeric values need imputation. |
| [xRFM](https://github.com/dmbeaglehole/xRFM) | Modern feature-learning model for both regression and classification, combining kernel machines with a tree to adapt to local structure; useful when tabular feature interactions and interpretability matter. No pretrained Hub checkpoint. | Accepted at [ICLR 2026](https://proceedings.iclr.cc/paper_files/paper/2026/hash/ecbc5963c05a83e07404c028b55b29bc-Abstract-Conference.html). Against 31 methods, the paper reports best performance across 100 TALENT regression datasets and competitive results across 200 classification datasets, outperforming GBDTs there. This is benchmark-scoped, not a universal classification win. MIT. |

Choose among the pretrained models by matching dataset size, task, hardware, and license constraints. Compare TabM or RealMLP when you want a trainable neural model, and xRFM when you want learned local feature structure. Compare holdout performance and inference cost; none of the cited papers establishes a universal winner for every table or split.

### Tabular Code

The examples below cover pretrained in-context models, train-on-your-data neural models, and xRFM. Change the file path and target column. Keep the test set untouched until model selection is complete; replace random splitting with a time/group split when required by the data.

Install the dependencies:

```bash
pip install pandas "scikit-learn>=1.4" tabpfn tabicl tabdpt
pip install "pytabkit[models]" xrfm
```

Classification (complete script):

```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score, f1_score
from tabpfn import TabPFNClassifier
from tabpfn.constants import ModelVersion
from tabicl import TabICLClassifier

# CSV must contain a categorical target column and feature columns.
df = pd.read_csv("data.csv")
target = "label"
X = df.drop(columns=target)
y = df[target]
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42, stratify=y
)

models = {
    "TabPFN v2": TabPFNClassifier.create_default_for_version(ModelVersion.V2),
    "TabICL": TabICLClassifier(),
}
for name, model in models.items():
    model.fit(X_train, y_train)
    pred = model.predict(X_test)
    print(f"{name}: accuracy={accuracy_score(y_test, pred):.4f}, "
          f"macro_f1={f1_score(y_test, pred, average='macro'):.4f}")
```

TabM classification through PyTabKit’s scikit-learn interface (train-on-your-data; numeric missing values must be imputed first):

```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score, f1_score
from pytabkit import TabM_D_Classifier, RealMLP_TD_Classifier

# CSV must contain a categorical target and numeric or categorical features.
df = pd.read_csv("data.csv")
target = "label"
cat_cols = ["country", "product_type"]  # replace with your categorical column names
X = df.drop(columns=target)
y = df[target]

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42, stratify=y
)
X_fit, X_valid, y_fit, y_valid = train_test_split(
    X_train, y_train, test_size=0.2, random_state=42, stratify=y_train
)
X_fit, X_valid, X_test = X_fit.copy(), X_valid.copy(), X_test.copy()

# Fit numeric imputation on the training fold only to avoid leakage.
num_cols = X.select_dtypes(include="number").columns
medians = X_fit[num_cols].median()
for frame in (X_fit, X_valid, X_test):
    frame.loc[:, num_cols] = frame[num_cols].fillna(medians)

models = {
    "TabM": TabM_D_Classifier(device="cpu", random_state=42),
    "RealMLP-TD": RealMLP_TD_Classifier(device="cpu", random_state=42),
}
for name, model in models.items():
    model.fit(X_fit, y_fit, X_valid, y_valid, cat_col_names=cat_cols)
    pred = model.predict(X_test)
    print(f"{name}: accuracy={accuracy_score(y_test, pred):.4f}, "
          f"macro-F1={f1_score(y_test, pred, average='macro'):.4f}")
```

TabM regression through PyTabKit (same training-fold-only numeric imputation):

```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_absolute_error, root_mean_squared_error
from pytabkit import TabM_D_Regressor, RealMLP_TD_Regressor

# CSV must contain a numeric target and numeric or categorical features.
df = pd.read_csv("data.csv")
target = "target_value"
cat_cols = ["country", "product_type"]  # replace with your categorical column names
X = df.drop(columns=target)
y = df[target]
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)
X_fit, X_valid, y_fit, y_valid = train_test_split(
    X_train, y_train, test_size=0.2, random_state=42
)
X_fit, X_valid, X_test = X_fit.copy(), X_valid.copy(), X_test.copy()
num_cols = X.select_dtypes(include="number").columns
medians = X_fit[num_cols].median()
for frame in (X_fit, X_valid, X_test):
    frame.loc[:, num_cols] = frame[num_cols].fillna(medians)

models = {
    "TabM": TabM_D_Regressor(device="cpu", random_state=42),
    "RealMLP-TD": RealMLP_TD_Regressor(device="cpu", random_state=42),
}
for name, model in models.items():
    model.fit(X_fit, y_fit, X_valid, y_valid, cat_col_names=cat_cols)
    pred = model.predict(X_test)
    print(f"{name}: MAE={mean_absolute_error(y_test, pred):.4f}, "
          f"RMSE={root_mean_squared_error(y_test, pred):.4f}")
```

Regression (complete script with a numeric target column):

```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_absolute_error, root_mean_squared_error
from tabpfn import TabPFNRegressor
from tabpfn.constants import ModelVersion
from tabicl import TabICLRegressor

# CSV must contain a numeric target column and feature columns.
df = pd.read_csv("data.csv")
target = "target_value"
X = df.drop(columns=target)
y = df[target]
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

models = {
    "TabPFN v2": TabPFNRegressor.create_default_for_version(ModelVersion.V2),
    "TabICL": TabICLRegressor(),
}
for name, model in models.items():
    model.fit(X_train, y_train)
    pred = model.predict(X_test)
    print(f"{name}: MAE={mean_absolute_error(y_test, pred):.4f}, "
          f"RMSE={root_mean_squared_error(y_test, pred):.4f}")
```

TabDPT classification or regression on a mixed CSV (one-hot encoding is fit on training data only; high-cardinality columns can produce too many features for a dense matrix):

```python
import numpy as np
import pandas as pd
from sklearn.compose import ColumnTransformer
from sklearn.impute import SimpleImputer
from sklearn.metrics import accuracy_score, f1_score, mean_absolute_error, root_mean_squared_error
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import LabelEncoder, OneHotEncoder
from sklearn.pipeline import Pipeline
from tabdpt import TabDPTClassifier, TabDPTRegressor

task = "classification"  # set to "regression" for a numeric target
target = "label" if task == "classification" else "target_value"
df = pd.read_csv("data.csv")
X = df.drop(columns=target)

if task == "classification":
    label_encoder = LabelEncoder()
    y = label_encoder.fit_transform(df[target].astype(str))
    stratify = y
else:
    y = df[target].to_numpy(dtype=np.float32)
    stratify = None

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42, stratify=stratify
)
numeric_cols = X_train.select_dtypes(include="number").columns.tolist()
categorical_cols = [col for col in X_train.columns if col not in numeric_cols]
transformers = []
if numeric_cols:
    transformers.append(("numeric", SimpleImputer(strategy="median"), numeric_cols))
if categorical_cols:
    categorical_pipeline = Pipeline([
        ("imputer", SimpleImputer(strategy="most_frequent")),
        ("onehot", OneHotEncoder(handle_unknown="ignore", sparse_output=False, dtype=np.float32)),
    ])
    transformers.append(("categorical", categorical_pipeline, categorical_cols))
preprocessor = ColumnTransformer(transformers, sparse_threshold=0.0)
X_train = np.asarray(preprocessor.fit_transform(X_train), dtype=np.float32)
X_test = np.asarray(preprocessor.transform(X_test), dtype=np.float32)

if task == "classification":
    model = TabDPTClassifier()
    model.fit(X_train, y_train)
    pred = model.predict(
        X_test, n_ensembles=8, temperature=1.0,
        context_size=None, permute_classes=True, seed=42
    )
    print("accuracy:", accuracy_score(y_test, pred))
    print("macro-F1:", f1_score(y_test, pred, average="macro"))
else:
    model = TabDPTRegressor()
    model.fit(X_train, y_train)
    pred = model.predict(X_test, n_ensembles=2, seed=42)
    print("MAE:", mean_absolute_error(y_test, pred))
    print("RMSE:", root_mean_squared_error(y_test, pred))
```

xRFM supports numeric and categorical features. This complete script fits imputers, the numeric scaler, and one-hot categories on the training fold; choose `task` and set the target column accordingly. xRFM requires a validation set for model selection.

```python
import numpy as np
import pandas as pd
import torch
from sklearn.impute import SimpleImputer
from sklearn.metrics import accuracy_score, f1_score, mean_absolute_error, root_mean_squared_error
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import LabelEncoder, OneHotEncoder, StandardScaler
from xrfm import xRFM

task = "classification"  # set to "regression" for a numeric target
target = "label" if task == "classification" else "target_value"
df = pd.read_csv("data.csv")
X = df.drop(columns=target)
numeric_cols = X.select_dtypes(include="number").columns.tolist()
categorical_cols = [col for col in X.columns if col not in numeric_cols]

if task == "classification":
    label_encoder = LabelEncoder()
    y = label_encoder.fit_transform(df[target].astype(str)).astype(np.int64)
    stratify = y
    tuning_metric = "accuracy"
else:
    y = df[target].to_numpy(dtype=np.float32)
    stratify = None
    tuning_metric = "mse"

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42, stratify=stratify
)
X_fit, X_valid, y_fit, y_valid = train_test_split(
    X_train, y_train, test_size=0.2, random_state=42,
    stratify=y_train if task == "classification" else None
)

def preprocess(train_df, valid_df, test_df):
    train_parts, valid_parts, test_parts = [], [], []
    categorical_info = None

    if numeric_cols:
        imputer = SimpleImputer(strategy="median")
        scaler = StandardScaler()
        train_num = scaler.fit_transform(imputer.fit_transform(train_df[numeric_cols]))
        valid_num = scaler.transform(imputer.transform(valid_df[numeric_cols]))
        test_num = scaler.transform(imputer.transform(test_df[numeric_cols]))
        train_parts.append(train_num)
        valid_parts.append(valid_num)
        test_parts.append(test_num)
        n_numeric = train_num.shape[1]
    else:
        n_numeric = 0

    if categorical_cols:
        cat_imputer = SimpleImputer(strategy="most_frequent")
        encoder = OneHotEncoder(handle_unknown="ignore", sparse_output=False, dtype=np.float32)
        train_cat = encoder.fit_transform(cat_imputer.fit_transform(train_df[categorical_cols]))
        valid_cat = encoder.transform(cat_imputer.transform(valid_df[categorical_cols]))
        test_cat = encoder.transform(cat_imputer.transform(test_df[categorical_cols]))
        train_parts.append(train_cat)
        valid_parts.append(valid_cat)
        test_parts.append(test_cat)

        category_indices, category_vectors = [], []
        start = n_numeric
        for categories in encoder.categories_:
            width = len(categories)
            category_indices.append(torch.arange(start, start + width, dtype=torch.long))
            category_vectors.append(torch.eye(width, dtype=torch.float32))
            start += width
        categorical_info = {
            "numerical_indices": torch.arange(n_numeric, dtype=torch.long),
            "categorical_indices": category_indices,
            "categorical_vectors": category_vectors,
        }

    X_fit = np.hstack(train_parts).astype(np.float32)
    X_valid = np.hstack(valid_parts).astype(np.float32)
    X_test = np.hstack(test_parts).astype(np.float32)
    return X_fit, X_valid, X_test, categorical_info

X_fit_np, X_valid_np, X_test_np, categorical_info = preprocess(X_fit, X_valid, X_test)
device = torch.device("cuda" if torch.cuda.is_available() else "cpu")
model = xRFM(device=device, tuning_metric=tuning_metric, categorical_info=categorical_info)
model.fit(X_fit_np, y_fit, X_valid_np, y_valid)
prediction = model.predict(X_test_np)
if isinstance(prediction, torch.Tensor):
    prediction = prediction.detach().cpu().numpy()
prediction = np.asarray(prediction).reshape(-1)

if task == "classification":
    print("accuracy:", accuracy_score(y_test, prediction))
    print("macro-F1:", f1_score(y_test, prediction, average="macro"))
else:
    print("MAE:", mean_absolute_error(y_test, prediction))
    print("RMSE:", root_mean_squared_error(y_test, prediction))
```

---

## Featured Models

### Most Downloaded (all time)

| Model | Why it matters |
|-------|---------------|
| [bert-base-uncased](https://huggingface.co/bert-base-uncased) | Foundational encoder, still used for fine-tuning baselines |
| [gpt2](https://huggingface.co/gpt2) | Original GPT-2, reference decoder for teaching |
| [distilbert-base-uncased](https://huggingface.co/distilbert-base-uncased) | Distilled BERT, ~40% smaller, ~60% faster |
| [openai/clip-vit-base-patch32](https://huggingface.co/openai/clip-vit-base-patch32) | Baseline image-text model, still widely deployed |

### Featured Newer Releases (October 2026)

| Model | Category |
|-------|----------|
| [openai/gpt-oss-120b](https://huggingface.co/openai/gpt-oss-120b) | Open LLM |
| [deepseek-ai/DeepSeek-V3.2](https://huggingface.co/deepseek-ai/DeepSeek-V3.2) | Open LLM |
| [moonshotai/Kimi-K2-Instruct](https://huggingface.co/moonshotai/Kimi-K2-Instruct) | Open LLM |
| [zai-org/GLM-4.6](https://huggingface.co/zai-org/GLM-4.6) | Open LLM |
| [Qwen/Qwen3-Coder-480B-A35B-Instruct](https://huggingface.co/Qwen/Qwen3-Coder-480B-A35B-Instruct) | Code |
| [Qwen/Qwen3-VL-235B-A22B-Instruct](https://huggingface.co/Qwen/Qwen3-VL-235B-A22B-Instruct) | Multimodal |
| [facebook/sam2.1-hiera-large](https://huggingface.co/facebook/sam2.1-hiera-large) | Promptable image/video segmentation |
| [Qwen/Qwen3-ASR-1.7B](https://huggingface.co/Qwen/Qwen3-ASR-1.7B) | Multilingual ASR, including Indonesian |
| [Qwen/Qwen3-VL-30B-A3B-Instruct](https://huggingface.co/Qwen/Qwen3-VL-30B-A3B-Instruct) | Image/video/document reasoning |
| [Lightricks/LTX-2.5](https://huggingface.co/Lightricks/LTX-2.5) | Open-weight video with synchronized audio |
| [facebook/sam3](https://huggingface.co/facebook/sam3) | Promptable concept segmentation and video tracking |
| [facebook/PE-Core-L14-336](https://huggingface.co/facebook/PE-Core-L14-336) | Robust zero-shot vision-language classification |
| [facebook/dinov3-vitb16-pretrain-lvd1689m](https://huggingface.co/facebook/dinov3-vitb16-pretrain-lvd1689m) | Visual representation learning |
| [imageomics/bioclip-2](https://huggingface.co/imageomics/bioclip-2) | Biodiversity and species image recognition |
| [PaddlePaddle/PaddleOCR-VL-1.6](https://huggingface.co/PaddlePaddle/PaddleOCR-VL-1.6) | Document parsing |
| [TabPFN v2](https://huggingface.co/Prior-Labs/TabPFN-v2-clf) | Small-to-medium tabular classification |
| [jingang/TabICL](https://huggingface.co/jingang/TabICL) | In-context tabular classification and regression |
| [Layer6/TabDPT](https://huggingface.co/Layer6/TabDPT) | In-context tabular learning |
| [xRFM](https://github.com/dmbeaglehole/xRFM) | Feature-learning model for tabular prediction |

---

## Recommended Picks (October 2026)

These are task-fit starting points, not universal benchmark winners. Check the task scope, license, hardware, and linked evaluation before deployment.

- **General open-weight assistant** -> Compare GPT-OSS-20B, Qwen3-30B-A3B-Instruct, and DeepSeek-V3.2 on your prompt/tool set.
- **Multi-step reasoning** -> DeepSeek-R1-0528 or a Qwen3 Thinking checkpoint; set enough output budget for reasoning traces.
- **Code completion/infill** -> StarCoder2; **instruction-based coding** -> Qwen3-Coder at a size your serving budget can support.
- **Image and video reasoning** -> Qwen3-VL; **integrated audio/video conversation** -> Qwen3-Omni with significant compute.
- **Fixed-label image classification** -> start with EVA-02 Small; compare TransNeXt Base 384 or ConvNeXt Base after validation on the target labels. **Changing/open labels** -> SigLIP 2 or PE-Core; **on-device prompt labels** -> MobileCLIP2-S2 with its research-only weight terms. **Species recognition** -> BioCLIP-2 for taxonomic labels.
- **Visual feature extraction** -> DINOv2; **prompted object masks** -> SAM 2; **fixed-class real-time boxes** -> RT-DETRv2.
- **Human keypoints** -> ViTPose++ with a person detector; **alpha matting** -> ViTMatte when an aligned trimap is available; **multi-view geometry** -> VGGT when its GPU and non-commercial license constraints fit.
- **Image generation** -> FLUX.1-dev for high-quality local open weights under its non-commercial terms; FLUX.1-schnell for fast Apache-2.0 generation.
- **Prompt-based image editing** -> FLUX.1-Kontext-dev; verify consistency and review its license.
- **Video generation** -> Compare Wan2.2 and LTX-2.5 for quality, synchronized audio, runtime, and license.
- **ASR with Indonesian support** -> Qwen3-ASR; compare with Whisper on your own accents/noise.
- **English ASR latency** -> Parakeet-TDT; **broad multilingual baseline** -> Whisper large-v3.
- **Preset multilingual TTS** -> Qwen3-TTS CustomVoice (10 languages, no Indonesian); **reference voice cloning** -> Qwen3-TTS Base with consented audio.
- **Small-to-medium supervised tables** -> evaluate TabPFN v2; **larger classification and regression tables** -> evaluate TabICLv2; **trainable neural model** -> compare TabM, RealMLP, and xRFM. Keep the recommendation tied to published benchmark scope and validate on a held-out split.
- **Multilingual retrieval** -> BGE-M3 for hybrid retrieval or GTE-Qwen2-1.5B for longer-context embeddings; rerank only after candidate retrieval.

---

## Snippets

### Text generation with chat template

```python
from transformers import AutoModelForCausalLM, AutoTokenizer
import torch

model_id = "Qwen/Qwen3-30B-A3B-Instruct-2507"
tokenizer = AutoTokenizer.from_pretrained(model_id)
model = AutoModelForCausalLM.from_pretrained(
    model_id,
    torch_dtype=torch.bfloat16,
    device_map="auto",
)

messages = [
    {"role": "system", "content": "You are a helpful coding assistant."},
    {"role": "user", "content": "Refactor this Python function to use pathlib."},
]
inputs = tokenizer.apply_chat_template(
    messages, add_generation_prompt=True, return_tensors="pt"
).to(model.device)

with torch.no_grad():
    out = model.generate(inputs, max_new_tokens=512, do_sample=True, temperature=0.7)
print(tokenizer.decode(out[0][inputs.shape[-1]:], skip_special_tokens=True))
```

### Streaming output with Transformers

```python
from transformers import TextIteratorStreamer
from threading import Thread

streamer = TextIteratorStreamer(tokenizer, skip_prompt=True, skip_special_tokens=True)
gen_kwargs = dict(inputs=inputs, streamer=streamer, max_new_tokens=512)
Thread(target=model.generate, kwargs=gen_kwargs).start()

for text in streamer:
    print(text, end="", flush=True)
```

### Fast inference with vLLM

```python
from vllm import LLM, SamplingParams

llm = LLM(model="openai/gpt-oss-120b", tensor_parallel_size=1, dtype="bfloat16")
prompts = ["Explain backpropagation in 3 sentences."]
out = llm.generate(prompts, SamplingParams(temperature=0.7, max_tokens=200))
print(out[0].outputs[0].text)
```

### Embeddings + rerank pipeline (RAG)

```python
from sentence_transformers import SentenceTransformer
from FlagEmbedding import FlagReranker

docs = ["Paris is the capital of France.", "Rome is the capital of Italy.", "Berlin is the capital of Germany."]
query = "What is the capital of France?"

embedder = SentenceTransformer("Alibaba-NLP/gte-modernbert-base")
doc_embs = embedder.encode(docs, normalize_embeddings=True)
q_emb = embedder.encode([query], normalize_embeddings=True)

# Stage 1: retrieve top-3 by cosine similarity
scores = (doc_embs @ q_emb.T).ravel()
top_idx = scores.argsort()[::-1][:3]
candidates = [docs[i] for i in top_idx]

# Stage 2: rerank with a cross-encoder
reranker = FlagReranker("BAAI/bge-reranker-v2-m3", use_fp16=True)
pairs = [[query, c] for c in candidates]
rerank_scores = reranker.compute_score(pairs, normalize=True)

best = sorted(zip(candidates, rerank_scores), key=lambda x: -x[1])[0]
print(best)
```

### Financial sentiment classification

```python
from transformers import pipeline

classifier = pipeline("text-classification", model="ProsusAI/finbert")
print(classifier("The company reported higher quarterly revenue."))
```

### Long scientific-paper summarization with LED

LED expects global attention on the first token for long-document generation. This checkpoint is fine-tuned for arXiv papers, not arbitrary long documents.

```python
import torch
from transformers import AutoModelForSeq2SeqLM, AutoTokenizer

model_id = "allenai/led-large-16384-arxiv"
tokenizer = AutoTokenizer.from_pretrained(model_id)
model = AutoModelForSeq2SeqLM.from_pretrained(model_id)
paper_text = open("paper.txt", encoding="utf-8").read()
inputs = tokenizer(paper_text, return_tensors="pt", max_length=16384, truncation=True)
global_attention_mask = torch.zeros_like(inputs["input_ids"])
global_attention_mask[:, 0] = 1
summary_ids = model.generate(
    input_ids=inputs["input_ids"],
    attention_mask=inputs["attention_mask"],
    global_attention_mask=global_attention_mask,
    max_new_tokens=512,
    num_beams=4,
)
print(tokenizer.batch_decode(summary_ids, skip_special_tokens=True)[0])
```

### Whisper Turbo batched transcription

```python
from transformers import pipeline

asr = pipeline(
    "automatic-speech-recognition",
    model="openai/whisper-large-v3-turbo",
    chunk_length_s=30,
    device="cuda",
)
result = asr("meeting.wav", return_timestamps=True, batch_size=8)
print(result["text"])
```

### Qwen3-ASR multilingual transcription

Qwen3-ASR uses its own `qwen-asr` package. Its card lists Indonesian among supported languages; validate accent, noise, and domain vocabulary with your own audio.

```python
# pip install -U qwen-asr
import torch
from qwen_asr import Qwen3ASRModel

model = Qwen3ASRModel.from_pretrained(
    "Qwen/Qwen3-ASR-1.7B",
    dtype=torch.bfloat16,
    device_map="cuda:0",
)
result = model.transcribe(audio="meeting.wav", language="Indonesian")
print(result)
```

### Qwen3-TTS preset-voice synthesis

This CustomVoice checkpoint provides preset speakers in 10 languages, which do not include Indonesian.

```python
# pip install -U qwen-tts soundfile
import torch
import soundfile as sf
from qwen_tts import Qwen3TTSModel

model = Qwen3TTSModel.from_pretrained(
    "Qwen/Qwen3-TTS-12Hz-0.6B-CustomVoice",
    device_map="cuda:0",
    dtype=torch.bfloat16,
    attn_implementation="flash_attention_2",
)
wavs, sample_rate = model.generate_custom_voice(
    text="The next train departs in five minutes.",
    language="English",
    speaker="Ryan",
    instruct="Speak clearly and calmly.",
)
sf.write("announcement.wav", wavs[0], sample_rate)
```

### NLLB translation

Replace the source and target tags with supported language codes from the model card. Translation quality varies by language pair; NLLB's model-card license limits use to research and humanitarian purposes.

```python
from transformers import AutoModelForSeq2SeqLM, AutoTokenizer

model_id = "facebook/nllb-200-distilled-600M"
source_language = "eng_Latn"
target_language = "ind_Latn"
tokenizer = AutoTokenizer.from_pretrained(model_id, src_lang=source_language)
model = AutoModelForSeq2SeqLM.from_pretrained(model_id)
inputs = tokenizer("The meeting starts at noon.", return_tensors="pt", truncation=True)
translated = model.generate(
    **inputs,
    forced_bos_token_id=tokenizer.convert_tokens_to_ids(target_language),
    max_new_tokens=128,
)
print(tokenizer.batch_decode(translated, skip_special_tokens=True)[0])
```

### FLUX.1 image generation

```python
from diffusers import FluxPipeline
import torch

pipe = FluxPipeline.from_pretrained("black-forest-labs/FLUX.1-dev", torch_dtype=torch.bfloat16)
pipe.to("cuda")
image = pipe(
    prompt="a photo of a red panda wearing a tiny chef hat, soft natural light",
    num_inference_steps=28,
    guidance_scale=3.5,
    height=1024, width=1024,
).images[0]
image.save("panda.png")
```

### FLUX.1-Kontext image editing

```python
from diffusers import FluxKontextPipeline
from PIL import Image
import torch

pipe = FluxKontextPipeline.from_pretrained(
    "black-forest-labs/FLUX.1-Kontext-dev", torch_dtype=torch.bfloat16
).to("cuda")

input_image = Image.open("portrait.png").convert("RGB")
edited = pipe(
    image=input_image,
    prompt="add round glasses and a yellow beanie",
    num_inference_steps=20,
    guidance_scale=2.5,
).images[0]
edited.save("portrait_edited.png")
```

### Supervised image classification

Install `transformers[torch]`, `timm`, and Pillow first. This runs a fixed-label ImageNet classifier. The same pipeline pattern works for the supervised checkpoints in the table; replace the model ID and fine-tune for a new label set.

```python
from transformers import pipeline

model_id = "timm/eva02_large_patch14_448.mim_m38m_ft_in22k_in1k"
classifier = pipeline("image-classification", model=model_id)
for prediction in classifier("photo.jpg", top_k=5):
    print(prediction["label"], round(prediction["score"], 4))
```

### Zero-shot image classification with SigLIP 2

Use candidate descriptions for a changing label set. The returned similarity scores depend on the candidate list and prompt phrasing; they are not calibrated class probabilities.

```python
from transformers import pipeline

classifier = pipeline(
    "zero-shot-image-classification",
    model="google/siglip2-base-patch16-224",
)
predictions = classifier(
    "photo.jpg",
    candidate_labels=[
        "a close-up photo of a red fox",
        "a close-up photo of a domestic cat",
        "a close-up photo of a golden retriever",
    ],
)
for prediction in predictions:
    print(prediction["label"], round(prediction["score"], 4))
```

### Perception Encoder Core zero-shot classification

Install Meta's [official `perception_models` repository](https://github.com/facebookresearch/perception_models) as documented there. This uses prompt-relative image/text scores; include every candidate label you want compared.

```python
import torch
from PIL import Image
import core.vision_encoder.pe as pe
import core.vision_encoder.transforms as transforms

device = torch.device("cuda" if torch.cuda.is_available() else "cpu")
model = pe.CLIP.from_config("PE-Core-L14-336", pretrained=True).to(device).eval()
preprocess = transforms.get_image_transform(model.image_size)
tokenizer = transforms.get_text_tokenizer(model.context_length)

image = preprocess(Image.open("photo.jpg").convert("RGB")).unsqueeze(0).to(device)
labels = ["a photo of a red fox", "a photo of a gray wolf", "a photo of a coyote"]
text = tokenizer(labels).to(device)
with torch.inference_mode():
    with torch.autocast(device_type=device.type, enabled=device.type == "cuda"):
        image_features, text_features, logit_scale = model(image, text)
        probabilities = (logit_scale * image_features @ text_features.T).softmax(dim=-1)[0]

print(sorted(zip(labels, probabilities.tolist()), key=lambda item: -item[1]))
```

### BioCLIP-2 species classification

Install `open_clip_torch`. Use taxonomically meaningful candidate labels; these similarity scores rank only the supplied choices.

```python
import torch
import open_clip
from PIL import Image

model_id = "hf-hub:imageomics/bioclip-2"
model, _, preprocess = open_clip.create_model_and_transforms(model_id)
tokenizer = open_clip.get_tokenizer(model_id)
model.eval()

image = preprocess(Image.open("organism.jpg").convert("RGB")).unsqueeze(0)
labels = ["a photo of a red fox", "a photo of a gray wolf", "a photo of a coyote"]
text = tokenizer(labels)
with torch.inference_mode():
    image_features = model.encode_image(image)
    text_features = model.encode_text(text)
    image_features = image_features / image_features.norm(dim=-1, keepdim=True)
    text_features = text_features / text_features.norm(dim=-1, keepdim=True)
    probabilities = (model.logit_scale.exp() * image_features @ text_features.T).softmax(dim=-1)[0]

print(sorted(zip(labels, probabilities.tolist()), key=lambda item: -item[1]))
```

### TransNeXt fixed-label classification

Clone/install the [official TransNeXt source](https://github.com/DaiShiResearch/TransNeXt) and its documented pinned dependencies first; this checkpoint uses the repository's custom `timm` model registration.

```python
import torch
import timm
import transnext  # registers the TransNeXt model definitions
from huggingface_hub import hf_hub_download
from PIL import Image
from timm.data.constants import IMAGENET_DEFAULT_MEAN, IMAGENET_DEFAULT_STD
from torchvision import transforms
from torchvision.transforms import InterpolationMode

device = torch.device("cuda" if torch.cuda.is_available() else "cpu")
model = timm.create_model(
    "transnext_base", img_size=384, pretrain_size=224, num_classes=1000, pretrained=False
)
checkpoint_path = hf_hub_download(
    "DaiShiResearch/transnext-base-384-1k-ft-1k", "transnext_base_384_1k_ft_1k.pth"
)
checkpoint = torch.load(checkpoint_path, map_location="cpu")
model.load_state_dict(checkpoint["model"] if "model" in checkpoint else checkpoint)
model = model.to(device).eval()

preprocess = transforms.Compose([
    transforms.Resize((384, 384), interpolation=InterpolationMode.BICUBIC),
    transforms.ToTensor(),
    transforms.Normalize(IMAGENET_DEFAULT_MEAN, IMAGENET_DEFAULT_STD),
])
image = preprocess(Image.open("photo.jpg").convert("RGB")).unsqueeze(0).to(device)
with torch.inference_mode():
    probabilities = model(image).softmax(dim=-1)[0]
scores, indices = probabilities.topk(5)
print(list(zip(indices.tolist(), scores.tolist())))  # ImageNet-1K class indices
```

### DINOv2 image features

This extracts a pooled feature vector. Train or fit a downstream classifier/retriever on task-specific data; DINOv2 is not a ready-made label predictor.

```python
from PIL import Image
import torch
from transformers import AutoImageProcessor, AutoModel

model_id = "facebook/dinov2-base"
processor = AutoImageProcessor.from_pretrained(model_id)
model = AutoModel.from_pretrained(model_id).eval()
image = Image.open("photo.jpg").convert("RGB")
inputs = processor(images=image, return_tensors="pt")
with torch.no_grad():
    features = model(**inputs).pooler_output
print(features.shape)
```

### RT-DETRv2 object detection

```python
import torch
from PIL import Image
from transformers import RTDetrV2ImageProcessor, RTDetrV2ForObjectDetection

model_id = "PekingU/rtdetr_v2_r50vd"
processor = RTDetrV2ImageProcessor.from_pretrained(model_id)
model = RTDetrV2ForObjectDetection.from_pretrained(model_id).eval()
image = Image.open("street.jpg").convert("RGB")
inputs = processor(images=image, return_tensors="pt")
with torch.no_grad():
    outputs = model(**inputs)
results = processor.post_process_object_detection(
    outputs,
    threshold=0.5,
    target_sizes=torch.tensor([(image.height, image.width)]),
)[0]
for score, label, box in zip(results["scores"], results["labels"], results["boxes"]):
    print(model.config.id2label[label.item()], round(score.item(), 3), box.tolist())
```

### D-FINE X object detection

This checkpoint detects the fixed COCO classes. Use `DFineForObjectDetection` with `AutoImageProcessor`; it is not a text-prompt/open-vocabulary detector.

```python
import torch
from PIL import Image
from transformers import AutoImageProcessor, DFineForObjectDetection

model_id = "ustc-community/dfine-xlarge-coco"
processor = AutoImageProcessor.from_pretrained(model_id)
model = DFineForObjectDetection.from_pretrained(model_id).eval()
image = Image.open("street.jpg").convert("RGB")
inputs = processor(images=image, return_tensors="pt")
with torch.inference_mode():
    outputs = model(**inputs)
result = processor.post_process_object_detection(
    outputs,
    threshold=0.5,
    target_sizes=[(image.height, image.width)],
)[0]
for score, label, box in zip(result["scores"], result["labels"], result["boxes"]):
    print(model.config.id2label[label.item()], round(score.item(), 3), box.tolist())
```

### SAM 2 promptable segmentation

Provide a positive click on the object to segment. The model returns candidate masks; inspect or post-process them for your task.

```python
import torch
from PIL import Image
from transformers import Sam2Model, Sam2Processor

model_id = "facebook/sam2.1-hiera-large"
model = Sam2Model.from_pretrained(model_id, device_map="auto")
processor = Sam2Processor.from_pretrained(model_id)
image = Image.open("object.jpg").convert("RGB")
points = [[[[500, 375]]]]  # x, y point inside the target object
labels = [[[1]]]           # 1 = positive click
inputs = processor(
    images=image, input_points=points, input_labels=labels, return_tensors="pt"
).to(model.device)
with torch.no_grad():
    outputs = model(**inputs)
masks = processor.post_process_masks(
    outputs.pred_masks.cpu(), inputs["original_sizes"]
)[0]
print("candidate masks:", masks.shape[1])
```

### OneFormer panoptic segmentation

Set the task token and call the matching postprocessor. This COCO checkpoint uses its trained label set; it does not accept arbitrary text labels.

```python
import torch
from PIL import Image
from transformers import OneFormerForUniversalSegmentation, OneFormerProcessor

model_id = "shi-labs/oneformer_coco_swin_large"
processor = OneFormerProcessor.from_pretrained(model_id)
model = OneFormerForUniversalSegmentation.from_pretrained(model_id).eval()
image = Image.open("street.jpg").convert("RGB")
inputs = processor(images=image, task_inputs=["panoptic"], return_tensors="pt")
with torch.inference_mode():
    outputs = model(**inputs)
result = processor.post_process_panoptic_segmentation(
    outputs, target_sizes=[(image.height, image.width)]
)[0]
for segment in result["segments_info"]:
    label = model.config.id2label[segment["label_id"]]
    print(label, round(segment["score"], 3), "segment_id=", segment["id"])
```

### SAM 3 text-prompt segmentation

This finds image regions matching a concept prompt. SAM 3 is gated and requires accepting Meta's model license on the Hub before loading the checkpoint.

```python
import torch
from PIL import Image
from transformers import Sam3Model, Sam3Processor

model_id = "facebook/sam3"
processor = Sam3Processor.from_pretrained(model_id)
model = Sam3Model.from_pretrained(model_id, device_map="auto").eval()
image = Image.open("kitchen.jpg").convert("RGB")
inputs = processor(images=image, text="red mug", return_tensors="pt").to(model.device)
with torch.inference_mode():
    outputs = model(**inputs)
result = processor.post_process_instance_segmentation(
    outputs,
    threshold=0.5,
    mask_threshold=0.5,
    target_sizes=inputs["original_sizes"].tolist(),
)[0]
print("matching objects:", len(result["masks"]))
```

### ViTPose++ human keypoints

This top-down workflow first detects people, converts boxes from `xyxy` to `xywh`, then estimates COCO keypoints with the COCO expert. It does not track identities across video frames.

```python
import torch
from PIL import Image
from transformers import (
    AutoImageProcessor,
    AutoProcessor,
    DFineForObjectDetection,
    VitPoseForPoseEstimation,
)

device = "cuda" if torch.cuda.is_available() else "cpu"
image = Image.open("people.jpg").convert("RGB")

# D-FINE X emits COCO boxes; the COCO person label is 0.
detector_id = "ustc-community/dfine-xlarge-coco"
detector_processor = AutoImageProcessor.from_pretrained(detector_id)
detector = DFineForObjectDetection.from_pretrained(detector_id).to(device).eval()
detector_inputs = detector_processor(images=image, return_tensors="pt").to(device)
with torch.inference_mode():
    detections = detector(**detector_inputs)
detections = detector_processor.post_process_object_detection(
    detections,
    target_sizes=[(image.height, image.width)],
    threshold=0.3,
)[0]
boxes = detections["boxes"][detections["labels"] == 0].cpu().numpy()
if len(boxes) == 0:
    raise ValueError("No people detected")
boxes[:, 2] -= boxes[:, 0]
boxes[:, 3] -= boxes[:, 1]  # convert xyxy to the pose API's xywh format

pose_id = "usyd-community/vitpose-plus-base"
pose_processor = AutoProcessor.from_pretrained(pose_id)
pose_model = VitPoseForPoseEstimation.from_pretrained(pose_id).to(device).eval()
pose_inputs = pose_processor(image, boxes=[boxes], return_tensors="pt").to(device)
pose_inputs["dataset_index"] = torch.tensor([0], device=device)  # COCO expert
with torch.inference_mode():
    pose_outputs = pose_model(**pose_inputs)
poses = pose_processor.post_process_pose_estimation(
    pose_outputs, boxes=[boxes], threshold=0.3
)[0]

for person_idx, pose in enumerate(poses):
    print(f"Person {person_idx}")
    for xy, label, score in zip(pose["keypoints"], pose["labels"], pose["scores"]):
        name = pose_model.config.id2label[int(label)]
        print(name, xy.tolist(), round(float(score), 3))
```

### ViTMatte alpha matting

Provide an aligned trimap (background `0`, unknown boundary `128`, foreground `255`). This checkpoint has an upstream non-commercial license restriction despite its Hub Apache metadata.

```python
import numpy as np
import torch
from PIL import Image
from transformers import VitMatteForImageMatting, VitMatteImageProcessor

device = "cuda" if torch.cuda.is_available() else "cpu"
model_id = "hustvl/vitmatte-base-composition-1k"
image = Image.open("input.jpg").convert("RGB")
trimap = Image.open("trimap.png").convert("L")
if image.size != trimap.size:
    raise ValueError("Image and trimap must have the same dimensions")

processor = VitMatteImageProcessor.from_pretrained(model_id)
model = VitMatteForImageMatting.from_pretrained(model_id).to(device).eval()
inputs = processor(images=image, trimaps=trimap, return_tensors="pt").to(device)
with torch.inference_mode():
    alpha = model(**inputs).alphas[0, 0].float().cpu().numpy()

# The processor pads to a multiple of 32; crop back to the original image.
alpha = np.clip(alpha[:image.height, :image.width], 0.0, 1.0)
Image.fromarray(np.round(alpha * 255).astype(np.uint8)).save("alpha.png")
```

### Relative depth with Depth Anything V2

The small checkpoint returns relative depth ordering for one image. The normalized visualization below is not metric distance in meters.

```python
import numpy as np
from PIL import Image
from transformers import pipeline

depth_estimator = pipeline(
    "depth-estimation",
    model="depth-anything/Depth-Anything-V2-Small-hf",
    device="cuda",
)
prediction = depth_estimator(Image.open("scene.jpg").convert("RGB"))
prediction["depth"].save("relative_depth.png")
```

### Swin2SR real-world 4× upscaling

This direct model API supports Transformers v5, where the old `image-to-image` pipeline is no longer available. The output is a plausible reconstruction, not guaranteed original detail.

```python
import numpy as np
import torch
from PIL import Image
from transformers import AutoImageProcessor, Swin2SRForImageSuperResolution

device = "cuda" if torch.cuda.is_available() else "cpu"
model_id = "caidas/swin2SR-realworld-sr-x4-64-bsrgan-psnr"
image = Image.open("low_resolution.jpg").convert("RGB")
processor = AutoImageProcessor.from_pretrained(model_id)
model = Swin2SRForImageSuperResolution.from_pretrained(model_id).to(device).eval()
inputs = processor(images=image, return_tensors="pt").to(device)
with torch.inference_mode():
    reconstruction = model(**inputs).reconstruction
sr = reconstruction[0].float().cpu().clamp(0, 1).permute(1, 2, 0).numpy()
Image.fromarray(np.round(sr * 255).astype(np.uint8)).save("upscaled_x4.png")
```

### VGGT multi-view geometry

Clone the [official repository](https://github.com/facebookresearch/vggt) and install its documented dependencies. This inference example processes several views; the original 1B weights are non-commercial and require a GPU for practical use.

```python
import torch
from vggt.models.vggt import VGGT
from vggt.utils.load_fn import load_and_preprocess_images

if not torch.cuda.is_available():
    raise RuntimeError("VGGT-1B inference requires a CUDA GPU in this example")
device = "cuda"
dtype = torch.bfloat16 if torch.cuda.get_device_capability()[0] >= 8 else torch.float16
model = VGGT.from_pretrained("facebook/VGGT-1B").to(device).eval()
images = load_and_preprocess_images(
    ["view1.jpg", "view2.jpg", "view3.jpg"], mode="pad"
).to(device)

with torch.inference_mode(), torch.cuda.amp.autocast(dtype=dtype):
    predictions = model(images)

for name in ("pose_enc", "depth", "depth_conf", "world_points", "world_points_conf"):
    value = predictions.get(name)
    if value is not None:
        print(name, tuple(value.shape))
```

### Scene text detection and recognition with PP-OCRv5

This example uses the server detector and recognizer documented by PaddleOCR. Install PaddleOCR and the PaddlePaddle build matching your platform first. The server recognizer's documented evaluation does not establish Indonesian-specific accuracy.

```python
from paddleocr import PaddleOCR

ocr = PaddleOCR(
    text_detection_model_name="PP-OCRv5_server_det",
    text_recognition_model_name="PP-OCRv5_server_rec",
    use_doc_orientation_classify=False,
    use_doc_unwarping=False,
    use_textline_orientation=False,
)
for result in ocr.predict("sign.jpg"):
    result.print()
    result.save_to_json(save_path="./ocr_output")
```

### Page parsing with PaddleOCR-VL 1.6

Use this for document pages containing layout, text, tables, formulas, charts, or seals. It can process each page in a PDF and save structured output; install the PaddleOCR runtime and a supported inference backend first.

```python
from pathlib import Path
from paddleocr import PaddleOCRVL

output_dir = Path("./document_output")
output_dir.mkdir(parents=True, exist_ok=True)
pipeline = PaddleOCRVL(pipeline_version="v1.6")
for result in pipeline.predict("report.pdf"):
    result.print()
    result.save_to_json(save_path=output_dir)
    result.save_to_markdown(save_path=output_dir)
```

### Video features with VideoPrism

VideoPrism's base checkpoint is a frozen encoder. Add a task-specific head for action classes; use the LVT variant for text-video similarity. The Transformers integration currently documents revision `refs/pr/4`.

```python
import torch
from transformers import AutoModel, AutoVideoProcessor

model_id = "google/videoprism-base-f16r288"
processor = AutoVideoProcessor.from_pretrained(model_id, revision="refs/pr/4")
model = AutoModel.from_pretrained(
    model_id, revision="refs/pr/4", device_map="auto"
).eval()
video = "clip.mp4"  # local path or a supported video URL
processed = processor(videos=[video], return_metadata=True, do_sample_frames=True)
pixel_values = processed["pixel_values_videos"].to(model.device)
with torch.inference_mode():
    outputs = model(pixel_values)
video_features = outputs.last_hidden_state
print(video_features.shape)
```

### Qwen-Image 2512 generation

This uses the current Diffusers pipeline for the text-to-image checkpoint. The weight files are large; select a supported accelerator and precision that fit your available memory.

```python
import torch
from diffusers import DiffusionPipeline

pipe = DiffusionPipeline.from_pretrained(
    "Qwen/Qwen-Image-2512",
    dtype=torch.bfloat16,
    device_map="cuda",
)
image = pipe(
    "A hand-painted street-market sign that clearly reads 'PASAR PAGI', warm morning light",
    num_inference_steps=50,
).images[0]
image.save("market_sign.png")
```

### Qwen-Image-Edit 2511

Edit a reference image with natural-language instructions. Match the image and prompt options to the desired single- or multi-image edit workflow in the model card.

```python
import torch
from diffusers import QwenImageEditPlusPipeline
from PIL import Image

pipe = QwenImageEditPlusPipeline.from_pretrained(
    "Qwen/Qwen-Image-Edit-2511",
    torch_dtype=torch.bfloat16,
).to("cuda")
source = Image.open("portrait.jpg").convert("RGB")
edited = pipe(
    image=[source],
    prompt="Replace the background with a quiet garden while keeping the person's face and clothing unchanged.",
    num_inference_steps=40,
    true_cfg_scale=4.0,
    guidance_scale=1.0,
    negative_prompt=" ",
).images[0]
edited.save("portrait_edited.png")
```

### LTX-2.5 text-to-video

Accept the gated model terms, authenticate with `hf auth login`, clone the [official LTX-2 repository](https://github.com/Lightricks/LTX-2), install its dependencies, and download the listed model assets (about 66 GiB for the basic distilled workflow). Then run the documented pipeline with the downloaded asset paths:

```bash
uv sync --extra natten
uv run python -m ltx_pipelines.distilled \
  --transformer-path models/ltx-2.5/diffusion_models/ltx-2.5-22b-distilled-transformer-bf16.safetensors \
  --text-encoder-path models/ltx-2.5/text_encoders/gemma4-12b-with-proj-ltx-2.5-bf16.safetensors \
  --video-vae-path models/ltx-2.5/vae/ltx-2.5-video-vae-bf16.safetensors \
  --audio-vae-path models/ltx-2.5/vae/ltx-2.5-audio-vae-bf16.safetensors \
  --spatial-upsampler-path models/ltx-2.5/latent_upscale_models/ltx-2.5-latent-spatial-upscaler-x2-bf16-1.0.safetensors \
  --num-frames 121 --seed 42 --output-path output.mp4 \
  --prompt "A red bicycle rolls through a quiet rainy street at dusk. Slow tracking shot."
```

For image-to-video, add `--image input.jpg 0 0.8` to condition the first frame. Check the official repository for current hardware and license requirements.

### LoRA fine-tuning with PEFT

```python
from peft import LoraConfig, get_peft_model
from transformers import AutoModelForCausalLM

model = AutoModelForCausalLM.from_pretrained(
    "meta-llama/Meta-Llama-3.3-70B-Instruct",
    device_map="auto", torch_dtype=torch.bfloat16,
)
config = LoraConfig(
    r=16, lora_alpha=32, lora_dropout=0.05,
    target_modules=["q_proj", "k_proj", "v_proj", "o_proj"],
    task_type="CAUSAL_LM",
)
model = get_peft_model(model, config)
model.print_trainable_parameters()  # ~0.1% of params
```

### Quantized loading (4-bit) with bitsandbytes

```python
from transformers import AutoModelForCausalLM, BitsAndBytesConfig
import torch

bnb_config = BitsAndBytesConfig(
    load_in_4bit=True,
    bnb_4bit_quant_type="nf4",
    bnb_4bit_compute_dtype=torch.bfloat16,
    bnb_4bit_use_double_quant=True,
)
model = AutoModelForCausalLM.from_pretrained(
    "Qwen/Qwen3-235B-A22B-Instruct-2507",
    quantization_config=bnb_config,
    device_map="auto",
)
```

### Run GGUF locally with llama.cpp

```bash
# Download a quantized GGUF
huggingface-cli download Qwen/Qwen3-30B-A3B-Instruct-2507-GGUF \
  Qwen3-30B-A3B-Instruct-2507-Q4_K_M.gguf --local-dir ./models

# Run inference
llama-cli -m ./models/Qwen3-30B-A3B-Instruct-2507-Q4_K_M.gguf \
  -p "Write a haiku about distributed systems" -n 128
```

### Qwen3-VL multimodal inference

```python
from transformers import AutoProcessor, AutoModelForVision2Seq
import torch
from PIL import Image

model_id = "Qwen/Qwen3-VL-30B-A3B-Instruct"
processor = AutoProcessor.from_pretrained(model_id)
model = AutoModelForVision2Seq.from_pretrained(
    model_id, torch_dtype=torch.bfloat16, device_map="auto"
)

image = Image.open("chart.png").convert("RGB")
messages = [
    {"role": "user", "content": [
        {"type": "image", "image": image},
        {"type": "text", "text": "Summarize this chart in 3 bullet points."},
    ]},
]
text = processor.apply_chat_template(messages, tokenize=False, add_generation_prompt=True)
inputs = processor(text=text, images=image, return_tensors="pt").to(model.device)
out = model.generate(**inputs, max_new_tokens=256)
print(processor.decode(out[0][inputs["input_ids"].shape[-1]:], skip_special_tokens=True))
```

### vLLM OpenAI-compatible server

```bash
# Serve any supported HF model with an OpenAI-compatible API
vllm serve Qwen/Qwen3-30B-A3B-Instruct-2507 \
  --tensor-parallel-size 1 \
  --max-model-len 32768 \
  --port 8000

# Then call it like the OpenAI API
curl http://localhost:8000/v1/chat/completions \
  -H "Content-Type: application/json" \
  -d '{
    "model": "Qwen/Qwen3-30B-A3B-Instruct-2507",
    "messages": [{"role": "user", "content": "Say hi in 5 words."}],
    "max_tokens": 32
  }'
```

---

## Standalone Snippet Files

Several core examples are also available as runnable standalone files in [`snippets/`](./snippets). Each listed Python file is self-contained: install the listed dependencies, then run `python snippets/<name>.py`.

| File | What it does | Key deps |
|------|--------------|---------|
| [`snippets/01_chat_generation.py`](./snippets/01_chat_generation.py) | Single-shot chat with proper template + `torch.bfloat16` | `transformers`, `torch` |
| [`snippets/02_streaming.py`](./snippets/02_streaming.py) | Token-by-token streaming via `TextIteratorStreamer` | `transformers`, `torch` |
| [`snippets/03_vllm_inference.py`](./snippets/03_vllm_inference.py) | Batched high-throughput inference with vLLM | `vllm` |
| [`snippets/04_embeddings_rerank_rag.py`](./snippets/04_embeddings_rerank_rag.py) | Two-stage retrieve-then-rerank RAG pipeline | `sentence-transformers`, `FlagEmbedding` |
| [`snippets/05_whisper_turbo.py`](./snippets/05_whisper_turbo.py) | Batched long-audio transcription with Whisper Turbo | `transformers`, `torch` |
| [`snippets/06_flux_image_gen.py`](./snippets/06_flux_image_gen.py) | Text-to-image generation with FLUX.1-dev | `diffusers`, `torch` |
| [`snippets/07_flux_kontext_edit.py`](./snippets/07_flux_kontext_edit.py) | In-context image editing with FLUX.1-Kontext | `diffusers`, `torch`, `Pillow` |
| [`snippets/08_lora_peft.py`](./snippets/08_lora_peft.py) | Wrap a causal LM with LoRA via PEFT | `peft`, `transformers`, `torch` |
| [`snippets/09_bitsandbytes_4bit.py`](./snippets/09_bitsandbytes_4bit.py) | 4-bit NF4 quantized loading | `transformers`, `bitsandbytes`, `torch` |
| [`snippets/10_llama_cpp_gguf.sh`](./snippets/10_llama_cpp_gguf.sh) | Download a GGUF and run it with `llama-cli` | `huggingface-hub`, `llama.cpp` |
| [`snippets/11_qwen3_vl_multimodal.py`](./snippets/11_qwen3_vl_multimodal.py) | Vision-language Q&A with Qwen3-VL | `transformers`, `torch`, `Pillow` |
| [`snippets/12_vllm_openai_server.sh`](./snippets/12_vllm_openai_server.sh) | Serve an HF model as an OpenAI-compatible endpoint | `vllm`, `curl` |

---

## Common Mistakes

### 1. Skipping the chat template

Using raw `tokenizer(prompt)` instead of `apply_chat_template()` breaks instruction-tuned models. They were trained on structured turns with `<|im_start|>`, `<|start_header_id|>`, or similar special tokens. Without the template, the model gets a flat string and produces worse or weirdly formatted output. Always use:

```python
tokenizer.apply_chat_template(messages, add_generation_prompt=True, return_tensors="pt")
```

### 2. Loading large models without quantization

A 70B model in fp16 needs ~140GB of VRAM. On a single 24GB GPU, use 4-bit quantization (BitsAndBytesConfig with `load_in_4bit=True`) or GGUF (Q4_K_M). You can also pick a smaller MoE like Qwen3-30B-A3B, which only activates 3B parameters per token.

### 3. Using `device_map="auto"` with multi-GPU pipelines

`device_map="auto"` works for inference, but for vLLM or TensorRT-LLM you want explicit `tensor_parallel_size=N`. Auto-sharding across GPUs through `device_map` is slow because every layer crossing triggers a sync. For production, use vLLM with `--tensor-parallel-size N`.

### 4. Forgetting `torch_dtype` and loading in fp32

By default, Transformers loads weights in fp32. That doubles memory and halves throughput. Always pass `torch_dtype=torch.bfloat16` (or `float16`) when loading inference models.

### 5. Whisper on long audio without chunking

Whisper has a 30-second window. Pass an hour-long file straight to `pipeline(...)` and you get truncated or hallucinated output. Set `chunk_length_s=30` and `return_timestamps=True`, then batch with `batch_size=8` for speed.

### 6. Treating embeddings as cosine-optional

Many embedding models (gte, bge, nomic) output vectors that should be L2-normalized before similarity search. Skip the `normalize_embeddings=True` flag in `SentenceTransformer.encode()` and recall numbers quietly drop. Always check the model card.

### 7. Using CLIP for everything visual

SigLIP2 (`google/siglip2-so400m-patch16-naflex`) is a newer image-text embedding option with flexible image sizing; compare it with CLIP on your retrieval set rather than assuming it wins every task. For captioning or VQA, use a vision-language model such as Qwen3-VL and validate on representative images.

### 8. Trusting model card benchmarks without replication

Vendor benchmarks cherry-pick. Cross-check on LMSYS Arena, OpenCompass, or Artificial Analysis before picking a model for production. A model that wins HumanEval by 5 points might lose 10 points on your real-world task distribution.

### 9. Generating without `max_new_tokens`

Some inference setups default `max_new_tokens` to a small value (like 20) or to the full context window. Set it explicitly. Also set `do_sample=False` if you want deterministic output for tests and evals.

### 10. Fine-tuning the full model when LoRA would do

Full fine-tuning of a 7B model needs ~80GB+ of VRAM and three optimizer states per parameter. LoRA or QLoRA trains 0.1% of parameters and matches full-FT on most task-specific fine-tunes. Use PEFT unless you have a clear reason not to.

### 11. Not setting `padding_side="left"` for batched generation

Decoder-only models need left padding so the last token is the real last token. Default right-padding breaks batched generation silently. Set `tokenizer.padding_side = "left"` before batching.

### 12. Ignoring eos_token and watching the model ramble

If you change the tokenizer or strip special tokens, the model may never emit EOS and ramble to `max_new_tokens`. Always verify `eos_token_id` is set on both the tokenizer and the model config, and pass it explicitly to `generate()` if you customized templates.

### 13. Treating MoE size labels as dense equivalents

Qwen3-30B-A3B has 30B total parameters but only 3B active per token. Weight memory depends mainly on total parameters and precision; throughput also depends on active parameters, context, and serving stack. Read the `A<active>` suffix carefully when budgeting.

### 14. Comparing reasoning models without thinking budget

DeepSeek-R1 and Kimi-K2-Thinking emit `<think>...</think>` blocks that consume output tokens. If you set `max_new_tokens=256`, the model spends it all on thinking and never answers. Use 4K+ for reasoning models, or strip thinking tokens from your downstream parser.

### 15. Using the original FLUX.1-dev pipeline for editing

FLUX.1-dev is primarily a text-to-image checkpoint. For instruction-based reference editing, use `FluxKontextPipeline` with FLUX.1-Kontext-dev; identity consistency still needs evaluation and is not guaranteed.

### 16. Mixing Qwen3-VL image input formats

Use the image input format in the Qwen3-VL model card and pass image objects or URLs through the processor. The processor handles resizing and visual token preparation; raw byte strings are not a substitute for supported image inputs.

---

## Contributing

PRs welcome.

Rules:
- Real models only, no vaporware
- HF links required
- Short and accurate descriptions
- No dead or deprecated models
- Prefer Apache 2.0 or MIT where possible

See [CONTRIBUTING.md](./CONTRIBUTING.md) for the full guide.

---

## License

Creative Commons Attribution 4.0 International, see [LICENSE.md](./LICENSE.md).

© Jehoshua 2026

Star the repo if it helped.
Last updated: October 2026
