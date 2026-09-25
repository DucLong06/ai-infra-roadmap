# Lộ trình AI Infrastructure

[English](README.md) · **Tiếng Việt**

> **Lưu ý trước khi đọc:** tôi chưa học hết tất cả những gì trong roadmap này. Tôi đang cố gắng tổng hợp, đặt mục tiêu và học dần theo nó. Nếu có gì sai sót hoặc bạn có gợi ý tốt hơn, hãy mở issue hoặc PR để hỗ trợ tôi. Tôi cảm ơn mọi sự giúp đỡ.

> Lộ trình học cho kỹ sư đi từ DevOps/MLOps lên **phần cứng GPU, AI networking, security, LLMOps và AI Data Center (AIDC)**.
> Viết bởi một kỹ sư Việt Nam đang đi đúng con đường này. Tài liệu được nhóm theo định dạng — **YouTube, Udemy, LinkedIn Learning, NVIDIA DLI, docs chính thức, sách open-access** — để bạn chọn cách học phù hợp. Mọi link đều được kiểm tra tại thời điểm viết.
> Thuật ngữ kỹ thuật giữ tiếng Anh.



---

## Mục lục

- [Lộ trình AI Infrastructure](#lộ-trình-ai-infrastructure)
  - [Mục lục](#mục-lục)
  - [📖 Cách dùng lộ trình](#-cách-dùng-lộ-trình)
  - [🎯 Lộ trình tối thiểu](#-lộ-trình-tối-thiểu)
  - [🗺 Tổng quan](#-tổng-quan)
  - [1. Nền tảng: Linux, Git, Python, network cơ bản, Docker](#1-nền-tảng-linux-git-python-network-cơ-bản-docker)
    - [Linux \& command line](#linux--command-line)
    - [Git](#git)
    - [Python cho infra](#python-cho-infra)
    - [Network cơ bản](#network-cơ-bản)
    - [Docker](#docker)
  - [2. DevOps \& Platform Engineering](#2-devops--platform-engineering)
    - [Kubernetes](#kubernetes)
    - [Infrastructure as Code: Terraform, Ansible](#infrastructure-as-code-terraform-ansible)
    - [CI/CD \& GitOps: Jenkins, GitLab CI, ArgoCD](#cicd--gitops-jenkins-gitlab-ci-argocd)
    - [Observability: Prometheus, Grafana, OpenTelemetry](#observability-prometheus-grafana-opentelemetry)
  - [3. MLOps](#3-mlops)
    - [Nguyên lý \& thiết kế hệ thống](#nguyên-lý--thiết-kế-hệ-thống)
    - [Tool (docs chính thức)](#tool-docs-chính-thức)
    - [Khoá học có hệ thống (tiếng Việt)](#khoá-học-có-hệ-thống-tiếng-việt)
  - [3.5. Nền tảng LLM: transformer, token, KV cache, MoE](#35-nền-tảng-llm-transformer-token-kv-cache-moe)
    - [Xem \& tự build](#xem--tự-build)
    - [Đọc: kiến trúc quyết định memory và tốc độ](#đọc-kiến-trúc-quyết-định-memory-và-tốc-độ)
  - [4. GPU \& phần cứng NVIDIA](#4-gpu--phần-cứng-nvidia)
    - [Video](#video)
    - [Sách \& docs](#sách--docs)
    - [Tool](#tool)
  - [5. AI Networking: interconnect, RDMA, NCCL](#5-ai-networking-interconnect-rdma-nccl)
    - [Video](#video-1)
    - [Sách \& docs](#sách--docs-1)
  - [6. Security cho AI platform](#6-security-cho-ai-platform)
    - [Video](#video-2)
    - [Sách \& docs](#sách--docs-2)
  - [7. LLMOps \& inference quy mô lớn](#7-llmops--inference-quy-mô-lớn)
    - [Video](#video-3)
    - [Sách \& docs](#sách--docs-3)
    - [Quantization \& các format low-precision](#quantization--các-format-low-precision)
    - [Evaluation: quantization làm mất bao nhiêu?](#evaluation-quantization-làm-mất-bao-nhiêu)
    - [Speculative decoding](#speculative-decoding)
    - [Metric \& benchmark cho LLM serving](#metric--benchmark-cho-llm-serving)
    - [Nhìn về phía trước: disaggregated serving (tách prefill/decode)](#nhìn-về-phía-trước-disaggregated-serving-tách-prefilldecode)
  - [8. AI Data Center (AIDC)](#8-ai-data-center-aidc)
    - [Video](#video-4)
    - [Sách \& docs](#sách--docs-4)
  - [🎓 Chứng chỉ](#-chứng-chỉ)
  - [🧪 Dự án thực hành](#-dự-án-thực-hành)
  - [🧭 Roadmap \& danh mục khác](#-roadmap--danh-mục-khác)
  - [🙏 Lời cảm ơn](#-lời-cảm-ơn)
  - [🤝 Contributing](#-contributing)

---

## 📖 Cách dùng lộ trình

1. Mục 1–3 là nền. Mục 3.5 (Nền tảng LLM) là cây cầu mà mục 4 và mục 7 mặc định bạn đã qua. Mục 4–8 có thể học song song tuỳ công việc. Đã biết MLOps thì vào thẳng mục 3.5.
2. Mỗi mục có **Học** (xem/đọc) → **Làm** (lab) → **Milestone** (sản phẩm để chứng minh). Chưa có milestone = chưa xong.
3. Ký hiệu: 🆓 miễn phí · 💰 trả phí · 🎥 video · 📕 sách · 📄 docs/paper · 🧪 lab · ⭐ bắt đầu từ đây.
4. Viết journal bằng tiếng Anh sau mỗi lab. Đó chính là portfolio của bạn.
5. Ít thời gian? Làm **Lộ trình tối thiểu** bên dưới trước. Phần còn lại là thư viện tra cứu.

---

## 🎯 Lộ trình tối thiểu

Roadmap đầy đủ cố tình rộng, và rất dễ học rộng mà không sâu, hoặc bỏ dở giữa chừng. Nếu mục tiêu của bạn là *chạy và vận hành LLM inference trên phần cứng GPU*, hãy làm 13 thứ này theo thứ tự và coi phần còn lại là tài liệu tra cứu. Mỗi mục có một sản phẩm cụ thể; chưa có thì chưa đi tiếp.

![Lộ trình tối thiểu: 13 chặng từ Kubernetes tới threat model](assets/minimum-path.png)

| # | Tài nguyên (mục) | Sản phẩm bạn phải có |
|---|---|---|
| 1 | Kubernetes docs tutorials → Kubernetes The Hard Way (mục 2) | một cluster bạn tự dựng bằng tay |
| 2 | Made With ML (mục 3) | một model được serve kèm monitoring |
| 3 | 3Blue1Brown chapter 5–6 → Karpathy "Let's build GPT" → *AI Infrastructure* (Bojie Li) ch.2 model architecture (mục 3.5) | GPT nhỏ của chính bạn có KV cache, và số byte KV mỗi token cho GQA vs MLA tính tay |
| 4 | Bài giảng PMPP (Izzat El Hajj) + GPU MODE Lecture 8 "CUDA Performance Checklist" (mục 4) | một kernel matmul đã profile bằng `ncu` và roofline của nó |
| 5 | *AI Infrastructure* (Bojie Li) ch.3 workloads, ch.4 accelerator & memory hierarchy, ch.8 inference optimization (mục 4, 7) | memory budget của một model (weights + KV cache) tính tay |
| 6 | MIT 6.5940 Lecture 5–6 "Quantization I & II" + Lecture 13 "LLM Deployment Techniques" (mục 7) | giải thích được W8A8 vs W4A16 vs NVFP4 và vì sao group size khác nhau |
| 7 | How to Scale Your Model (Scaling Book), các chương inference (mục 7) | suy ra được TTFT và TPOT từ bandwidth, batch size và kích thước model |
| 8 | vLLM docs: Optimization & Tuning, Conserving memory, Quantization, Metrics (mục 7) | một `vllm serve` đã tune, xuất metric Prometheus |
| 9 | DeepLearning.AI × Red Hat "Fast & Efficient LLM Inference with vLLM" (mục 7) | bạn đã tự quantize, serve và benchmark một model |
| 10 | lm-evaluation-harness chạy trên model đã quantize của bạn (mục 7) | một con số cho biết quantization lấy mất bao nhiêu |
| 11 | Loạt blog NVIDIA "LLM Inference Benchmarking" + `vllm bench serve` (mục 7) | đồ thị throughput vs p99 TTFT/TPOT kèm goodput theo một SLO |
| 12 | NCCL user guide + nccl-tests trên NIC của bạn (mục 5) | bus bandwidth `all_reduce` đo được và transport NCCL đã chọn |
| 13 | Container Security (Liz Rice) + OWASP Top 10 for LLM (mục 6) | một trang threat model cho serving stack của bạn |

Sau 13 mục này, mục 8 (AI Data Center) và các chứng chỉ là bước tiếp theo tự nhiên.

---

## 🗺 Tổng quan

![Tổng quan lộ trình AI Infrastructure](assets/roadmap-overview.png)

---

## 1. Nền tảng: Linux, Git, Python, network cơ bản, Docker

*Mọi thứ phía sau chạy trên Linux, quản lý bằng Git, tự động hoá bằng Python và nói chuyện qua TCP/IP.*

### Linux & command line
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ The Linux Command Line (William Shotts) | 🆓📕 | https://linuxcommand.org/tlcl.php |
| MIT — The Missing Semester of Your CS Education | 🆓🎥 | https://missing.csail.mit.edu/ |
| Linux Foundation LFS101 — Introduction to Linux | 🆓🎥 | https://training.linuxfoundation.org/training/introduction-to-linux/ |
| Operating Systems: Three Easy Pieces (OSTEP) | 🆓📕 | https://pages.cs.wisc.edu/~remzi/OSTEP/ |
| Dive into Systems | 🆓📕 | https://diveintosystems.org/ |
| LinkedIn Learning — Strategic Linux for Network Professionals: Security, Monitoring, and Automation | 💰🎥 | https://www.linkedin.com/learning/ (tìm theo tên) |

### Git
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ Pro Git | 🆓📕 | https://git-scm.com/book/en/v2 |
| Learn Git Branching (tương tác) | 🆓🧪 | https://learngitbranching.js.org/ |

### Python cho infra
| Tài nguyên | Loại | Link |
|---|---|---|
| Python official tutorial | 🆓📄 | https://docs.python.org/3/tutorial/ |
| Machine Learning Engineering (Andriy Burkov) | 🆓📕 | http://www.mlebook.com/ |
| The Hundred-Page Machine Learning Book | 🆓📕 | https://themlbook.com/ |

### Network cơ bản
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ Computer Networks: A Systems Approach (Peterson & Davie) | 🆓📕 | https://book.systemsapproach.org/ |
| Kurose & Ross — video bài giảng free theo sách *Computer Networking: A Top-Down Approach* | 🆓🎥 | https://gaia.cs.umass.edu/kurose_ross/index.php |
| Computer Networking: A Top-Down Approach (sách) | 💰📕 | https://www.pearson.com/en-us/subject-catalog/p/computer-networking/P200000003334 |
| Practical Networking (YouTube) | 🆓🎥 | https://www.youtube.com/@PracticalNetworking |
| High Performance Browser Networking (Ilya Grigorik) | 🆓📕 | https://hpbn.co/ |
| LinkedIn Learning — Networking Foundations: Networking Basics (Kevin Wallace) | 💰🎥 | https://www.linkedin.com/learning/networking-foundations-networking-basics |

### Docker
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ Docker — Get Started | 🆓📄 | https://docs.docker.com/get-started/ |
| TechWorld with Nana — Docker / Kubernetes / DevOps (YouTube) | 🆓🎥 | https://www.youtube.com/@TechWorldwithNana |
| KodeKloud (YouTube) | 🆓🎥 | https://www.youtube.com/@KodeKloud |

🧪 **Làm**: dựng 1 VM Ubuntu, cài Docker, container hoá 1 API Python nhỏ sau Nginx, dùng `tcpdump` và `ss -tulpn` để thấy gói tin đi đâu.

---

## 2. DevOps & Platform Engineering

*Kubernetes là hệ điều hành của mọi AI platform hiện nay. Đây là bộ tool bạn sẽ dùng lại ở mọi mục sau.*

### Kubernetes
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ Kubernetes docs & tutorials | 🆓📄 | https://kubernetes.io/docs/tutorials/ |
| Linux Foundation LFS158 — Introduction to Kubernetes | 🆓🎥 | https://training.linuxfoundation.org/training/introduction-to-kubernetes/ |
| Kubernetes The Hard Way (Kelsey Hightower) | 🆓🧪 | https://github.com/kelseyhightower/kubernetes-the-hard-way |
| Killercoda — lab trên trình duyệt | 🆓🧪 | https://killercoda.com/ |
| KodeKloud — khoá học & lab | 🆓/💰🎥🧪 | https://www.kodekloud.com/ |
| Udemy — Certified Kubernetes Administrator (CKA) with Practice Tests (Mumshad Mannambeth) | 💰🎥 | https://www.udemy.com/course/certified-kubernetes-administrator-with-practice-tests/ |
| LinkedIn Learning — Kubernetes: Provisioning for Infrastructure as Code (Carlos Nunez) | 💰🎥 | https://www.linkedin.com/learning/kubernetes-provisioning-for-infrastructure-as-code |
| LinkedIn Learning — Getting Started with Kubernetes (learning path) | 💰🎥 | https://www.linkedin.com/learning/paths/getting-started-with-kubernetes |
| roadmap.sh — Kubernetes | 🆓📄 | https://roadmap.sh/kubernetes |

### Infrastructure as Code: Terraform, Ansible
| Tài nguyên | Loại | Link |
|---|---|---|
| Terraform tutorials | 🆓📄🧪 | https://developer.hashicorp.com/terraform/tutorials |
| Ansible docs | 🆓📄 | https://docs.ansible.com/ |

### CI/CD & GitOps: Jenkins, GitLab CI, ArgoCD
| Tài nguyên | Loại | Link |
|---|---|---|
| Jenkins docs | 🆓📄 | https://www.jenkins.io/doc/ |
| ⭐ ArgoCD docs | 🆓📄 | https://argo-cd.readthedocs.io/ |
| CNCF (YouTube) — KubeCon talks | 🆓🎥 | https://www.youtube.com/@cncf |

### Observability: Prometheus, Grafana, OpenTelemetry
| Tài nguyên | Loại | Link |
|---|---|---|
| Prometheus docs | 🆓📄 | https://prometheus.io/docs/introduction/overview/ |
| Grafana docs | 🆓📄 | https://grafana.com/docs/ |
| OpenTelemetry docs | 🆓📄 | https://opentelemetry.io/docs/ |
| ⭐ Google SRE books | 🆓📕 | https://sre.google/books/ |

🧪 **Làm**: cluster k3s/kubeadm 2–3 node → Helm → ArgoCD sync từ Git → kube-prometheus-stack → dashboard + alert cho 1 service.
**Milestone**: một repo Git mà mỗi lần `git push` là ArgoCD tự động deploy lên cluster của bạn, kèm dashboard Grafana có ít nhất một alert hoạt động cho một service đang chạy.

---

## 3. MLOps

*Từ notebook đến hệ thống ML chạy tự động, có version, monitoring và vòng lặp retrain. Đây là nền trực tiếp cho LLMOps.*

### Nguyên lý & thiết kế hệ thống
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ Made With ML (Goku Mohandas) | 🆓📕🧪 | https://madewithml.com/ |
| ⭐ Machine Learning Systems (Vijay Janapa Reddi) | 🆓📕 | https://mlsysbook.ai/ |
| ml-ops.org — nguyên lý & maturity model | 🆓📄 | https://ml-ops.org/ |
| Google — Practitioners Guide to MLOps | 🆓📄 | https://cloud.google.com/resources/mlops-whitepaper |
| Full Stack Deep Learning | 🆓🎥 | https://fullstackdeeplearning.com/ |
| DataTalks.Club — MLOps Zoomcamp (khoá + YouTube) | 🆓🎥🧪 | https://github.com/DataTalksClub/mlops-zoomcamp · https://www.youtube.com/@DataTalksClub |
| LinkedIn Learning — MLOps Essentials for Developers and AI Engineers: Tools, Pipelines, Security (learning path) | 💰🎥 | https://www.linkedin.com/learning/paths/mlops-essentials-for-developers-and-ai-engineers-tools-pipelines-security |
| Udemy — The Complete Guide to AI Infrastructure: Zero to Hero | 💰🎥🧪 | https://www.udemy.com/course/complete-guide-ai-infrastructure/ |
| roadmap.sh — MLOps | 🆓📄 | https://roadmap.sh/mlops |

### Tool (docs chính thức)
| Tool | Vai trò | Link |
|---|---|---|
| MLflow | experiment tracking, model registry | https://mlflow.org/docs/latest/index.html |
| DVC | data/model versioning | https://dvc.org/doc |
| Apache Airflow | orchestration | https://airflow.apache.org/docs/ |
| Kubeflow | ML platform trên Kubernetes | https://www.kubeflow.org/docs/ |
| Feast | feature store | https://feast.dev/ |
| Ray | distributed training/serving | https://docs.ray.io/ |
| KServe | model serving trên Kubernetes | https://kserve.github.io/website/ |
| Triton Inference Server | serving đa framework trên GPU | https://github.com/triton-inference-server/server |
| Evidently | drift & data-quality monitoring | https://www.evidentlyai.com/ |

### Khoá học có hệ thống (tiếng Việt)
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ Full Stack Data Science — khoá MLOps/LLMOps theo cohort, đồ án chấm theo rubric | 💰🎥🧪 | https://fullstackdatascience.com/ |

🧪 **Làm**: train → MLflow registry → KServe/Triton → Evidently drift → alert → retrain tự động → canary.
**Milestone**: một repo train model, đăng ký vào MLflow, serve trên Kubernetes, phát hiện data drift bằng Evidently, và tự động retrain + redeploy (canary) khi có drift — toàn bộ chạy không cần thao tác tay.

---

## 3.5. Nền tảng LLM: transformer, token, KV cache, MoE

*Cây cầu nối giữa MLOps và mọi thứ phía sau. Bạn không thể tính KV cache, chọn cách parallelism, đọc config quantization hay giải thích vì sao decode bị memory-bound nếu chưa biết transformer tính gì cho mỗi token và phải giữ gì trong bộ nhớ. Mục 4 và mục 7 mặc định bạn đã học mục này.*

**Mục tiêu**: cho `config.json` của bất kỳ model nào, tự tính tay được tổng số tham số và số tham số active, FLOPs mỗi token, dung lượng weight ở BF16 / FP8 / NVFP4 và số byte KV cache mỗi token, và giải thích được điều gì thay đổi giữa prefill và decode.

### Xem & tự build
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ 3Blue1Brown — Chapter 5 "But what is a GPT?" và Chapter 6 "Attention in transformers, step by step" (trực giác trước) | 🆓🎥 | https://www.3blue1brown.com/lessons/gpt/ · https://www.3blue1brown.com/lessons/attention/ |
| Andrej Karpathy — Deep Dive into LLMs like ChatGPT (3,5 giờ, toàn bộ stack: data pretraining, tokenization, mạng neural, SFT, RL) | 🆓🎥 | https://www.youtube.com/watch?v=7xTGNNLPyMI |
| ⭐ Andrej Karpathy — Neural Networks: Zero to Hero, Lecture 7 "Let's build GPT: from scratch, in code, spelled out" và Lecture 8 "Let's build the GPT Tokenizer" (bắt đầu từ Lecture 1 nếu bạn chưa quen backpropagation) | 🆓🎥🧪 | https://www.youtube.com/watch?v=kCc8FmEb1nY · https://www.youtube.com/watch?v=zduSFxRajkE · https://github.com/karpathy/nn-zero-to-hero |
| Tương tác: Transformer Explainer (GPT-2 chạy thật trong trình duyệt) · LLM Visualization (Brendan Bycroft, mô phỏng 3D một bước inference cho một token) | 🆓🧪 | https://poloclub.github.io/transformer-explainer/ · https://bbycroft.net/llm |
| ⭐ Stanford CS336 — Lecture 1 "Overview and Tokenization", Lecture 2 "PyTorch, Resource Accounting", Lecture 3 "Architectures, Hyperparameters", Lecture 4 "Mixture of Experts", cùng Assignment 1 "Basics" (tự viết BPE tokenizer, transformer và AdamW). Đây là lựa chọn học sâu, và cùng khoá này học tiếp ở mục 4 và mục 7 | 🆓🎥🧪 | https://cs336.stanford.edu/ · https://www.youtube.com/watch?v=SQ3fZ1sAqXI · https://github.com/stanford-cs336/assignment1-basics |
| Build a Large Language Model (From Scratch) (Sebastian Raschka) — sách trả phí, code miễn phí. Các notebook bonus tự cài KV cache (`ch04/03_kv-cache`), GQA (`ch04/04_gqa`), MLA (`ch04/05_mla`), sliding-window attention, MoE (`ch04/07_moe`), phân tích FLOPs, và Llama 3 / Qwen3 / Gemma từ đầu | 💰📕 · 🆓🧪 | https://github.com/rasbt/LLMs-from-scratch |

### Đọc: kiến trúc quyết định memory và tốc độ
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ AI Infrastructure (Bojie Li) — ch.1 (§1.3 ước lượng một lần chạy model bằng vài con số) và ch.2 model architecture (§2.2 prefill, decode và tái sử dụng state; §2.3 multi-head attention và KV sharing, MLA, sliding window, linear và hybrid attention, "mỗi token lưu bao nhiêu, mỗi bước decode đọc bao nhiêu"; §2.4 expert routing và lượng weight đọc mỗi batch) | 🆓📕 | https://bojieli.github.io/ai-infra-book/en/ |
| ⭐ EleutherAI — Transformer Math 101 (FLOPs training ≈ 6 × số tham số × số token; memory cho weight, optimizer state và activation) · kipply — Transformer Inference Arithmetic (kích thước KV cache, khi nào decode bị memory-bound, một mô hình latency đơn giản) | 🆓📄 | https://blog.eleuther.ai/transformer-math/ · https://kipp.ly/transformer-inference-arithmetic/ |
| Sebastian Raschka — The Big LLM Architecture Comparison (từ GPT-2 tới DeepSeek-V3, Llama 4, Qwen3, GLM: RoPE, GQA, MLA, MoE, vị trí normalization) và LLM Architecture Gallery | 🆓📄 | https://magazine.sebastianraschka.com/p/the-big-llm-architecture-comparison · https://sebastianraschka.com/llm-architecture-gallery/ |
| Jay Alammar — The Illustrated Transformer · Harvard NLP — The Annotated Transformer (paper gốc dưới dạng khoảng 400 dòng code chạy được) | 🆓📄🧪 | https://jalammar.github.io/illustrated-transformer/ · https://nlp.seas.harvard.edu/annotated-transformer/ |
| Dive into Deep Learning — Chapter 11 "Attention Mechanisms and Transformers" (sách tham chiếu kèm code) | 🆓📕 | https://d2l.ai/chapter_attention-mechanisms-and-transformers/ |
| Outcome School (Amit Shekhar) — AI Engineering Course, Module 3 "Generative AI and the Transformer Architecture" và Module 5 "Modern LLM Architecture", cùng danh mục đi kèm `llm-internals`: các bài blog viết dễ hiểu về BPE, toán đằng sau Q/K/V và hệ số √dₖ, causal masking, RoPE, MoE, GQA, sliding-window attention, attention sink, FlashAttention và DeepSeek-V4. Hợp để đọc lướt lần đầu hoặc ôn nhanh; không có code hay lab | 🆓📄🎥 | https://github.com/amitshekhariitbhu/ai-engineering-course · https://github.com/amitshekhariitbhu/llm-internals |
| Paper nên biết tên: Attention Is All You Need · multi-query attention (Shazeer) · GQA · RoPE (RoFormer) · DeepSeek-V2 (MLA: KV cache nhỏ hơn 93 % so với DeepSeek 67B) · Mixtral of Experts (47B tham số tổng, 13B active) · scaling laws (Kaplan) và Chinchilla (training tối ưu theo compute) | 🆓📄 | https://arxiv.org/abs/1706.03762 · https://arxiv.org/abs/1911.02150 · https://arxiv.org/abs/2305.13245 · https://arxiv.org/abs/2104.09864 · https://arxiv.org/abs/2405.04434 · https://arxiv.org/abs/2401.04088 · https://arxiv.org/abs/2001.08361 · https://arxiv.org/abs/2203.15556 |
| Post-training trong một cuốn sách: RLHF Book (Nathan Lambert, đọc miễn phí online) — SFT, reward model, DPO, RL; "rollout" và "policy update" nghĩa là gì khi chúng xuất hiện dưới dạng workload hạ tầng | 🆓📕 | https://rlhfbook.com/ |

🧪 **Làm**
1. Xem 3Blue1Brown chapter 5–6, rồi code theo Karpathy "Let's build GPT" và train model mức ký tự trên một đoạn text nhỏ.
2. Thêm KV cache vào vòng lặp generate. Đo tokens/s có và không có KV cache khi sinh 256 và 2.048 token. Tham chiếu: `ch04/03_kv-cache` của Raschka.
3. Thay multi-head attention bằng GQA (Raschka `ch04/04_gqa`) và tính số byte KV mỗi token trước và sau.
4. Kiểm tra tokenizer: đếm số token của cùng một đoạn văn bằng tiếng Anh và tiếng Việt với tokenizer của model bạn đang serve (`AutoTokenizer.from_pretrained(...)`). Tỷ lệ đó là hệ số chi phí thật: nhiều token hơn nghĩa là nhiều KV cache hơn, TTFT dài hơn và tốn tiền hơn cho cùng một nội dung.
5. Bài tập trên giấy: mở `config.json` của một model dense (ví dụ Llama-3.1-8B) và một model MoE dùng MLA (ví dụ DeepSeek-V3, hoặc model bạn đang serve). Tính tổng số tham số và số tham số active, FLOPs mỗi token sinh ra (khoảng 2 × số tham số active), dung lượng weight ở BF16 / FP8 / NVFP4, và số byte KV cache mỗi token cho MHA vs GQA vs MLA. Đối chiếu với https://elinx.github.io/llm-mem-calculator/ và với log của vLLM lúc khởi động.
6. Prefill vs decode: đo thời gian một forward pass cho prompt 2.048 token so với 256 bước decode một token trên GPU của bạn, rồi giải thích chênh lệch tokens/s bằng arithmetic intensity. Đây là cây cầu sang mục 4.

**Milestone**: một repo hoặc notebook gồm (1) GPT nhỏ của bạn với vòng lặp generate có KV cache chạy được và tốc độ tăng đo được, và (2) một trang "infra model card" cho model bạn thực sự serve: tổng số tham số và số tham số active, số layer, loại attention (MHA / GQA / MLA) và số KV head, số byte KV mỗi token ở BF16 và FP8, dung lượng weight ở BF16 / FP8 / NVFP4, và FLOPs mỗi token, mỗi con số đều tính tay và kiểm lại bằng số đo. Sau mục này, video "Let's reproduce GPT-2" của Karpathy ở mục 7 cho thấy cùng model đó ở tầng hệ thống.

---

## 4. GPU & phần cứng NVIDIA

*Phần mà đa số roadmap MLOps bỏ qua. Học NVIDIA trước; các hãng khác theo cùng mô hình (SIMT, memory hierarchy, interconnect).*

**Mục tiêu**: với bất kỳ workload nào, trả lời được *chuyển cái gì, bao nhiêu, mấy lần, qua đâu, ai phải đợi* — và giải thích vì sao LLM inference bị memory-bound.

### Video
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ Kênh chính thức sách PMPP — bài giảng GPU Computing của Izzat El Hajj | 🆓🎥 | https://www.youtube.com/@pmpp-book |
| ⭐ GPU MODE (YouTube + repo lecture) | 🆓🎥 | https://www.youtube.com/@GPUMODE · https://github.com/gpu-mode/lectures |
| freeCodeCamp — khoá luyện NCA-AIIO (4 giờ) | 🆓🎥 | https://www.freecodecamp.org/news/pass-the-nvidia-certified-associate-ai-infrastructure-and-operations-certification-exam/ |
| NVIDIA Developer (YouTube) & GTC on-demand | 🆓🎥 | https://www.youtube.com/@NVIDIADeveloper · https://www.nvidia.com/gtc/ |
| OLCF CUDA Training Series (Oak Ridge) | 🆓🎥🧪 | https://www.olcf.ornl.gov/cuda-training-series/ |
| MIT 6.5940 — TinyML & Efficient AI Computing (Song Han): bản ghi Fall 2024; khoá mới Fall 2026. Các bài giảng quantization được liệt kê ở mục 7 | 🆓🎥🧪 | https://efficientml.ai · https://hanlab.mit.edu/courses/2024-fall-65940 · https://hanlab.mit.edu/courses/2026-fall-65940 |
| CMU — Deep Learning Systems | 🆓🎥 | https://dlsyscourse.org/ |
| Stanford CS336 — Language Modeling from Scratch: Lecture 5 GPUs, 6 kernels/Triton, 7–8 parallelism, 10 inference; Assignment 2 "Systems" (kernel Triton, FlashAttention, DDP, optimizer sharding) | 🆓🎥🧪 | https://cs336.stanford.edu/ · https://github.com/stanford-cs336 |
| CMU 15-442/642 — Machine Learning Systems (Tianqi Chen): assignment công khai về tối ưu GEMM trên Blackwell và distributed training | 🆓📄🧪 | https://mlsyscourse.org/ · https://github.com/mlsyscourse |
| NVIDIA DLI — Fundamentals of Accelerated Computing with CUDA C/C++ | 💰🎥🧪 | https://learn.nvidia.com/ |
| Udemy — CUDA GPU Programming Beginner To Advanced | 💰🎥 | https://www.udemy.com/course/cuda-gpu-programming-beginner-to-advanced/ |
| Udemy — Mastering Parallel programming with CUDA platform | 💰🎥 | https://www.udemy.com/course/mastering-parallel-programming-with-cuda-platform/ |
| Udemy — NVIDIA-Certified Professional: AI Infrastructure (NCP-AII) | 💰🎥 | https://www.udemy.com/course/ncp-aii-nvidia-certified-professional-ai-infrastructure/ |

### Sách & docs
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ AI Infrastructure (Bojie Li) — sách open-source, bản tiếng Anh: ch.3 workloads (§3.1.1 prefill và decode), ch.4 accelerator architecture (§4.2.4 low precision, §4.3 memory hierarchy, §4.3.1 GPU memory và unified memory), ch.5 operators & runtime (§5.3.3 FlashAttention: tiling và online softmax) | 🆓📕 | https://bojieli.github.io/ai-infra-book/en/ · https://github.com/bojieli/ai-infra-book/tree/main/book-en |
| Programming Massively Parallel Processors, 4th ed. (Hwu, Kirk, El Hajj) | 💰📕 | https://shop.elsevier.com/books/programming-massively-parallel-processors/hwu/978-0-323-91231-0 |
| CUDA C++ Programming Guide | 🆓📄 | https://docs.nvidia.com/cuda/cuda-c-programming-guide/index.html |
| An Even Easier Introduction to CUDA (NVIDIA blog) | 🆓📄 | https://developer.nvidia.com/blog/even-easier-introduction-cuda/ |
| GPU Gems 1–3 | 🆓📕 | https://developer.nvidia.com/gpugems/gpugems/contributors |
| NVIDIA Blackwell architecture | 🆓📄 | https://resources.nvidia.com/en-us-blackwell-architecture |
| Horace He — Making Deep Learning Go Brrrr From First Principles (compute-bound vs memory-bound vs overhead-bound) | 🆓📄 | https://horace.io/brrr_intro.html |
| Modal — GPU Glossary ("GPU documentation for humans": SM, warp, HBM, tensor core, CUDA graph) | 🆓📄 | https://modal.com/gpu-glossary |

### Tool
| Tool | Link |
|---|---|
| Nsight Systems / Nsight Compute | https://developer.nvidia.com/nsight-systems |
| DCGM + dcgm-exporter | https://docs.nvidia.com/datacenter/dcgm/latest/index.html |
| NVIDIA GPU Operator (driver, device plugin, MIG / time-slicing / MPS) | https://docs.nvidia.com/datacenter/cloud-native/gpu-operator/latest/index.html |
| Kueue (job queueing, GPU quota) | https://kueue.sigs.k8s.io/ |
| DGX Spark docs & playbooks (mã nguồn playbook trên GitHub) | https://docs.nvidia.com/dgx/dgx-spark/ · https://build.nvidia.com/spark · https://github.com/NVIDIA/dgx-spark-playbooks |

🧪 **Làm**
1. `nvidia-smi -q`, `nvidia-smi topo -m`, `lspci -tv` → tự vẽ sơ đồ CPU–GPU–memory–NIC của máy bạn.
2. DCGM exporter → Grafana: SM active, DRAM active, tensor-core active.
3. Viết 1 kernel matmul, profile bằng `nsys`/`ncu`, tính arithmetic intensity, vẽ roofline.
4. Chạy vLLM model 8B, đo tokens/s từ batch 1 → 32, giải thích bằng roofline.
5. Tính tay: 70B FP8 + KV cache 32k context — có vừa GPU của bạn không? Đối chiếu với calculator: https://elinx.github.io/llm-mem-calculator/ (hỗ trợ GQA, MLA, MoE) hoặc https://github.com/engineering87/sparkfit (riêng cho DGX Spark).

> ⚠️ **Unified memory là một cuộc chơi khác (GB10 / DGX Spark, Grace Hopper, Grace Blackwell).** Trên GPU rời, cấp phát quá tay thì CUDA báo OOM và chỉ process của bạn chết. Trên GB10, CPU và GPU dùng chung một pool LPDDR5x 128 GB *không có carve-out cố định* (DGX Spark Porting Guide), nên cấp phát cứ thành công cho tới khi chính driver hết bộ nhớ — và lúc đó cả máy có thể treo: không OOM-kill, không kernel panic, mất SSH, phải rút điện. OOM killer của Linux và giới hạn cgroup không nhìn thấy CUDA memory đã pin, nên không cứu được bạn. Tôi học điều này qua thực tế; rất ít tài liệu nói. Những quy tắc mà docs NVIDIA và cộng đồng cùng đi đến:
> - `nvidia-smi` in `Memory-Usage: Not Supported` trên GB10; theo dõi `/proc/meminfo` hoặc `free -h` thay thế. `cudaMemGetInfo` báo thiếu bộ nhớ trống (NVIDIA Known Issues, KB 5728).
> - Page cache bị tính vào bộ nhớ CUDA nhìn thấy (một phép đo của cộng đồng: ghi một file 60 GB làm CUDA-free giảm từ ~103 xuống ~42 GiB trong khi `MemAvailable` vẫn ~115 GiB). Chạy `sync; echo 3 > /proc/sys/vm/drop_caches` trước mỗi lần load model; mọi playbook chính thức của Spark đều làm vậy.
> - Tính khoảng 100 GiB dùng được mỗi node, không phải 128; giữ `--gpu-memory-utilization` của vLLM ở 0.85 trở xuống; đặt `vm.swappiness=0` (hoặc `swapoff -a`); chạy `earlyoom -m 10 -s 100,100` để SSH sống sót khi cấp phát quá tay.
> - Đọc: DGX Spark Porting Guide https://docs.nvidia.com/dgx/dgx-spark-porting-guide/index.html · Known Issues https://docs.nvidia.com/dgx/dgx-spark/known-issues.html · KB 5775 https://nvidia.custhelp.com/app/answers/detail/a_id/5775 · CUDA Programming Guide, Unified Memory https://docs.nvidia.com/cuda/cuda-programming-guide/04-special-topics/unified-memory.html · issue driver đang mở https://github.com/NVIDIA/open-gpu-kernel-modules/issues/1358 · issue vLLM https://github.com/vllm-project/vllm/issues/56824 · hướng dẫn setup đã "gia cố" https://github.com/natolambert/dgx-spark-setup · Bojie Li ch.4 §4.3.1 GPU memory và unified memory.

**Milestone**: một bài blog hoặc doc trong repo gồm (1) sơ đồ topology CPU–GPU–memory–NIC của máy bạn, (2) biểu đồ roofline của GPU dựng từ số đo Nsight của chính bạn, và (3) tokens/s của vLLM ở nhiều batch size kèm giải thích nghẽn ở đâu. Nếu muốn có chứng chỉ ở giai đoạn này, thi **NCA-AIIO**.

---

## 5. AI Networking: interconnect, RDMA, NCCL

*GPU nhanh mấy cũng vô nghĩa nếu dữ liệu không đến kịp. Từ trong máy (NVLink/PCIe) ra ngoài máy (RDMA / InfiniBand / RoCE) rồi lên Kubernetes.*

### Video
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ NVIDIA Networking Academy — InfiniBand, RoCE, Spectrum-X, Cumulus Linux | 🆓🎥 | https://academy.nvidia.com/ |
| GPU MODE — Lecture 17: GPU Collective Communication (NCCL, Dan Johnson); Lecture 67: NCCL & NVSHMEM (Jeff Hammond) | 🆓🎥 | https://github.com/gpu-mode/lectures |
| CNCF (YouTube) — tìm "Kubernetes networking" KubeCon talks | 🆓🎥 | https://www.youtube.com/@cncf |
| Udemy — InfiniBand Fundamentals for AI & HPC Data Centers | 💰🎥🧪 | https://www.udemy.com/course/infiniband-fundamentals/ |
| Udemy — NCP-AIN practice tests | 💰🎥 | https://www.udemy.com/course/nvidia-ai-networking-ncp-ain/ · https://www.udemy.com/course/ai-networking-certification-prep-questions-ncp-ain/ |
| LinkedIn Learning — Kubernetes: Cloud Native Ecosystem (Karthik Gaekwad) | 💰🎥 | https://www.linkedin.com/learning/ (tìm theo tên) |

### Sách & docs
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ AI Infrastructure (Bojie Li) — ch.6 supernodes (§6.2 sáu chiến lược parallelism, §6.4 chi phí collective communication), ch.7 data-center networks (§7.2 traffic liên node, multi-NIC và multi-rail, §7.3 đường đi RDMA) | 🆓📕 | https://bojieli.github.io/ai-infra-book/en/ |
| NCCL user guide + biến môi trường (`NCCL_IB_HCA`, `NCCL_SOCKET_IFNAME`, `NCCL_IB_GID_INDEX`, `NCCL_NET_GDR_LEVEL`) + nccl-tests | 🆓📄🧪 | https://docs.nvidia.com/deeplearning/nccl/user-guide/docs/index.html · https://docs.nvidia.com/deeplearning/nccl/user-guide/docs/env.html · https://github.com/NVIDIA/nccl-tests |
| vLLM docs — Parallelism and Scaling (TP/PP đa node, Ray vs multiprocessing, `NCCL_DEBUG=TRACE` để xác nhận RDMA hay TCP) | 🆓📄 | https://docs.vllm.ai/en/stable/serving/parallelism_scaling/ |
| DGX Spark playbooks — Connect two Sparks, NCCL trên hai Spark, hướng dẫn benchmark hiệu năng (`ib_write_bw`, `vllm bench`) | 🆓📄🧪 | https://github.com/NVIDIA/dgx-spark-playbooks/blob/main/nvidia/connect-two-sparks/README.md · https://github.com/NVIDIA/dgx-spark-playbooks/blob/main/nvidia/nccl/README.md · https://github.com/NVIDIA/dgx-spark-playbooks/blob/main/nvidia/connect-two-sparks/assets/performance_benchmarking_guide.md |
| Learning eBPF (Liz Rice) — free từ Isovalent | 🆓📕 | https://isovalent.com/books/learning-ebpf/ |
| ebpf.io | 🆓📄 | https://ebpf.io/ |
| Cilium docs | 🆓📄 | https://docs.cilium.io/ |
| Istio docs | 🆓📄 | https://istio.io/latest/docs/ |

🧪 **Làm** (cần 2 máy có NIC tốc độ cao — tôi dùng 2 DGX Spark nối bằng một sợi cáp QSFP; writeup ở mục Dự án thực hành)
1. `iperf3` (TCP) vs `ib_write_bw` (RDMA, perftest).
2. Bật RoCE v2 + PFC/ECN; chạy `all_reduce_perf` với `NCCL_DEBUG=INFO`; đọc xem NCCL chọn transport nào. Số tham chiếu trên 2 DGX Spark: `ib_write_bw` khoảng 185–190 Gb/s, bus bandwidth `all_reduce` của NCCL khoảng 18–24 GB/s với MTU 9000. Nếu chỉ thấy khoảng 3 GB/s thì NCCL đã rơi về TCP: sai interface, MTU 1500, hoặc bản NCCL cũ hơn 2.28 (ra đời trước GB10).
3. vLLM tensor-parallel 2 node; so sánh RDMA với ép Socket.
4. Kubernetes + Cilium; dùng Hubble theo dõi 1 packet từ ingress → pod; viết NetworkPolicy default-deny rồi mở dần.

**Milestone**: một tài liệu mô tả toàn bộ mạng của lab từ đầu đến cuối — đường cáp vật lý, bố trí IP/VLAN, cấu hình RDMA, kết quả benchmark NCCL (băng thông và độ trễ của `all_reduce`), và cấu hình CNI/NetworkPolicy trên Kubernetes — với số đo thật từ `iperf3`, `ib_write_bw` và `nccl-tests`. Nếu muốn có chứng chỉ ở giai đoạn này, thi **NCP-AIN**.

---

## 6. Security cho AI platform

*Threat model → zero trust → supply chain → LLM security.*

### Video
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ Kim Wüstkamp — Kubernetes CKS Full Course (free trên YouTube) | 🆓🎥🧪 | https://www.youtube.com/watch?v=d9xfB5qaOfg |
| Udemy — Kubernetes CKS Complete Course (Kim Wüstkamp, kèm phiên killer.sh) | 💰🎥🧪 | https://killer.sh/r?d=cks-course |
| LinkedIn Learning — Securing Containers and Kubernetes Ecosystem (Sam Sehgal) | 💰🎥 | https://www.linkedin.com/learning/securing-containers-and-kubernetes-ecosystem |
| LinkedIn Learning — Cert Prep: Kubernetes and Cloud Native Security Associate (KCSA) (Michael Levan) | 💰🎥 | https://www.linkedin.com/learning/cert-prep-kubernetes-and-cloud-native-security-associate-kcsa |
| LinkedIn Learning — Understanding Zero Trust (Malcolm Shore) | 💰🎥 | https://www.linkedin.com/learning/ (tìm theo tên) |
| KodeKloud — khoá CKS & challenges | 💰🎥🧪 | https://www.kodekloud.com/ |
| Killercoda — kịch bản CKS | 🆓🧪 | https://killercoda.com/ |

### Sách & docs
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ Container Security, 2nd ed. (Liz Rice) — free từ Isovalent | 🆓📕 | https://isovalent.com/books/container-security/ |
| Kubernetes security concepts | 🆓📄 | https://kubernetes.io/docs/concepts/security/ |
| NSA/CISA Kubernetes Hardening Guide | 🆓📄 | https://www.cisa.gov/news-events/alerts/2022/03/15/updated-kubernetes-hardening-guide |
| NIST SP 800-190 — Application Container Security Guide | 🆓📄 | https://csrc.nist.gov/pubs/sp/800/190/final |
| NIST AI Risk Management Framework | 🆓📄 | https://www.nist.gov/itl/ai-risk-management-framework |
| CKS curated resources (walidshaari) | 🆓📄 | https://github.com/walidshaari/Certified-Kubernetes-Security-Specialist |
| Kyverno docs | 🆓📄 | https://kyverno.io/docs/ |
| HashiCorp Vault tutorials | 🆓📄🧪 | https://developer.hashicorp.com/vault/tutorials |
| Sigstore / cosign docs | 🆓📄 | https://docs.sigstore.dev/ |
| ⭐ OWASP Top 10 for LLM Applications | 🆓📄 | https://genai.owasp.org/ |
| MITRE ATLAS | 🆓📄 | https://atlas.mitre.org/ |
| NVIDIA garak — scanner lỗ hổng LLM | 🆓🧪 | https://github.com/NVIDIA/garak |
| NVIDIA NeMo Guardrails | 🆓🧪 | https://github.com/NVIDIA/NeMo-Guardrails |
| roadmap.sh — Cyber Security | 🆓📄 | https://roadmap.sh/cyber-security |

🧪 **Làm**
1. Threat model 1 trang (STRIDE) cho hệ thống ML của bạn.
2. Kyverno: ép `runAsNonRoot`, cấm `privileged`, bắt buộc label; test bằng pod vi phạm.
3. Vault + External Secrets Operator; xoá mọi secret khỏi repo; bỏ `cluster-admin` của CI.
4. CI: Trivy scan → cosign ký → Kyverno `verifyImages`.
5. mTLS STRICT (Istio hoặc Cilium); kiểm chứng bằng tcpdump.
6. Falco runtime alert; garak scan endpoint LLM.

**Milestone**: một pull request được merge vào dự án của bạn, thêm Kyverno policy, secret quản lý bằng Vault, image đã ký và được kiểm tra khi admission, mTLS giữa các service, và một rule alert Falco — kèm tài liệu threat model 1 trang giải thích mỗi biện pháp chống lại rủi ro nào. Nếu muốn có chứng chỉ ở giai đoạn này, thi **KCSA** trước rồi **CKS**.

---

## 7. LLMOps & inference quy mô lớn

*Vận hành LLM = MLOps + GPU memory là tài nguyên khan hiếm nhất + quantization là đòn bẩy để model vừa máy + evaluation kiểu mới (eval harness, LLM-as-judge) + latency không phải một con số (TTFT, TPOT) + cost per token.*

### Video
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ GPU Optimization Workshop (MLOps.community) — talk của kỹ sư TensorRT-LLM (NVIDIA) và Triton (OpenAI) | 🆓🎥 | https://github.com/mlops-discord/gpu-optimization-workshop |
| GPU MODE — Lecture 22 (speculative decoding trong vLLM), Lecture 35 (SGLang performance), Lecture 40 (FlashInfer) | 🆓🎥 | https://github.com/gpu-mode/lectures |
| Stanford CS336 — Lecture 10 "Inference", Lecture 12 "Evaluation" (bản ghi và code Spring 2025) | 🆓🎥 | https://cs336.stanford.edu/ · https://github.com/stanford-cs336/spring2025-lectures |
| Andrej Karpathy — Let's reproduce GPT-2 (124M): training loop làm gì ở tầng hệ thống (DDP, mixed precision, `torch.compile`) | 🆓🎥🧪 | https://youtu.be/l8pRSuU81PU · https://github.com/karpathy/build-nanogpt |
| DeepLearning.AI — Efficiently Serving LLMs (Travis Addair, Predibase): batching, continuous batching, quantization, multi-LoRA | 🆓🎥🧪 | https://www.deeplearning.ai/courses/efficiently-serving-llms |
| NVIDIA DLI — Sizing LLM Inference Systems (miễn phí, tự học) | 🆓🎥🧪 | https://learn.nvidia.com/courses/course-detail?course_id=course-v1:DLI+S-FX-18+V1 |
| NVIDIA DLI — Model Parallelism: Building and Deploying Large Neural Networks | 💰🎥🧪 | https://learn.nvidia.com/courses/course-detail?course_id=course-v1:DLI+C-FX-07+V1 |
| NVIDIA Developer (YouTube) — session Dynamo, TensorRT-LLM | 🆓🎥 | https://www.youtube.com/@NVIDIADeveloper |

### Sách & docs
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ How to Scale Your Model (Google/JAX "Scaling Book") — đọc các chương roofline, sharding và inference | 🆓📕 | https://jax-ml.github.io/scaling-book/ |
| ⭐ The Ultra-Scale Playbook (Hugging Face) | 🆓📕 | https://huggingface.co/spaces/nanotron/ultrascale-playbook |
| AI Infrastructure (Bojie Li) — ch.8 inference optimization (§8.1 vòng đời request và memory, §8.2 continuous batching, §8.3 KV cache, §8.4 compression và offloading, §8.5 speculative decoding), ch.9 distributed inference (§9.2 tách prefill–decode, §9.3–9.4 MoE và expert parallelism), ch.10 training systems, ch.11 scheduling | 🆓📕 | https://bojieli.github.io/ai-infra-book/en/ |
| AI Performance Engineering (Chris Fregly) — repo code | 🆓🧪 | https://github.com/cfregly/ai-performance-engineering |
| vLLM docs — bắt đầu từ Optimization & Tuning, Conserving memory, Engine args | 🆓📄 | https://docs.vllm.ai/ · https://docs.vllm.ai/en/stable/configuration/optimization/ · https://docs.vllm.ai/en/latest/configuration/conserving_memory/ |
| vLLM Zero to Hero (Red Hat AI) — run → optimize → benchmark → scale | 🆓🧪 | https://github.com/red-hat-ai-dev/vLLM-zero-to-hero-overview |
| Aleksa Gordić — Inside vLLM: Anatomy of a High-Throughput LLM Inference System | 🆓📄 | https://www.aleksagordic.com/blog/vllm |
| Lilian Weng — Large Transformer Model Inference Optimization | 🆓📄 | https://lilianweng.github.io/posts/2023-01-10-inference-optimization/ |
| Outcome School (Amit Shekhar) — LLM Inference Engineering: các bài blog viết dễ hiểu về prefill vs decode và TTFT/TPOT, KV cache và nén KV cache, PagedAttention, continuous batching, speculative decoding (n-gram, Medusa, EAGLE), vLLM, SGLang, TensorRT-LLM, GGUF, và cách GPU, TPU, LPU chạy inference. Đọc một bài trước khi vào paper hoặc docs tương ứng ở trên; không có lab | 🆓📄 | https://github.com/amitshekhariitbhu/llm-inference-engineering · https://outcomeschool.com/blog/prefill-vs-decode-llm-inference-optimization |
| TensorRT-LLM docs | 🆓📄 | https://nvidia.github.io/TensorRT-LLM/ |
| NVIDIA Dynamo docs | 🆓📄 | https://docs.nvidia.com/dynamo/latest/ |
| gpu-perf-engineering-resources — danh sách paper (FlashAttention-3, PagedAttention, FlashInfer, MLA) | 🆓📄 | https://github.com/JINO-ROHIT/gpu-perf-engineering-resources |
| Blog nên theo dõi: vLLM blog · LMSYS/SGLang blog · NVIDIA Technical Blog · Hao AI Lab | 🆓📄 | https://blog.vllm.ai/ · https://lmsys.org/blog/ · https://developer.nvidia.com/blog/ · https://haoailab.com/ |

### Quantization & các format low-precision

*Đây là đòn bẩy giúp một MoE 320B tham số chạy được trên hai máy 128 GB. FP8 → NVFP4 không phải một cái flag, mà là một cuộc trao đổi bạn phải đo (xem Evaluation bên dưới). Nhóm của Song Han viết AWQ và SmoothQuant, nên khoá học của ông là nguồn gốc; không khoá trả phí nào hơn được.*

| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ MIT 6.5940 — Lecture 5 "Quantization Part I", Lecture 6 "Quantization Part II", Lecture 13 "LLM Deployment Techniques" (playlist Fall 2024; Lecture 3–4 là pruning và sparsity) | 🆓🎥 | https://youtube.com/playlist?list=PL80kAHvQbh-qGtNc54A6KW4i4bkTPjiRF · https://efficientml.ai |
| ⭐ MIT 6.5940 Lab 5 "Optimize LLM on Edge" — deploy Llama-2-7B bằng TinyChat (AWQ INT4) trên máy của bạn, rồi đối chiếu với model bạn đang chạy trên GPU | 🆓🧪 | https://github.com/mit-han-lab/tinychat-tutorial · https://github.com/mit-han-lab/TinyChatEngine |
| ⭐ DeepLearning.AI × Red Hat — Fast & Efficient LLM Inference with vLLM (Cedric Clyburn, ~1.5 giờ): quantize model Qwen bằng LLM Compressor → serve bằng vLLM → benchmark bằng GuideLLM, đánh giá bằng lm-eval và perplexity | 🆓🎥🧪 | https://www.deeplearning.ai/courses/fast-and-efficient-llm-inference-with-vllm/ · https://vllm.ai/blog/2026-06-03-deeplearning-ai-vllm-course |
| DeepLearning.AI — Quantization Fundamentals with Hugging Face → Quantization in Depth (tự viết linear quantizer per-tensor/per-channel/per-group bằng PyTorch) | 🆓🎥🧪 | https://www.deeplearning.ai/short-courses/quantization-fundamentals-with-hugging-face/ · https://www.deeplearning.ai/courses/quantization-in-depth |
| GPU MODE — Lecture 7: Advanced Quantization (Charles Hernandez), Lecture 30: Quantized Training, Lecture 84: Numerics and AI (Paulius Micikevicius, tác giả chính paper FP8 formats) | 🆓🎥 | https://github.com/gpu-mode/lectures · https://www.youtube.com/watch?v=1u9xUK3G4VM |
| Maarten Grootendorst — A Visual Guide to Quantization | 🆓📄 | https://newsletter.maartengrootendorst.com/p/a-visual-guide-to-quantization |
| Paper đứng sau các checkpoint bạn tải về: LLM.int8() · GPTQ · SmoothQuant (W8A8) · AWQ (W4A16, best paper MLSys 2024) · QuaRot và SpinQuant (4-bit cho weight, activation và KV bằng rotation) · KIVI (quantize KV cache) | 🆓📄 | https://arxiv.org/abs/2208.07339 · https://arxiv.org/abs/2210.17323 · https://arxiv.org/abs/2211.10438 · https://arxiv.org/abs/2306.00978 · https://arxiv.org/abs/2404.00456 · https://arxiv.org/abs/2405.16406 · https://arxiv.org/abs/2402.02750 |
| Code tham chiếu: mit-han-lab/llm-awq · mit-han-lab/smoothquant · IST-DASLab/gptq · IST-DASLab/marlin (kernel INT4×FP16 mà vLLM dùng) | 🆓🧪 | https://github.com/mit-han-lab/llm-awq · https://github.com/mit-han-lab/smoothquant · https://github.com/IST-DASLab/gptq · https://github.com/IST-DASLab/marlin |
| Format: FP8 Formats for Deep Learning (E4M3/E5M2) · paper Microscaling · ⭐ OCP Microscaling (MX) Specification v1.0 (MXFP8/MXFP4: block size 32, shared scale E8M0) · NVIDIA "Introducing NVFP4" (block size 16, scale E4M3 cộng thêm một tensor scale FP32). Đó là lý do một file `hf_quant_config.json` có group size 32 cho MXFP8 và 16 cho NVFP4 | 🆓📄 | https://arxiv.org/abs/2209.05433 · https://arxiv.org/abs/2310.10537 · https://www.opencompute.org/documents/ocp-microscaling-formats-mx-v1-0-spec-final-pdf · https://developer.nvidia.com/blog/introducing-nvfp4-for-efficient-and-accurate-low-precision-inference/ |
| DeepSeek-V3 technical report — training mixed-precision FP8 ở 671B tham số, bằng chứng quy mô lớn đầu tiên rằng FP8 training chạy được | 🆓📄 | https://arxiv.org/abs/2412.19437 |
| ⭐ NVIDIA Model Optimizer (tên cũ TensorRT Model Optimizer) — chính công cụ tạo ra checkpoint `modelopt` NVFP4/MXFP8; PTQ/QAT cho FP8, NVFP4, MXFP4, INT4-AWQ, W4A8; export sang TensorRT-LLM, vLLM, SGLang | 🆓🧪📄 | https://github.com/NVIDIA/Model-Optimizer · https://nvidia.github.io/Model-Optimizer · playbook NVFP4 cho DGX Spark: https://github.com/NVIDIA/dgx-spark-playbooks/blob/main/nvidia/nvfp4-quantization/README.md |
| ⭐ LLM Compressor (vLLM project / Red Hat) — tự quantize model sang W8A8 FP8/INT8, W4A16, NVFP4, MXFP4, FP8 KV cache; output load thẳng vào vLLM | 🆓🧪📄 | https://github.com/vllm-project/llm-compressor · https://docs.vllm.ai/projects/llm-compressor/en/latest/ |
| vLLM docs — Quantization (các phương pháp hỗ trợ và ma trận phần cứng) | 🆓📄 | https://docs.vllm.ai/en/latest/features/quantization/ · https://docs.vllm.ai/en/stable/features/quantization/supported_hardware.html |
| TensorRT-LLM — "Speed up inference with SOTA quantization techniques" (bảng accuracy và tốc độ cho FP8, INT8-SmoothQuant, INT4-AWQ, FP8 KV cache) | 🆓📄 | https://github.com/NVIDIA/TensorRT-LLM/blob/main/docs/source/blogs/quantization-in-TRT-LLM.md |
| Hugging Face Transformers — Quantization overview (mọi backend) · bitsandbytes · torchao · các loại quant GGUF của llama.cpp (`Q4_K_M`, `IQ*`, imatrix) | 🆓📄 | https://huggingface.co/docs/transformers/en/quantization/overview · https://huggingface.co/docs/bitsandbytes/main/en/index · https://github.com/pytorch/ao · https://github.com/ggml-org/llama.cpp/blob/master/tools/quantize/README.md |
| Red Hat Developer — LLM quantization guide: how to do it, and how it helps (2026) | 🆓📄 | https://developers.redhat.com/articles/2026/09/02/llm-quantization-guide-how-to-do-it--and-how-it-helps |

> AutoAWQ và AutoGPTQ đã archived năm 2025. Dùng LLM Compressor, hoặc GPTQModel (https://github.com/ModelCloud/GPTQModel) cho GPTQ.

### Evaluation: quantization làm mất bao nhiêu?

*Không eval thì không biết. Một model 4-bit "chat thấy ổn" vẫn có thể mất điểm đo được ở instruction following, toán hoặc long context. Đo trước và sau, cùng một harness.*

| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ lm-evaluation-harness (EleutherAI) — harness chuẩn; `--model vllm`, hoặc `--model local-completions` trỏ vào bất kỳ endpoint OpenAI-compatible nào | 🆓🧪 | https://github.com/EleutherAI/lm-evaluation-harness |
| ⭐ Công thức: ví dụ W4A16 của LLM Compressor, bước "Evaluate accuracy" (`lm_eval --model vllm ... --tasks gsm8k`, kèm bẫy BOS token) · trang FP8 của vLLM kết thúc bằng đúng bước kiểm tra này | 🆓📄 | https://github.com/vllm-project/llm-compressor/blob/main/examples/quantization_w4a16/README.md · https://docs.vllm.ai/en/stable/features/quantization/llm_compressor/fp8/ |
| ⭐ Red Hat / Neural Magic — "We ran over half a million evaluations on quantized LLMs" và paper "Give Me BF16 or Give Me Death?": FP8 W8A8 gần như không mất, INT8 mất 1–3 %, W4A16 vẫn cạnh tranh; scheme nào hợp workload nào | 🆓📄 | https://developers.redhat.com/articles/2024/10/17/we-ran-over-half-million-evaluations-quantized-llms · https://arxiv.org/abs/2411.02355 |
| Perplexity và KL divergence: Hugging Face "Perplexity of fixed-length models" · llama.cpp `llama-perplexity --kl-divergence` (KL so với bản FP16 tham chiếu là tín hiệu chất lượng quant ổn định hơn perplexity đơn thuần) | 🆓📄🧪 | https://huggingface.co/docs/transformers/en/perplexity · https://github.com/ggml-org/llama.cpp/blob/master/tools/perplexity/README.md |
| Bộ regression cho quant: MMLU-Pro · GPQA Diamond · IFEval · LiveCodeBench · RULER (long context; bắt được hỏng hóc do FP8 KV cache) | 🆓🧪 | https://github.com/TIGER-AI-Lab/MMLU-Pro · https://github.com/idavidrein/gpqa · https://github.com/google-research/google-research/tree/master/instruction_following_eval · https://github.com/LiveCodeBench/LiveCodeBench · https://github.com/NVIDIA/RULER |
| Leaderboard: LiveBench (hạn chế contamination, làm mới hàng tháng) · Arena (trước là LMArena) · Arena-Hard-Auto · Artificial Analysis (chất lượng và tokens/s đặt cạnh nhau) | 🆓🧪 | https://livebench.ai/ · https://arena.ai/ · https://github.com/lmarena/arena-hard-auto · https://artificialanalysis.ai/ |
| LLM-as-judge: "Judging LLM-as-a-Judge with MT-Bench and Chatbot Arena" · Hamel Husain, "Your AI Product Needs Evals" và "Creating a LLM-as-a-Judge That Drives Business Results" · Prometheus 2 (judge open-weight tự host được) | 🆓📄 | https://arxiv.org/abs/2306.05685 · https://hamel.dev/blog/posts/evals/ · https://hamel.dev/blog/posts/llm-judge/ · https://arxiv.org/abs/2405.01535 |
| Hugging Face Evaluation Guidebook (Clémentine Fourrier) | 🆓📕 | https://github.com/huggingface/evaluation-guidebook |
| DeepLearning.AI — Automated Testing for LLMOps (eval trong CI ở mỗi thay đổi; gate việc rollout model đã quantize theo cùng cách) | 🆓🎥🧪 | https://www.deeplearning.ai/courses/automated-testing-llmops |
| Stack khác: lighteval (Hugging Face) · Inspect AI (UK AISI) · OpenCompass · NVIDIA NeMo Evaluator (chạy lm-eval và các harness khác trong container, trỏ vào bất kỳ endpoint nào) · accuracy gate GSM8K của chính vLLM trong `tests/evals/gsm8k` | 🆓🧪 | https://github.com/huggingface/lighteval · https://github.com/UKGovernmentBEIS/inspect_ai · https://github.com/open-compass/opencompass · https://github.com/NVIDIA-NeMo/Evaluator · https://github.com/vllm-project/vllm/tree/main/tests/evals/gsm8k |

> Hugging Face Open LLM Leaderboard đã ngừng từ tháng 3/2025. Bộ task cuối của nó (IFEval, BBH, MATH level 5, GPQA, MuSR, MMLU-Pro) vẫn là một bộ regression hợp lý.

### Speculative decoding

*Draft thì rẻ, verification thì chính xác, và con số quan trọng là acceptance. `num_speculative_tokens: 5` với acceptance 29 % là một cỗ máy rất khác so với cùng setting ở 85 %.*

| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ GPU MODE — Lecture 22: Hacker's Guide to Speculative Decoding in vLLM (Cade Daniel) | 🆓🎥 | https://www.youtube.com/watch?v=9wNAgpX6z_4 |
| ⭐ vLLM docs — Speculative Decoding (draft model, n-gram, EAGLE-3, MTP, …) và "Per-request acceptance metrics": mean acceptance length = 1 + số token được chấp nhận / số draft; counter Prometheus `vllm:spec_decode_num_draft_tokens`, `vllm:spec_decode_num_accepted_tokens` | 🆓📄 | https://docs.vllm.ai/en/latest/features/speculative_decoding/ · https://docs.vllm.ai/en/latest/features/speculative_decoding/acceptance_metrics/ |
| Paper gốc: Leviathan et al. (ICML 2023) · Chen et al. (DeepMind) · Hugging Face "Assisted Generation" (dẫn nhập nhẹ nhàng) | 🆓📄 | https://arxiv.org/abs/2211.17192 · https://arxiv.org/abs/2302.01318 · https://huggingface.co/blog/assisted-generation |
| Medusa (thêm decoding head) · EAGLE-1/2/3 (draft ở tầng feature; EAGLE-3 là drafter phổ biến trong deployment vLLM và SGLang) | 🆓📄🧪 | https://arxiv.org/abs/2401.10774 · https://arxiv.org/abs/2401.15077 · https://arxiv.org/abs/2406.16858 · https://arxiv.org/abs/2503.01840 · https://github.com/SafeAILab/EAGLE |
| Multi-token prediction (MTP), drafter tích hợp sẵn mà GLM và DeepSeek ship kèm: Gloeckle et al. (Meta) · DeepSeek-V3 report (module MTP làm draft, acceptance 85–90 % cho token thứ hai) · GLM-4.5 và GLM-5 report (các layer MTP thiết kế cho speculative decoding) | 🆓📄 | https://arxiv.org/abs/2404.19737 · https://arxiv.org/abs/2412.19437 · https://arxiv.org/abs/2508.06471 · https://arxiv.org/abs/2602.15763 |
| vLLM blog — How Speculative Decoding Boosts vLLM Performance by up to 2.8x (và vì sao ở QPS cao nó có thể phản tác dụng) | 🆓📄 | https://vllm.ai/blog/2024-10-17-spec-decode |
| Survey (Xia et al., ACL 2024) + Spec-Bench (EAGLE, Medusa, lookahead, prompt lookup trên cùng một harness) | 🆓📄🧪 | https://arxiv.org/abs/2401.07851 · https://github.com/hemingkx/Spec-Bench |
| Tự train drafter: vllm-project/speculators (EAGLE-3, DFlash, fine-tune MTP) · docs speculative decoding của SGLang và TensorRT-LLM | 🆓🧪📄 | https://github.com/vllm-project/speculators · https://docs.sglang.ai/advanced_features/speculative_decoding.html · https://github.com/NVIDIA/TensorRT-LLM/blob/main/docs/source/features/speculative-decoding.md |
| Bojie Li — ch.8 §8.5 Speculative Decoding (draft, verification, rollback; latency mỗi vòng so với số token ra) | 🆓📕 | https://bojieli.github.io/ai-infra-book/en/ |

### Metric & benchmark cho LLM serving

*Đây là thứ phân biệt LLMOps với MLOps: latency không phải một con số. TTFT (prefill), TPOT và ITL (decode), latency end-to-end, throughput, và goodput (số request mỗi giây đạt cả hai SLO).*

| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ NVIDIA Technical Blog — "LLM Inference Benchmarking: Fundamental Concepts" (định nghĩa TTFT, ITL, TPOT, throughput, goodput), rồi "How much does your LLM inference cost?" | 🆓📄 | https://developer.nvidia.com/blog/llm-benchmarking-fundamental-concepts/ · https://developer.nvidia.com/blog/llm-inference-benchmarking-how-much-does-your-llm-inference-cost |
| ⭐ vLLM docs — Production Metrics và design doc về Metrics. Tên metric V1: `vllm:time_to_first_token_seconds`, `vllm:inter_token_latency_seconds`, `vllm:request_time_per_output_token_seconds`, `vllm:e2e_request_latency_seconds`, `vllm:kv_cache_usage_perc` (V0 là `vllm:gpu_cache_usage_perc`), `vllm:num_requests_running` / `_waiting`, `vllm:prefix_cache_hits` / `_queries`, `vllm:num_preemptions` | 🆓📄 | https://docs.vllm.ai/en/stable/design/metrics/ · https://github.com/vllm-project/vllm/blob/main/docs/usage/metrics.md |
| vLLM — dashboard mẫu Prometheus + Grafana | 🆓🧪 | https://github.com/vllm-project/vllm/tree/main/examples/observability/prometheus_grafana |
| ⭐ Load generator: `vllm bench serve` (có sẵn) · GuideLLM (sweep theo SLO) · NVIDIA AIPerf (kế nhiệm GenAI-Perf) · inference-perf (Kubernetes WG Serving) | 🆓🧪 | https://docs.vllm.ai/en/latest/benchmarking/cli/ · https://github.com/vllm-project/guidellm · https://github.com/ai-dynamo/aiperf · https://github.com/kubernetes-sigs/inference-perf |
| NVIDIA NIM benchmarking guide — Metrics (định nghĩa chính xác, ví dụ ITL = (latency e2e − TTFT) / (số token ra − 1)) | 🆓📄 | https://docs.nvidia.com/nim/benchmarking/llm/latest/metrics.html |
| Databricks — LLM Inference Performance Engineering: Best Practices · Anyscale — Reproducible Performance Metrics for LLM Inference | 🆓📄 | https://www.databricks.com/blog/llm-inference-performance-engineering-best-practices · https://www.anyscale.com/blog/reproducible-performance-metrics-for-llm-inference |
| Goodput: paper DistServe (OSDI 2024) và Hao AI Lab, "Throughput is Not All You Need" | 🆓📄 | https://arxiv.org/abs/2401.09670 · https://haoailab.com/blogs/distserve/ |
| SGLang — Production metrics · Kubernetes Gateway API Inference Extension ("inference gateway": InferencePool, load balancing theo prefix cache) | 🆓📄 | https://docs.sglang.ai/references/production_metrics.html · https://gateway-api-inference-extension.sigs.k8s.io/ |
| MLPerf Inference (MLCommons) — bộ LLM cho datacenter (Llama 2 70B, Llama 3.1 405B, DeepSeek-R1, …) và cách vendor báo cáo | 🆓🧪 | https://github.com/mlcommons/inference |
| Bojie Li — ch.3 §3.1.2 mục tiêu tác vụ và metric đánh giá; ch.8 §8.1.3 từ thời gian một request đến mục tiêu dịch vụ | 🆓📕 | https://bojieli.github.io/ai-infra-book/en/ |

### Nhìn về phía trước: disaggregated serving (tách prefill/decode)

*Prefill bị compute-bound, decode bị memory-bound. Frontier chạy hai pha trên hai pool riêng, chuyển KV cache qua RDMA, và route request theo prefix-cache hit. Đọc phần này sau khi bạn đã giải thích được TTFT và TPOT trên một máy.*

| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ DistServe (OSDI 2024) · Splitwise (ISCA 2024) · Mooncake (best paper FAST 2025; thiết kế lấy KV làm trung tâm đứng sau Kimi) | 🆓📄🧪 | https://arxiv.org/abs/2401.09670 · https://arxiv.org/abs/2311.18677 · https://arxiv.org/abs/2407.00079 · https://github.com/kvcache-ai/Mooncake |
| Hao AI Lab — "Disaggregated Inference: 18 Months Later" (Dynamo, llm-d, SGLang và vLLM đã áp dụng gì) · "Beyond the Buzz: A Pragmatic Take on Inference Disaggregation" (khi nào không đáng) | 🆓📄 | https://haoailab.com/blogs/distserve-retro/ · https://arxiv.org/abs/2506.05508 |
| ⭐ llm-d (Red Hat, Google, IBM, CoreWeave, NVIDIA) — stack Kubernetes-native: well-lit paths, guide P/D disaggregation, routing theo prefix cache | 🆓📄🧪 | https://llm-d.ai/ · https://llm-d.ai/docs/well-lit-paths · https://github.com/llm-d/llm-d/tree/main/guides/pd-disaggregation |
| NVIDIA Dynamo — Disaggregated serving, KV-cache-aware routing, và bài ra mắt "Introducing NVIDIA Dynamo" (GTC 2025) | 🆓📄 | https://docs.nvidia.com/dynamo/dev/cli/disaggregated-serving/overview · https://docs.nvidia.com/dynamo/latest/user-guides/kv-cache-aware-routing · https://developer.nvidia.com/blog/introducing-nvidia-dynamo-a-low-latency-distributed-inference-framework-for-scaling-reasoning-ai-models |
| vLLM docs — Disaggregated Prefilling (KV connector: NIXL, LMCache, Mooncake; docs nói rõ nó *không* tăng throughput, mà tách việc tune TTFT và ITL) · SGLang — PD Disaggregation | 🆓📄 | https://docs.vllm.ai/en/latest/features/disagg_prefill/ · https://docs.sglang.ai/advanced_features/pd_disaggregation.html |
| Phần "ống nước": NIXL (NVIDIA Inference Xfer Library, chuyển KV qua RDMA và NVLink) · LMCache (các tầng KV cache: GPU → CPU → disk → remote) | 🆓🧪 | https://github.com/ai-dynamo/nixl · https://github.com/LMCache/LMCache |
| BentoML LLM Inference Handbook — Prefill-decode disaggregation · Prefix-aware routing (giải thích kiểu practitioner) | 🆓📕 | https://bentoml.com/llm/inference-optimization/prefill-decode-disaggregation · https://bentoml.com/llm/inference-optimization/prefix-aware-routing |
| Bojie Li — ch.9 §9.2 Tách Prefill–Decode và tỷ lệ tài nguyên (chuyển KV, throughput từng pha, tỷ lệ instance, khi nào có lợi) | 🆓📕 | https://bojieli.github.io/ai-infra-book/en/ |

🧪 **Làm**
1. Benchmark vLLM: prefix caching on/off, `max_num_seqs`, `gpu_memory_utilization`, `max_num_batched_tokens` → throughput vs p99 TTFT và p99 TPOT; báo cáo goodput theo một SLO bạn tự chọn.
2. Tự quantize một model bằng LLM Compressor (W8A8 FP8 và W4A16), rồi so với checkpoint NVFP4 của vendor: kích thước, tokens/s, điểm lm-eval (GSM8K, IFEval, MMLU-Pro) và perplexity hoặc KL divergence. Ghi lại 4-bit đã lấy đi của bạn những gì.
3. Speculative decoding: bật MTP, EAGLE-3 hoặc n-gram; đọc các counter `vllm:spec_decode_*`; vẽ mean acceptance length vs tokens/s ở batch 1 và batch 16; tìm batch size mà nó hết tác dụng.
4. Dashboard Grafana từ metric vLLM: TTFT p50/p99, ITL p99, KV-cache usage, độ sâu hàng đợi, preemption; alert theo p99 TTFT.
5. Kueue + GPU Operator: 2 team submit job; xem quota và preemption.
6. LoRA fine-tune qua 2 node (DDP/FSDP) trên RDMA; đo scaling efficiency.
7. Retrain loop: Evidently → Alertmanager → Argo Events → job → MLflow → canary.

**Milestone**: một báo cáo benchmark cho một LLM trên phần cứng của bạn (throughput vs TTFT/TPOT theo batch size; FP8 vs NVFP4 kèm số eval cho thấy quantization mất gì; acceptance của speculative decoding vs tốc độ tăng thêm; 1 node vs tensor parallel 2 node) và một vòng lặp retrain tự động chạy được. Nếu muốn có chứng chỉ ở giai đoạn này, thi **NCP-AII** (nếu bạn build cluster) hoặc **NCP-AIO** (nếu bạn vận hành).

---

## 8. AI Data Center (AIDC)

*Đọc được reference architecture; hiểu power, cooling, network, storage ràng buộc nhau thế nào; thiết kế cluster 64–256 GPU trên giấy.*

### Video
| Tài nguyên | Loại | Link |
|---|---|---|
| NVIDIA GTC on-demand — tìm "Spectrum-X", "liquid cooling GB200", "SuperPOD deployment" | 🆓🎥 | https://www.nvidia.com/gtc/ |
| NVIDIA Networking Academy — track data center | 🆓🎥 | https://academy.nvidia.com/ |

### Sách & docs
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ The Datacenter as a Computer, 3rd ed. (Barroso, Hölzle, Ranganathan) — open access | 🆓📕 | https://datacenter-book.org/ · https://library.oapen.org/handle/20.500.12657/61844 |
| ⭐ NVIDIA DGX SuperPOD reference architectures | 🆓📄 | https://docs.nvidia.com/dgx-superpod/ |
| Open Compute Project | 🆓📄 | https://www.opencompute.org/ |
| Uptime Institute | 🆓📄 | https://www.uptimeinstitute.com/ |
| AI Infrastructure (Bojie Li) — ch.6 supernodes, ch.7 data-center networks, ch.11 resource scheduling, ch.12 edge-cloud coordination | 🆓📕 | https://bojieli.github.io/ai-infra-book/en/ |
| ai-infra-curriculum — Architect track | 🆓📄 | https://ai-infra-curriculum.github.io/ |

🧪 **Làm (trên giấy)**: thiết kế cluster 128 GPU cho training + inference: TFLOPS, HBM, NVLink domain, port 400G, oversubscription, storage GB/s cho checkpoint, kW/rack, air vs liquid cooling, TCO on-prem vs cloud.
**Milestone**: tài liệu thiết kế cluster 128 GPU (compute, topology mạng, storage, power, cooling, chi phí) và một bài trình bày 20 phút cho đồng nghiệp hoặc một nhóm cộng đồng.

---

## 🎓 Chứng chỉ

| # | Chứng chỉ | Link |
|---|---|---|
| 1 | NVIDIA NCA-AIIO — AI Infrastructure & Operations (Associate) | https://www.nvidia.com/en-us/learn/certification/ |
| 2 | KCSA → CKS — Kubernetes security | https://www.cncf.io/certification/cks/ |
| 3 | NVIDIA NCP-AIN — AI Networking | https://www.nvidia.com/en-us/learn/certification/ |
| 4 | NVIDIA NCP-AII / NCP-AIO — AI Infrastructure / AI Operations (Professional) | https://www.nvidia.com/en-us/learn/certification/ |

Simulator thi CKA/CKAD/CKS: https://killer.sh/

---

## 🧪 Dự án thực hành

| Repository | Là gì |
|---|---|
| ⭐ https://github.com/DucLong06/face-detection-ml-system | Dự án của tôi: hệ thống ML face detection (Jenkins, GKE, Terraform/Ansible, ELK, Jaeger), đang nâng cấp lên GPU on-prem (DGX Spark), GitOps, GPU serving và security baseline. Xem nhánh plans. |
| ⭐ Hai DGX Spark qua RoCE 200G — writeup (đang viết) | Lab của tôi: hai node GB10 nối bằng một sợi cáp QSFP (RoCE v2, NCCL), vLLM tensor-parallel serve một MoE 320B tham số (họ GLM-5.3, checkpoint NVFP4/MXFP8 từ NVIDIA Model Optimizer) với MTP speculative decoding. Writeup sẽ gồm: đi cáp và cấu hình RoCE, số đo `ib_write_bw` và `nccl-tests`, tính memory budget trên unified memory, `--gpu-memory-utilization`, acceptance rate của speculative decoding, và các bài học trong ghi chú unified memory ở mục 4. Trong lúc chờ, các recipe công khai gần nhất: https://github.com/himorishige/glm53-flash-2x-dgx-spark-recipe · https://github.com/tonyd2wild/GLM-5.3-Flash-NVFP4-2x-DGX-Spark · https://github.com/Kdurazzo/dual-dgx-spark-config-guide · danh mục tổng hợp https://github.com/bidual/awesome-dgx-spark |
| https://github.com/ai-infra-curriculum/ai-infra-engineer-learning | 10 module, 62 lab, 3 project (model serving → MLOps pipeline → LLM deployment) |
| https://github.com/ai-infra-curriculum/ai-infra-performance-learning | Track performance engineer: CUDA, Nsight, compression, transformer kernels |
| https://github.com/DataTalksClub/mlops-zoomcamp | Nộp project để được peer review miễn phí |

**Sơ đồ lab của tôi**: hai DGX Spark (GB10) nối bằng một sợi cáp QSFP, vLLM tensor parallel trên cả hai node.

![Hai DGX Spark nối qua RoCE 200G, vLLM tensor parallel = 2](assets/dgx-spark-lab.png)

---

## 🧭 Roadmap & danh mục khác

| Tên | Link |
|---|---|
| ai-infra-curriculum (Engineer / Performance / MLOps / Senior / Architect tracks) | https://github.com/ai-infra-curriculum/ai-infra-engineer-learning · https://ai-infra-curriculum.github.io/ |
| roadmap.sh — MLOps / Kubernetes / Cyber Security / DevOps | https://roadmap.sh/mlops · https://roadmap.sh/kubernetes · https://roadmap.sh/cyber-security |
| AI/ML Platform Engineer — 6-Month Learning Roadmap (gist) | https://gist.github.com/piyushjajoo/51d72850754aabc06ef1f6d994a4d35f |
| awesome-gpu-engineering | https://github.com/goabiaryan/awesome-gpu-engineering |
| gpu-perf-engineering-resources | https://github.com/JINO-ROHIT/gpu-perf-engineering-resources |
| MLOps Engineer Roadmap (100% free video resources) | https://github.com/harish303118/MLOps-Engineering-with-Roadmap-and-Free-Learning-Resources |
| ml-roadmap | https://github.com/loganthorneloe/ml-roadmap |
| AI Engineering Course (Outcome School, 18 module: nền tảng ML → transformer → fine-tuning → RAG → agent → inference → system design). Mảng AI engineering phía ứng dụng, bổ sung cho roadmap hạ tầng này | https://github.com/amitshekhariitbhu/ai-engineering-course |
| Machine Learning Systems (mlsysbook.ai) | https://mlsysbook.ai/ |
| developer-roadmap (mã nguồn roadmap.sh) | https://github.com/kamranahmedse/developer-roadmap |

> **Đam mê open-source về AI?** Tôi dùng https://goodailist.com/repos để tìm các repo AI đang hot.

---

## 🙏 Lời cảm ơn

Roadmap này đứng trên vai nhiều người và cộng đồng:

- **[Full Stack Data Science](https://fullstackdatascience.com/)** và anh **[Quan Dang](https://github.com/quan-dang)** — khoá học cho tôi nền MLOps đầu tiên (Docker, Kubernetes, Kafka, Spark, Airflow, Kubeflow, Jenkins, GKE, observability) và cách làm đồ án theo rubric. Phần lớn mục 2–3 là những gì tôi học được ở đó, viết lại theo góc nhìn của người đã đi làm.
- **[Bojie Li](https://github.com/bojieli/ai-infra-book)** — tác giả sách open-source *AI Infrastructure* (Apache 2.0), xương sống của mục 3.5, 4, 5, 7, 8.
- **Wen-mei Hwu, David Kirk, Izzat El Hajj** — *Programming Massively Parallel Processors* và [kênh bài giảng chính thức](https://www.youtube.com/@pmpp-book).
- **[GPU MODE](https://github.com/gpu-mode/lectures)** — cộng đồng và loạt lecture free về GPU performance.
- **Andrej Karpathy, Grant Sanderson (3Blue1Brown), Sebastian Raschka** và đội ngũ **Stanford CS336** (Percy Liang, Tatsunori Hashimoto) — video, code và bài giảng miễn phí làm nền cho mục 3.5.
- **[Song Han / MIT HAN Lab](https://hanlab.mit.edu/)** — MIT 6.5940 (EfficientML.ai), AWQ, SmoothQuant và TinyChat, những kỹ thuật đứng sau phần lớn checkpoint quantized mà chúng ta chạy.
- **[vLLM project](https://github.com/vllm-project), Red Hat AI và DeepLearning.AI** — vLLM, LLM Compressor, GuideLLM và khoá học miễn phí *Fast & Efficient LLM Inference with vLLM*.
- **[EleutherAI](https://github.com/EleutherAI/lm-evaluation-harness)** — lm-evaluation-harness; **[Hao AI Lab (UCSD)](https://haoailab.com/)** — DistServe và các bài viết về disaggregated serving.
- **Cộng đồng DGX Spark** — himorishige, tonyd2wild, Kdurazzo, natolambert, bidual (awesome-dgx-spark) và các thành viên diễn đàn NVIDIA đã ghi lại cách dựng GB10 đa node và các bẫy unified memory.
- **Liz Rice / Isovalent** — *Container Security* và *Learning eBPF* phát hành miễn phí.
- **Kim Wüstkamp / Killer Shell** — khoá CKS free trên YouTube, killer.sh và Killercoda.
- **Luiz André Barroso, Urs Hölzle, Parthasarathy Ranganathan** — *The Datacenter as a Computer* open access; **Google SRE** — các sách SRE.
- **Larry Peterson & Bruce Davie** — *Computer Networks: A Systems Approach*; **Jim Kurose** — video bài giảng free.
- **Vijay Janapa Reddi** — *Machine Learning Systems*; **Goku Mohandas** — Made With ML.
- **ai-infra-curriculum**, **roadmap.sh**, **DataTalks.Club**, **harish303118** (format README), và các tác giả danh mục được dẫn link ở trên.
- **NVIDIA** — docs, Networking Academy, DLI và tài liệu kiến trúc công khai.
- **[Claude](https://claude.ai) của Anthropic** — đã giúp tôi tìm và kiểm tra link, review repo dự án, soạn thảo và cấu trúc README này. Mọi tài liệu đều được kiểm tra và lựa chọn cuối cùng là của tôi.

Nếu bạn là tác giả của tài liệu được liệt kê và muốn chỉnh mô tả hoặc gỡ link, hãy mở issue.

---

## 🤝 Contributing

- Mở **issue** khi link chết, tài liệu lỗi thời, hoặc bạn biết nguồn free tốt hơn.
- **PR** thêm tài liệu: ghi rõ *loại* (🆓/💰, 🎥/📕/📄/🧪), *mục*, và 1 dòng *vì sao đáng học*. Ưu tiên nguồn chính thống (tác giả, vendor, đại học) hơn blog tổng hợp.


---

*Nếu roadmap này giúp bạn, hãy ⭐ repo và chia sẻ. Nếu bạn đi cùng con đường này, mở issue để trao đổi — tôi cũng đang học.*
