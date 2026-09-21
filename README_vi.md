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

1. Mục 1–3 là nền. Mục 4–8 có thể học song song tuỳ công việc. Đã biết MLOps thì vào thẳng mục 4.
2. Mỗi mục có **Học** (xem/đọc) → **Làm** (lab) → **Milestone** (sản phẩm để chứng minh). Chưa có milestone = chưa xong.
3. Ký hiệu: 🆓 miễn phí · 💰 trả phí · 🎥 video · 📕 sách · 📄 docs/paper · 🧪 lab · ⭐ bắt đầu từ đây.
4. Viết journal bằng tiếng Anh sau mỗi lab. Đó chính là portfolio của bạn.

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
| Dive into Deep Learning (D2L) | 🆓📕 | https://d2l.ai/ |

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
| MIT 6.5940 — TinyML & Efficient Deep Learning (Song Han) | 🆓🎥 | https://hanlab.mit.edu/courses/2024-fall-65940 |
| CMU — Deep Learning Systems | 🆓🎥 | https://dlsyscourse.org/ |
| NVIDIA DLI — Fundamentals of Accelerated Computing with CUDA C/C++ | 💰🎥🧪 | https://learn.nvidia.com/ |
| Udemy — CUDA GPU Programming Beginner To Advanced | 💰🎥 | https://www.udemy.com/course/cuda-gpu-programming-beginner-to-advanced/ |
| Udemy — Mastering Parallel programming with CUDA platform | 💰🎥 | https://www.udemy.com/course/mastering-parallel-programming-with-cuda-platform/ |
| Udemy — NVIDIA-Certified Professional: AI Infrastructure (NCP-AII) | 💰🎥 | https://www.udemy.com/course/ncp-aii-nvidia-certified-professional-ai-infrastructure/ |

### Sách & docs
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ AI Infrastructure (Bojie Li) — sách open-source, ch.4 accelerator architecture, ch.5 memory | 🆓📕 | https://bojieli.github.io/ai-infra-book/ |
| Programming Massively Parallel Processors, 4th ed. (Hwu, Kirk, El Hajj) | 💰📕 | https://shop.elsevier.com/books/programming-massively-parallel-processors/hwu/978-0-323-91231-0 |
| CUDA C++ Programming Guide | 🆓📄 | https://docs.nvidia.com/cuda/cuda-c-programming-guide/index.html |
| An Even Easier Introduction to CUDA (NVIDIA blog) | 🆓📄 | https://developer.nvidia.com/blog/even-easier-introduction-cuda/ |
| GPU Gems 1–3 | 🆓📕 | https://developer.nvidia.com/gpugems/gpugems/contributors |
| NVIDIA Blackwell architecture | 🆓📄 | https://resources.nvidia.com/en-us-blackwell-architecture |

### Tool
| Tool | Link |
|---|---|
| Nsight Systems / Nsight Compute | https://developer.nvidia.com/nsight-systems |
| DCGM + dcgm-exporter | https://docs.nvidia.com/datacenter/dcgm/latest/index.html |
| NVIDIA GPU Operator (driver, device plugin, MIG / time-slicing / MPS) | https://docs.nvidia.com/datacenter/cloud-native/gpu-operator/latest/index.html |
| Kueue (job queueing, GPU quota) | https://kueue.sigs.k8s.io/ |
| DGX Spark docs & playbooks | https://docs.nvidia.com/dgx/dgx-spark/ · https://build.nvidia.com/spark |

🧪 **Làm**
1. `nvidia-smi -q`, `nvidia-smi topo -m`, `lspci -tv` → tự vẽ sơ đồ CPU–GPU–memory–NIC của máy bạn.
2. DCGM exporter → Grafana: SM active, DRAM active, tensor-core active.
3. Viết 1 kernel matmul, profile bằng `nsys`/`ncu`, tính arithmetic intensity, vẽ roofline.
4. Chạy vLLM model 8B, đo tokens/s từ batch 1 → 32, giải thích bằng roofline.
5. Tính tay: 70B FP8 + KV cache 32k context — có vừa GPU của bạn không?

