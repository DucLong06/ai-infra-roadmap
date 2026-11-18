# Roadmap freshness audit
When was each resource in this roadmap last updated? This audit answers that, so you know what to trust before you spend a weekend on it.
- **Audited:** 2026-11-18 — GitHub `pushedAt` via GraphQL for all repos, upload date via yt-dlp for videos
- **115 unique repos · 9 dated videos**
- Legend: ✅ updated ≤6 months · 🟡 6–12 months · 🔴 >12 months
- 🔴 is not automatically bad: frozen research code, benchmarks, and classic teaching material (Karpathy, CS336) stay valid — the *replacement column* below tells you when it matters

## Verified conflicts (check before using the quantization section)
| Resource | Status (2026-11-18) | Use instead |
|---|---|---|
| IST-DASLab/gptq 🔴 2024-03 | Frozen research code; AutoGPTQ unmaintained | ModelCloud/GPTQModel ✅ — vLLM loads GPTQ via GPTQModel + Marlin kernel |
| mit-han-lab/llm-awq 🔴 2025-07 | AutoAWQ deprecated per its README | vllm-project/llm-compressor (AWQ incl. W4AFp8) |
| mit-han-lab/smoothquant, TinyChatEngine, tinychat-tutorial 🔴 2024 | Frozen research code | SmoothQuant ships in llm-compressor + TensorRT-LLM — read the paper, don't build the repo |
| IST-DASLab/marlin 🔴 2024-09 | Repo frozen; the kernel lives on | Marlin inside vLLM/TensorRT-LLM; note: current vLLM Marlin is 16-bit activations only, W4A8 moved to `humming` |
| Spec-Bench, arena-hard-auto, LiveCodeBench, gpqa 🔴 2024–2025 | Benchmarks frozen by design | Still comparable, but date your reports; fresher: NVIDIA/RULER ✅, lm-evaluation-harness ✅ |
| mlops-discord/gpu-optimization-workshop 🔴 2024-06 | Talks concept-valid, commands/versions outdated | Watch for concepts, re-run with current versions |
| kelseyhightower/kubernetes-the-hard-way 🔴 2025-04 | Stable by design | Still the canonical lab |

Rule of thumb for quantization: **the kernel matters more than the algorithm** — the same AWQ/GPTQ checkpoint runs several times faster on Marlin kernels (one benchmark: AWQ 68 → 741 tok/s). On Blackwell (DGX Spark), prefer FP8/NVFP4 via Model-Optimizer/TensorRT-LLM over legacy W4A16.

## Per-section resource dates

