
# Customized Retrieval-Augmented Generation with LLM for Debiasing Recommendation Unlearning

官方项目主页：[https://zhanghaichao520.github.io/CRAGRU-Page/](https://zhanghaichao520.github.io/CRAGRU-Page/)

---

## 📖 概述 (Abstract)

现代推荐系统在遵守“被遗忘权”（如 GDPR）方面面临巨大挑战 。传统的**遗忘学习 (Machine Unlearning)** 方法在删除特定用户数据时，往往会产生**传播偏置 (Propagation Bias)**，即误伤行为相似的其他用户，导致推荐质量下降 。

**CRAGRU** 是首个将**检索增强生成 (RAG)** 与传统推荐系统结合的遗忘学习框架 。我们将遗忘过程解耦为检索、增强和生成三个阶段，通过在检索阶段精准过滤目标数据，实现原子级的用户遗忘，同时通过大语言模型 (LLM) 的推理能力保持极高的推荐精度 。

---

## ✨ 核心创新 (Core Contributions)

* 
**原子级遗忘 (Atomic Unlearning)**：通过 RAG 架构将遗忘操作下沉至检索层，无需重新训练或更新模型参数即可彻底删除目标用户痕迹 。


* **三种高效过滤策略 (Three Filtering Strategies)**：
1. **基于偏好的过滤 (Preference-based)**：根据用户长期偏好分布按比例采样，减少性能损失 。
2. **多样性感知过滤 (Diversity-aware)**：平衡项目覆盖度与准确率，解决数据分布偏置 。
3. **注意力权重过滤 (Attention-aware)**：利用 Transformer 注意力权重识别高影响交互记录 。

* 
**显著的去偏能力 (Debiasing)**：有效消除遗忘请求对非目标用户的负面溢出效应 。



---

## 📊 实验表现 (Experimental Results)

在 MovieLens 和 Netflix 数据集上的实验证明了 CRAGRU 的卓越性能 ：

* 
**极速执行**：平均遗忘时间比现有 SOTA 方案快 **4.5 倍** 。


* 
**高保真度**：在遗忘后仍能保留约 **90%** 的原始推荐精度 。


* 
**显着提升**：在 ML-1M 数据集（基于 LightGCN）上，HR@10 和 NDCG@10 分别比传统基准方法提高了 **9.64%** 和 **12.3%** 。



---

## 🧱 框架结构 (Methodology)

项目主页展示了详细的架构图。CRAGRU 主要包含：

1. **检索层**：从动态索引中精确过滤待遗忘数据 。


2. **增强层**：融合用户画像、历史记录与传统推荐模型（如 LightGCN, BPR）产生的候选集生成 Prompt 。


3. **生成层**：调用 LLM（如 Llama 3.1-8b）生成最终推荐结果 。



---

## 📜 论文引用 (Citation)

如果本项目对您的研究有所启发，请引用我们的工作 ：

```bibtex
@article{zhang2025customized,
  title={Customized Retrieval-Augmented Generation with LLM for Debiasing Recommendation Unlearning},
  author={Zhang, Haichao and Zhang, Chong and Hu, Peiyu and Qiu, Shi and Wang, Jia},
  journal={arXiv preprint arXiv:2511.05494},
  year={2025},
  url={https://zhanghaichao520.github.io/CRAGRU-Page/}
}

```

---

## ✉️ 联系方式 (Contact)

**Haichao Zhang** University of Liverpool (Uol) 

Email: `zhc@liverpool.ac.uk` 

Project Page: [https://zhanghaichao520.github.io/CRAGRU-Page/](https://zhanghaichao520.github.io/CRAGRU-Page/)