**Milestone**: một bài blog hoặc doc trong repo gồm (1) sơ đồ topology CPU–GPU–memory–NIC của máy bạn, (2) biểu đồ roofline của GPU dựng từ số đo Nsight của chính bạn, và (3) tokens/s của vLLM ở nhiều batch size kèm giải thích nghẽn ở đâu. Nếu muốn có chứng chỉ ở giai đoạn này, thi **NCA-AIIO**.

---

## 5. AI Networking: interconnect, RDMA, NCCL

*GPU nhanh mấy cũng vô nghĩa nếu dữ liệu không đến kịp. Từ trong máy (NVLink/PCIe) ra ngoài máy (RDMA / InfiniBand / RoCE) rồi lên Kubernetes.*

### Video
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ NVIDIA Networking Academy — InfiniBand, RoCE, Spectrum-X, Cumulus Linux | 🆓🎥 | https://academy.nvidia.com/ |
| GPU MODE — Lecture 17: GPU Collective Communication (NCCL) | 🆓🎥 | https://github.com/gpu-mode/lectures |
| CNCF (YouTube) — tìm "Kubernetes networking" KubeCon talks | 🆓🎥 | https://www.youtube.com/@cncf |
| Udemy — InfiniBand Fundamentals for AI & HPC Data Centers | 💰🎥🧪 | https://www.udemy.com/course/infiniband-fundamentals/ |
| Udemy — NCP-AIN practice tests | 💰🎥 | https://www.udemy.com/course/nvidia-ai-networking-ncp-ain/ · https://www.udemy.com/course/ai-networking-certification-prep-questions-ncp-ain/ |
| LinkedIn Learning — Kubernetes: Cloud Native Ecosystem (Karthik Gaekwad) | 💰🎥 | https://www.linkedin.com/learning/ (tìm theo tên) |

### Sách & docs
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ AI Infrastructure (Bojie Li) — ch.6 scale-up / super-node, ch.7 data-center network | 🆓📕 | https://bojieli.github.io/ai-infra-book/ |
| NCCL user guide + nccl-tests | 🆓📄🧪 | https://docs.nvidia.com/deeplearning/nccl/user-guide/docs/index.html · https://github.com/NVIDIA/nccl-tests |
| Learning eBPF (Liz Rice) — free từ Isovalent | 🆓📕 | https://isovalent.com/books/learning-ebpf/ |
| ebpf.io | 🆓📄 | https://ebpf.io/ |
| Cilium docs | 🆓📄 | https://docs.cilium.io/ |
| Istio docs | 🆓📄 | https://istio.io/latest/docs/ |

🧪 **Làm** (cần 2 máy có NIC tốc độ cao, ví dụ 2 DGX Spark nối QSFP)
1. `iperf3` (TCP) vs `ib_write_bw` (RDMA, perftest).
2. Bật RoCE v2 + PFC/ECN; chạy `all_reduce_perf` với `NCCL_DEBUG=INFO`; đọc xem NCCL chọn transport nào.
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

*Vận hành LLM = MLOps + GPU memory là tài nguyên khan hiếm nhất + evaluation kiểu mới (LLM-as-judge) + cost per token.*

### Video
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ GPU Optimization Workshop (MLOps.community) — talk của kỹ sư TensorRT-LLM (NVIDIA) và Triton (OpenAI) | 🆓🎥 | https://github.com/mlops-discord/gpu-optimization-workshop |
| GPU MODE — Lecture 22 (speculative decoding trong vLLM), Lecture 35 (SGLang) | 🆓🎥 | https://github.com/gpu-mode/lectures |
| NVIDIA DLI — Model Parallelism: Building and Deploying Large Neural Networks | 💰🎥🧪 | https://learn.nvidia.com/ |
| NVIDIA Developer (YouTube) — session Dynamo, TensorRT-LLM | 🆓🎥 | https://www.youtube.com/@NVIDIADeveloper |