### Books & docs
| Fresh | Date | Type | Resource | Notes |
|---|---|---|---|---|
| 🔴 | 2025-05-15 | repo | [deepseek-ai/open-infra-index](https://github.com/deepseek-ai/open-infra-index) | 8140★ stars |
| 🟡 | 2026-01-22 | repo | [anthropics/original_performance_takehome](https://github.com/anthropics/original_performance_takehome) | 4225★ stars |
| 🟡 | 2026-03-14 | repo | [walidshaari/Certified-Kubernetes-Security-Specialist](https://github.com/walidshaari/Certified-Kubernetes-Security-Specialist) | 2137★ stars |
| 🟡 | 2026-04-07 | repo | [JINO-ROHIT/gpu-perf-engineering-resources](https://github.com/JINO-ROHIT/gpu-perf-engineering-resources) | 3★ stars |
| ✅ | 2026-09-12 | repo | [HazyResearch/ThunderKittens](https://github.com/HazyResearch/ThunderKittens) | 3803★ stars |
| ✅ | 2026-10-01 | repo | [bojieli/ai-infra-book](https://github.com/bojieli/ai-infra-book) | 8075★ stars |
| ✅ | 2026-10-05 | repo | [NVIDIA/nccl-tests](https://github.com/NVIDIA/nccl-tests) | 1708★ stars |
| ✅ | 2026-10-09 | repo | [red-hat-ai-dev/vLLM-zero-to-hero-overview](https://github.com/red-hat-ai-dev/vLLM-zero-to-hero-overview) | 3★ stars |
| ✅ | 2026-10-20 | repo | [deepseek-ai/DeepGEMM](https://github.com/deepseek-ai/DeepGEMM) | 9204★ stars |
| ✅ | 2026-10-21 | repo | [deepseek-ai/DeepEP](https://github.com/deepseek-ai/DeepEP) | 10455★ stars |
| ✅ | 2026-10-23 | repo | [NVIDIA/dgx-spark-playbooks](https://github.com/NVIDIA/dgx-spark-playbooks) | 1491★ stars |
| ✅ | 2026-11-05 | repo | [THUDM/slime](https://github.com/THUDM/slime) | 8842★ stars |
| ✅ | 2026-11-09 | repo | [amitshekhariitbhu/llm-inference-engineering](https://github.com/amitshekhariitbhu/llm-inference-engineering) | 513★ stars |
| ✅ | 2026-11-18 | repo | [Dao-AILab/flash-attention](https://github.com/Dao-AILab/flash-attention) | 25316★ stars |
| ✅ | 2026-11-18 | repo | [NVIDIA/cutlass](https://github.com/NVIDIA/cutlass) | 10744★ stars |
| ✅ | 2026-11-18 | repo | [flashinfer-ai/flashinfer](https://github.com/flashinfer-ai/flashinfer) | 6957★ stars |
| ✅ | 2026-11-18 | repo | [NVIDIA/Megatron-LM](https://github.com/NVIDIA/Megatron-LM) | 18434★ stars |
| ✅ | 2026-11-18 | repo | [deepspeedai/DeepSpeed](https://github.com/deepspeedai/DeepSpeed) | 43340★ stars |
| ✅ | 2026-11-18 | repo | [pytorch/torchtitan](https://github.com/pytorch/torchtitan) | 5926★ stars |
| ✅ | 2026-11-18 | repo | [verl-project/verl](https://github.com/verl-project/verl) | 24274★ stars |
| ✅ | 2026-11-18 | repo | [cfregly/ai-performance-engineering](https://github.com/cfregly/ai-performance-engineering) | 2228★ stars |
| ✅ | 2026-11-18 | repo | [rohitg00/ai-engineering-from-scratch](https://github.com/rohitg00/ai-engineering-from-scratch) | 79455★ stars |

### Evaluation: what did quantization cost you?
| Fresh | Date | Type | Resource | Notes |
|---|---|---|---|---|
| 🔴 | 2024-09-30 | repo | [idavidrein/gpqa](https://github.com/idavidrein/gpqa) | 551★ stars |
| 🔴 | 2025-06-21 | repo | [lmarena/arena-hard-auto](https://github.com/lmarena/arena-hard-auto) | 1088★ stars |
| 🔴 | 2025-07-16 | repo | [LiveCodeBench/LiveCodeBench](https://github.com/LiveCodeBench/LiveCodeBench) | 978★ stars |
| 🟡 | 2025-12-03 | repo | [huggingface/evaluation-guidebook](https://github.com/huggingface/evaluation-guidebook) | 2168★ stars |
| 🟡 | 2026-03-18 | repo | [TIGER-AI-Lab/MMLU-Pro](https://github.com/TIGER-AI-Lab/MMLU-Pro) | 435★ stars |
| ✅ | 2026-11-03 | repo | [NVIDIA/RULER](https://github.com/NVIDIA/RULER) | 1639★ stars |
| ✅ | 2026-11-04 | repo | [EleutherAI/lm-evaluation-harness](https://github.com/EleutherAI/lm-evaluation-harness) | 14500★ stars |
| ✅ | 2026-11-05 | repo | [NVIDIA-NeMo/Evaluator](https://github.com/NVIDIA-NeMo/Evaluator) | 363★ stars |
| ✅ | 2026-11-17 | repo | [google-research/google-research](https://github.com/google-research/google-research) | 39222★ stars |
| ✅ | 2026-11-18 | repo | [vllm-project/llm-compressor](https://github.com/vllm-project/llm-compressor) | 3974★ stars |
| ✅ | 2026-11-18 | repo | [ggml-org/llama.cpp](https://github.com/ggml-org/llama.cpp) | 135621★ stars |
| ✅ | 2026-11-18 | repo | [huggingface/lighteval](https://github.com/huggingface/lighteval) | 2587★ stars |
| ✅ | 2026-11-18 | repo | [UKGovernmentBEIS/inspect_ai](https://github.com/UKGovernmentBEIS/inspect_ai) | 3282★ stars |
| ✅ | 2026-11-18 | repo | [open-compass/opencompass](https://github.com/open-compass/opencompass) | 7602★ stars |
| ✅ | 2026-11-18 | repo | [vllm-project/vllm](https://github.com/vllm-project/vllm) | 97165★ stars |

### Kubernetes
| Fresh | Date | Type | Resource | Notes |
|---|---|---|---|---|
| 🔴 | 2025-04-10 | repo | [kelseyhightower/kubernetes-the-hard-way](https://github.com/kelseyhightower/kubernetes-the-hard-way) | 50729★ stars |

### LLM & agent security: courses, labs, standards, tools
| Fresh | Date | Type | Resource | Notes |
|---|---|---|---|---|
| 🟡 | 2026-02-13 | repo | [microsoft/AI-Red-Teaming-Playground-Labs](https://github.com/microsoft/AI-Red-Teaming-Playground-Labs) | 2134★ stars |
| ✅ | 2026-10-22 | repo | [anmolksachan/AI-ML-Free-Resources-for-Security-and-Prompt-Injection](https://github.com/anmolksachan/AI-ML-Free-Resources-for-Security-and-Prompt-Injection) | 827★ stars |
| ✅ | 2026-11-06 | repo | [NVIDIA/garak](https://github.com/NVIDIA/garak) | 10084★ stars |
| ✅ | 2026-11-14 | repo | [data-privacy-stack/presidio](https://github.com/data-privacy-stack/presidio) | 11947★ stars |
| ✅ | 2026-11-18 | repo | [microsoft/PyRIT](https://github.com/microsoft/PyRIT) | 4935★ stars |
| ✅ | 2026-11-18 | repo | [NVIDIA/NeMo-Guardrails](https://github.com/NVIDIA/NeMo-Guardrails) | 7524★ stars |
| ✅ | 2026-11-18 | repo | [NVIDIA/OpenShell](https://github.com/NVIDIA/OpenShell) | 21763★ stars |
| ✅ | 2026-11-18 | repo | [NVIDIA/SkillSpector](https://github.com/NVIDIA/SkillSpector) | 26752★ stars |
| ✅ | 2026-11-18 | repo | [agentgateway/agentgateway](https://github.com/agentgateway/agentgateway) | 6285★ stars |

### LLM serving metrics & benchmarking
| Fresh | Date | Type | Resource | Notes |
|---|---|---|---|---|
| ✅ | 2026-11-06 | repo | [mlcommons/inference](https://github.com/mlcommons/inference) | 1660★ stars |
| ✅ | 2026-11-17 | repo | [kubernetes-sigs/inference-perf](https://github.com/kubernetes-sigs/inference-perf) | 278★ stars |
| ✅ | 2026-11-18 | repo | [vllm-project/vllm](https://github.com/vllm-project/vllm) | 97165★ stars |
| ✅ | 2026-11-18 | repo | [vllm-project/guidellm](https://github.com/vllm-project/guidellm) | 1794★ stars |
| ✅ | 2026-11-18 | repo | [ai-dynamo/aiperf](https://github.com/ai-dynamo/aiperf) | 892★ stars |

### Looking ahead: disaggregated serving (prefill/decode split)
| Fresh | Date | Type | Resource | Notes |
|---|---|---|---|---|
| ✅ | 2026-11-18 | repo | [kvcache-ai/Mooncake](https://github.com/kvcache-ai/Mooncake) | 7071★ stars |
| ✅ | 2026-11-18 | repo | [llm-d/llm-d](https://github.com/llm-d/llm-d) | 5300★ stars |
| ✅ | 2026-11-18 | repo | [ai-dynamo/nixl](https://github.com/ai-dynamo/nixl) | 1369★ stars |
| ✅ | 2026-11-18 | repo | [LMCache/LMCache](https://github.com/LMCache/LMCache) | 12388★ stars |

### Principles & system design
| Fresh | Date | Type | Resource | Notes |
|---|---|---|---|---|
| ✅ | 2026-11-16 | repo | [DataTalksClub/mlops-zoomcamp](https://github.com/DataTalksClub/mlops-zoomcamp) | 15576★ stars |
| ✅ | 2026-11-18 | repo | [harvard-edge/cs249r_book](https://github.com/harvard-edge/cs249r_book) | 30260★ stars |

### Quantization & low-precision formats
| Fresh | Date | Type | Resource | Notes |
|---|---|---|---|---|
| 🔴 | 2024-02-25 | video | [GPU MODE — Lecture 7 Advanced Quantization](https://www.youtube.com/watch?v=1u9xUK3G4VM) |  |
| 🔴 | 2024-03-27 | repo | [IST-DASLab/gptq](https://github.com/IST-DASLab/gptq) | 2403★ stars |
| 🔴 | 2024-07-04 | repo | [mit-han-lab/TinyChatEngine](https://github.com/mit-han-lab/TinyChatEngine) | 974★ stars |
| 🔴 | 2024-07-12 | repo | [mit-han-lab/smoothquant](https://github.com/mit-han-lab/smoothquant) | 1705★ stars |
| 🔴 | 2024-09-04 | repo | [IST-DASLab/marlin](https://github.com/IST-DASLab/marlin) | 1180★ stars |
| 🔴 | 2024-09-08 | video | [MIT HAN Lab — EfficientML.ai Lecture 1 - Introduction (MIT 6.5940, Fall 2024, Zoom Recording)](https://youtube.com/playlist?list=PL80kAHvQbh-qGtNc54A6KW4i4bkTPjiRF) |  |
| 🔴 | 2024-11-05 | repo | [mit-han-lab/tinychat-tutorial](https://github.com/mit-han-lab/tinychat-tutorial) | 79★ stars |
| 🔴 | 2025-07-17 | repo | [mit-han-lab/llm-awq](https://github.com/mit-han-lab/llm-awq) | 3667★ stars |
| ✅ | 2026-09-09 | repo | [gpu-mode/lectures](https://github.com/gpu-mode/lectures) | 7097★ stars |
| ✅ | 2026-10-23 | repo | [NVIDIA/dgx-spark-playbooks](https://github.com/NVIDIA/dgx-spark-playbooks) | 1491★ stars |
| ✅ | 2026-11-18 | repo | [NVIDIA/Model-Optimizer](https://github.com/NVIDIA/Model-Optimizer) | 5625★ stars |
| ✅ | 2026-11-18 | repo | [vllm-project/llm-compressor](https://github.com/vllm-project/llm-compressor) | 3974★ stars |
| ✅ | 2026-11-18 | repo | [NVIDIA/TensorRT-LLM](https://github.com/NVIDIA/TensorRT-LLM) | 15100★ stars |
| ✅ | 2026-11-18 | repo | [pytorch/ao](https://github.com/pytorch/ao) | 3032★ stars |
| ✅ | 2026-11-18 | repo | [ggml-org/llama.cpp](https://github.com/ggml-org/llama.cpp) | 135621★ stars |
| ✅ | 2026-11-18 | repo | [ModelCloud/GPTQModel](https://github.com/ModelCloud/GPTQModel) | 1293★ stars |

### Read: the architecture decides memory and speed
| Fresh | Date | Type | Resource | Notes |
|---|---|---|---|---|
| ✅ | 2026-11-16 | repo | [amitshekhariitbhu/llm-internals](https://github.com/amitshekhariitbhu/llm-internals) | 1774★ stars |
| ✅ | 2026-11-18 | repo | [amitshekhariitbhu/ai-engineering-course](https://github.com/amitshekhariitbhu/ai-engineering-course) | 749★ stars |

### Speculative decoding
| Fresh | Date | Type | Resource | Notes |
|---|---|---|---|---|
| 🔴 | 2024-06-02 | video | [GPU MODE — Lecture 22: Hacker's Guide to Speculative Decoding in VLLM](https://www.youtube.com/watch?v=9wNAgpX6z_4) |  |
| 🔴 | 2025-04-22 | repo | [hemingkx/Spec-Bench](https://github.com/hemingkx/Spec-Bench) | 415★ stars |
| 🟡 | 2026-02-20 | repo | [SafeAILab/EAGLE](https://github.com/SafeAILab/EAGLE) | 2579★ stars |
| ✅ | 2026-07-09 | repo | [deepseek-ai/DeepSpec](https://github.com/deepseek-ai/DeepSpec) | 7321★ stars |
| ✅ | 2026-11-18 | repo | [vllm-project/speculators](https://github.com/vllm-project/speculators) | 963★ stars |
| ✅ | 2026-11-18 | repo | [NVIDIA/TensorRT-LLM](https://github.com/NVIDIA/TensorRT-LLM) | 15100★ stars |

### Tools
| Fresh | Date | Type | Resource | Notes |
|---|---|---|---|---|
| 🟡 | 2026-02-26 | repo | [natolambert/dgx-spark-setup](https://github.com/natolambert/dgx-spark-setup) | 186★ stars |
| ✅ | 2026-10-05 | repo | [engineering87/sparkfit](https://github.com/engineering87/sparkfit) | 6★ stars |
| ✅ | 2026-10-23 | repo | [NVIDIA/dgx-spark-playbooks](https://github.com/NVIDIA/dgx-spark-playbooks) | 1491★ stars |
| ✅ | 2026-11-05 | repo | [NVIDIA/open-gpu-kernel-modules](https://github.com/NVIDIA/open-gpu-kernel-modules) | 17610★ stars |
| ✅ | 2026-11-12 | repo | [XuehaiPan/nvitop](https://github.com/XuehaiPan/nvitop) | 7258★ stars |
| ✅ | 2026-11-16 | repo | [Syllo/nvtop](https://github.com/Syllo/nvtop) | 11159★ stars |
| ✅ | 2026-11-18 | repo | [vllm-project/vllm](https://github.com/vllm-project/vllm) | 97165★ stars |

### Tools (official docs)
| Fresh | Date | Type | Resource | Notes |
|---|---|---|---|---|
| ✅ | 2026-11-17 | repo | [triton-inference-server/server](https://github.com/triton-inference-server/server) | 11152★ stars |

### Video
| Fresh | Date | Type | Resource | Notes |
|---|---|---|---|---|
| 🔴 | 2024-01-15 | video | [Killer Shell — Kubernetes CKS Full Course Theory + Practice + Browser Scenarios](https://www.youtube.com/watch?v=d9xfB5qaOfg) |  |
| 🔴 | 2024-06-01 | repo | [mlops-discord/gpu-optimization-workshop](https://github.com/mlops-discord/gpu-optimization-workshop) | 346★ stars |
| 🔴 | 2024-06-09 | video | [Andrej Karpathy — Let's reproduce GPT-2 (124M)](https://youtu.be/l8pRSuU81PU) |  |
| 🔴 | 2024-08-13 | repo | [karpathy/build-nanogpt](https://github.com/karpathy/build-nanogpt) | 5655★ stars |
| 🟡 | 2026-03-31 | repo | [stanford-cs336/spring2025-lectures](https://github.com/stanford-cs336/spring2025-lectures) | 253★ stars |
| 🟡 | 2026-04-30 | repo | [elizabetht/100-days-of-inference](https://github.com/elizabetht/100-days-of-inference) | 1934★ stars |
| ✅ | 2026-09-09 | repo | [gpu-mode/lectures](https://github.com/gpu-mode/lectures) | 7097★ stars |
| ✅ | 2026-11-15 | repo | [jmaczan/tiny-vllm](https://github.com/jmaczan/tiny-vllm) | 1199★ stars |
| ✅ | 2026-11-17 | repo | [datawhalechina/zero-to-sglang](https://github.com/datawhalechina/zero-to-sglang) | 2262★ stars |

### Watch & build
| Fresh | Date | Type | Resource | Notes |
|---|---|---|---|---|
| 🔴 | 2023-01-17 | video | [Andrej Karpathy — Let's build GPT: from scratch, in code, spelled out.](https://www.youtube.com/watch?v=kCc8FmEb1nY) |  |
| 🔴 | 2024-02-20 | video | [Andrej Karpathy — Let's build the GPT Tokenizer](https://www.youtube.com/watch?v=zduSFxRajkE) |  |
| 🔴 | 2024-08-18 | repo | [karpathy/nn-zero-to-hero](https://github.com/karpathy/nn-zero-to-hero) | 25835★ stars |
| 🔴 | 2025-02-05 | video | [Andrej Karpathy — Deep Dive into LLMs like ChatGPT](https://www.youtube.com/watch?v=7xTGNNLPyMI) |  |
| 🔴 | 2025-04-24 | video | [Stanford Online — Stanford CS336 Language Modeling from Scratch ](https://www.youtube.com/watch?v=SQ3fZ1sAqXI) |  |
| 🟡 | 2026-04-07 | repo | [stanford-cs336/assignment1-basics](https://github.com/stanford-cs336/assignment1-basics) | 3197★ stars |
| ✅ | 2026-07-31 | repo | [duoan/TorchCode](https://github.com/duoan/TorchCode) | 4756★ stars |
| ✅ | 2026-09-07 | repo | [karpathy/nanochat](https://github.com/karpathy/nanochat) | 60653★ stars |
| ✅ | 2026-11-09 | repo | [rasbt/LLMs-from-scratch](https://github.com/rasbt/LLMs-from-scratch) | 108609★ stars |
| ✅ | 2026-11-18 | repo | [rohitg00/ai-engineering-from-scratch](https://github.com/rohitg00/ai-engineering-from-scratch) | 79455★ stars |

### What AI teams build on top: RAG, agents, MCP (know it to run it)
| Fresh | Date | Type | Resource | Notes |
|---|---|---|---|---|
| ✅ | 2026-07-03 | repo | [chiphuyen/aie-book](https://github.com/chiphuyen/aie-book) | 18336★ stars |
| ✅ | 2026-11-13 | repo | [meta-llama/PurpleLlama](https://github.com/meta-llama/PurpleLlama) | 4486★ stars |
| ✅ | 2026-11-14 | repo | [explodinggradients/ragas](https://github.com/explodinggradients/ragas) | 16373★ stars |
| ✅ | 2026-11-17 | repo | [huggingface/text-embeddings-inference](https://github.com/huggingface/text-embeddings-inference) | 5128★ stars |
| ✅ | 2026-11-17 | repo | [envoyproxy/ai-gateway](https://github.com/envoyproxy/ai-gateway) | 2418★ stars |
| ✅ | 2026-11-18 | repo | [rohitg00/ai-engineering-from-scratch](https://github.com/rohitg00/ai-engineering-from-scratch) | 79455★ stars |
| ✅ | 2026-11-18 | repo | [amitshekhariitbhu/ai-engineering-course](https://github.com/amitshekhariitbhu/ai-engineering-course) | 749★ stars |
| ✅ | 2026-11-18 | repo | [pgvector/pgvector](https://github.com/pgvector/pgvector) | 23723★ stars |
| ✅ | 2026-11-18 | repo | [qdrant/qdrant](https://github.com/qdrant/qdrant) | 35628★ stars |
| ✅ | 2026-11-18 | repo | [milvus-io/milvus](https://github.com/milvus-io/milvus) | 46686★ stars |
| ✅ | 2026-11-18 | repo | [modelcontextprotocol/inspector](https://github.com/modelcontextprotocol/inspector) | 11330★ stars |
| ✅ | 2026-11-18 | repo | [promptfoo/promptfoo](https://github.com/promptfoo/promptfoo) | 27421★ stars |
| ✅ | 2026-11-18 | repo | [microsoft/PyRIT](https://github.com/microsoft/PyRIT) | 4935★ stars |
| ✅ | 2026-11-18 | repo | [open-telemetry/semantic-conventions-genai](https://github.com/open-telemetry/semantic-conventions-genai) | 547★ stars |
| ✅ | 2026-11-18 | repo | [langfuse/langfuse](https://github.com/langfuse/langfuse) | 37594★ stars |

### 🙏 Acknowledgments
| Fresh | Date | Type | Resource | Notes |
|---|---|---|---|---|
| ✅ | 2026-09-09 | repo | [gpu-mode/lectures](https://github.com/gpu-mode/lectures) | 7097★ stars |
| ✅ | 2026-10-01 | repo | [bojieli/ai-infra-book](https://github.com/bojieli/ai-infra-book) | 8075★ stars |
| ✅ | 2026-11-04 | repo | [EleutherAI/lm-evaluation-harness](https://github.com/EleutherAI/lm-evaluation-harness) | 14500★ stars |
| ✅ | 2026-11-18 | repo | [rohitg00/ai-engineering-from-scratch](https://github.com/rohitg00/ai-engineering-from-scratch) | 79455★ stars |
| ✅ | 2026-11-18 | repo | [amitshekhariitbhu/ai-engineering-course](https://github.com/amitshekhariitbhu/ai-engineering-course) | 749★ stars |

### 🧪 Hands-on projects
| Fresh | Date | Type | Resource | Notes |
|---|---|---|---|---|
| ✅ | 2026-09-02 | repo | [himorishige/glm53-flash-2x-dgx-spark-recipe](https://github.com/himorishige/glm53-flash-2x-dgx-spark-recipe) | 5★ stars |
| ✅ | 2026-09-03 | repo | [Kdurazzo/dual-dgx-spark-config-guide](https://github.com/Kdurazzo/dual-dgx-spark-config-guide) | 3★ stars |
| ✅ | 2026-09-30 | repo | [tonyd2wild/GLM-5.3-Flash-NVFP4-2x-DGX-Spark](https://github.com/tonyd2wild/GLM-5.3-Flash-NVFP4-2x-DGX-Spark) | 245★ stars |
| ✅ | 2026-11-03 | repo | [ai-infra-curriculum/ai-infra-engineer-learning](https://github.com/ai-infra-curriculum/ai-infra-engineer-learning) | 1899★ stars |
| ✅ | 2026-11-04 | repo | [bidual/awesome-dgx-spark](https://github.com/bidual/awesome-dgx-spark) | 102★ stars |
| ✅ | 2026-11-08 | repo | [ai-infra-curriculum/ai-infra-performance-learning](https://github.com/ai-infra-curriculum/ai-infra-performance-learning) | 82★ stars |
| ✅ | 2026-11-16 | repo | [DataTalksClub/mlops-zoomcamp](https://github.com/DataTalksClub/mlops-zoomcamp) | 15576★ stars |
| ✅ | 2026-11-18 | repo | [DucLong06/face-detection-ml-system](https://github.com/DucLong06/face-detection-ml-system) | 42★ stars |

### 🧭 Other roadmaps & curated lists
| Fresh | Date | Type | Resource | Notes |
|---|---|---|---|---|
| 🟡 | 2026-01-02 | repo | [harish303118/MLOps-Engineering-with-Roadmap-and-Free-Learning-Resources](https://github.com/harish303118/MLOps-Engineering-with-Roadmap-and-Free-Learning-Resources) | 67★ stars |
| 🟡 | 2026-04-07 | repo | [JINO-ROHIT/gpu-perf-engineering-resources](https://github.com/JINO-ROHIT/gpu-perf-engineering-resources) | 3★ stars |
| 🟡 | 2026-05-17 | repo | [goabiaryan/awesome-gpu-engineering](https://github.com/goabiaryan/awesome-gpu-engineering) | 610★ stars |
| ✅ | 2026-08-26 | repo | [loganthorneloe/ml-roadmap](https://github.com/loganthorneloe/ml-roadmap) | 1373★ stars |
| ✅ | 2026-11-01 | repo | [patchy631/ai-engineering-hub](https://github.com/patchy631/ai-engineering-hub) | 41990★ stars |
| ✅ | 2026-11-03 | repo | [ai-infra-curriculum/ai-infra-engineer-learning](https://github.com/ai-infra-curriculum/ai-infra-engineer-learning) | 1899★ stars |
| ✅ | 2026-11-18 | repo | [rohitg00/ai-engineering-from-scratch](https://github.com/rohitg00/ai-engineering-from-scratch) | 79455★ stars |
| ✅ | 2026-11-18 | repo | [amitshekhariitbhu/ai-engineering-course](https://github.com/amitshekhariitbhu/ai-engineering-course) | 749★ stars |
| ✅ | 2026-11-18 | repo | [kamranahmedse/developer-roadmap](https://github.com/kamranahmedse/developer-roadmap) | 372297★ stars |

## Keeping this fresh
- Data files (JSON) and the collection script live in the wiki: `graphs/ai-infra-roadmap/plan-{raw,repos,vids}.json` + `collect-freshness.py` (GitHub GraphQL + yt-dlp, resume-safe)
- Re-run roughly monthly; re-check 🟡 items before studying them
- A 🔴 *tool* (not teaching material or a frozen benchmark) deserves a README/status check for a maintained replacement before you invest time