### Sách & docs
| Tài nguyên | Loại | Link |
|---|---|---|
| ⭐ How to Scale Your Model (Google/JAX "Scaling Book") | 🆓📕 | https://jax-ml.github.io/scaling-book/ |
| ⭐ The Ultra-Scale Playbook (Hugging Face) | 🆓📕 | https://huggingface.co/spaces/nanotron/ultrascale-playbook |
| AI Infrastructure (Bojie Li) — ch.8–11 inference, distributed inference, training, scheduling | 🆓📕 | https://bojieli.github.io/ai-infra-book/ |
| AI Performance Engineering (Chris Fregly) — repo code | 🆓🧪 | https://github.com/cfregly/ai-performance-engineering |
| vLLM docs | 🆓📄 | https://docs.vllm.ai/ |
| TensorRT-LLM docs | 🆓📄 | https://nvidia.github.io/TensorRT-LLM/ |
| NVIDIA Dynamo docs | 🆓📄 | https://docs.nvidia.com/dynamo/latest/ |
| gpu-perf-engineering-resources — danh sách paper (FlashAttention-3, PagedAttention, FlashInfer, MLA) | 🆓📄 | https://github.com/JINO-ROHIT/gpu-perf-engineering-resources |

🧪 **Làm**
1. Benchmark vLLM: prefix caching on/off, `max_num_seqs`, `gpu_memory_utilization` → đồ thị throughput vs p99.
2. Quantization FP8 vs NVFP4: chất lượng và tốc độ.
3. Kueue + GPU Operator: 2 team submit job; xem quota và preemption.
4. LoRA fine-tune qua 2 node (DDP/FSDP) trên RDMA; đo scaling efficiency.
5. Retrain loop: Evidently → Alertmanager → Argo Events → job → MLflow → canary.

**Milestone**: một báo cáo benchmark cho một LLM trên phần cứng của bạn (throughput vs latency theo batch size, FP8 vs NVFP4, 1 node vs tensor parallel 2 node) và một vòng lặp retrain tự động chạy được. Nếu muốn có chứng chỉ ở giai đoạn này, thi **NCP-AII** (nếu bạn build cluster) hoặc **NCP-AIO** (nếu bạn vận hành).

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
| AI Infrastructure (Bojie Li) — ch.6, 7, 11, 12 | 🆓📕 | https://bojieli.github.io/ai-infra-book/ |
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
| https://github.com/ai-infra-curriculum/ai-infra-engineer-learning | 10 module, 62 lab, 3 project (model serving → MLOps pipeline → LLM deployment) |
| https://github.com/ai-infra-curriculum/ai-infra-performance-learning | Track performance engineer: CUDA, Nsight, compression, transformer kernels |
| https://github.com/DataTalksClub/mlops-zoomcamp | Nộp project để được peer review miễn phí |

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
| Machine Learning Systems (mlsysbook.ai) | https://mlsysbook.ai/ |
| developer-roadmap (mã nguồn roadmap.sh) | https://github.com/kamranahmedse/developer-roadmap |

> **Đam mê open-source về AI?** Tôi dùng https://goodailist.com/repos để tìm các repo AI đang hot.

---

## 🙏 Lời cảm ơn

Roadmap này đứng trên vai nhiều người và cộng đồng:

- **[Full Stack Data Science](https://fullstackdatascience.com/)** và anh **[Quan Dang](https://github.com/quan-dang)** — khoá học cho tôi nền MLOps đầu tiên (Docker, Kubernetes, Kafka, Spark, Airflow, Kubeflow, Jenkins, GKE, observability) và cách làm đồ án theo rubric. Phần lớn mục 2–3 là những gì tôi học được ở đó, viết lại theo góc nhìn của người đã đi làm.
- **[Bojie Li](https://github.com/bojieli/ai-infra-book)** — tác giả sách open-source *AI Infrastructure* (Apache 2.0), xương sống của mục 4, 5, 7, 8.
- **Wen-mei Hwu, David Kirk, Izzat El Hajj** — *Programming Massively Parallel Processors* và [kênh bài giảng chính thức](https://www.youtube.com/@pmpp-book).
- **[GPU MODE](https://github.com/gpu-mode/lectures)** — cộng đồng và loạt lecture free về GPU performance.
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
