---
source: chunks/wiki-Transformer_deep_learning_architecture-chunk-5.md
source_url: https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)
---

## Transformer Architecture Variants: Activations, Positional Encodings, and Efficiency Optimizations

This page covers the major post-2017 improvements to the original transformer architecture, spanning alternative activation functions and normalizations, positional encoding schemes (RoPE, ALiBi, relative), inference optimizations (KV caching, FlashAttention, speculative decoding), attention mechanism variants (MQA, GQA, MLA), and sub-quadratic attention methods that reduce the O(N²) computational cost.

## Key Concepts

- **Alternative activations**: Original transformer used ReLU; modern models use GELU (GPT-1, BERT) or SwiGLU (Llama, PaLM), often combined with Gated Linear Units (GLU) in feedforward layers.
- **Alternative normalizations**: LayerNorm can be replaced by RMSNorm (used in Llama), ScaleNorm, or FixNorm.
- **RoPE (Rotary Positional Embedding)**: Encodes position by rotating pairs of embedding dimensions by angle mθ. Mathematically equivalent to multiplying complex-number representations by e^{imθ}. Key property: dot products depend only on *relative* position, not absolute.
- **ALiBi (Attention with Linear Biases)**: Adds a linear bias matrix B (where B_{i,j} = j−i) scaled by scalar s directly into the attention logits. Acts as a "softened mask" — not a replacement for positional encoding but an addition to the attention mechanism. Enables short-context pretraining followed by long-context fine-tuning.
- **Relative Position Encodings**: Generalization of ALiBi where B is any Toeplitz matrix (entries depend only on i−j), contrasted with absolute positional encodings like sinusoidal.
- **KV Caching**: During autoregressive inference, previously computed key and value vectors are cached and reused since they don't change. PagedAttention applies memory paging to KV caches.
- **Prefilling**: The initial forward pass over the input sequence to populate KV caches before token-by-token generation begins. Disaggregated inference separates prefilling and decoding onto different hardware.
- **FlashAttention**: Communication-avoiding algorithm that performs attention using block matrix multiplications sized to fit GPU cache, minimizing slow data movement. FlashAttention-2 achieves up to 230 TFLOPS/s on A100 (2x over v1, 9x over standard PyTorch). FlashAttention-4 targets Blackwell GPUs with pipelining.
- **Multi-Query Attention (MQA)**: All attention heads share a single set of K and V projection matrices, reducing KV cache size. Neutral effect on quality/training speed but faster inference.
- **Grouped-Query Attention (GQA)**: Generalization where heads are partitioned into groups sharing K/V projections. MQA = 1 group; standard MHA = max groups.
- **Multihead Latent Attention (MLA)**: Low-rank approximation to MHA — projects hidden vectors to low-dimensional latent spaces before attention, minimizing KV cache to just the low-dimensional vectors.
- **Speculative decoding**: Uses a small/fast model to generate candidate tokens, then verifies them in parallel with the large model. Exploits the fact that verification (single forward pass) is cheaper than sequential generation. Incorrect speculative tokens are discarded and recomputed.
- **Multi-Token Prediction**: A single forward pass produces an embedding that is iteratively processed by additional transformer blocks to predict multiple future tokens, trading accuracy for speed.
- **Sub-quadratic attention**: Standard attention is O(N²). Reformer achieves O(N log N) via locality-sensitive hashing. BigBird achieves O(N) via random small-world networks. Attention-free transformers achieve linear memory.
- **Random Feature Attention**: Uses Fourier random features to approximate softmax attention in linear time by decomposing the kernel as an inner product of random feature maps.

## Commands and Syntax

No CLI commands. Key mathematical formulations:

- **RoPE**: `RoPE(z_m, m) = e^{imθ} · z_m` (complex form); rotation matrix applied to pairs of coordinates
- **ALiBi**: `Attention(Q,K,V) = softmax(QK^T/√d_k + sB)V` where `B_{i,j} = j - i`
- **Relative Position**: `Attention(Q,K,V) = softmax(QK^T/√d_k + B)V` where B is a Toeplitz matrix
- **MQA**: Same as MHA but with shared `W^K, W^V` across all heads (no per-head subscript i)
- **Speculative decoding cost**: `4·T_small + 3·T_large` can be less than `4·T_large` when small model is fast and accuracy is high

## Relationships

- **Activation functions** connect to feedforward sublayer design and GLU variants
- **RoPE and ALiBi** are complementary — RoPE encodes at the embedding level, ALiBi at the attention level; they can be combined
- **KV caching** directly motivates MQA, GQA, and MLA — all three reduce what must be cached
- **FlashAttention** is orthogonal to attention variants (MQA/GQA/MLA) — it optimizes the *computation* of attention, not the *formulation*
- **Speculative decoding** and **multi-token prediction** both address inference speed but from different angles (external draft model vs. internal multi-step heads)
- **Sub-quadratic methods** (Reformer, BigBird, linear attention) trade exactness for scalability to long sequences
- **RMSNorm** is a simplification of LayerNorm (removes mean-centering), reducing compute

## Exam-Relevant Points

- RoPE's key property: dot products between encoded vectors depend only on **relative** position (shift-invariant)
- ALiBi is added to attention logits (not to embeddings), uses B_{i,j} = j−i, and enables short-to-long context transfer
- MQA shares K/V projections across all heads; GQA generalizes this with groups; standard MHA is the extreme with all heads independent
- MLA uses low-rank projection to compress KV cache to low-dimensional latent vectors
- KV caching avoids recomputing K and V during autoregressive generation; prefilling is the initial pass that populates the cache
- FlashAttention is a **communication-avoiding** algorithm (block matmuls fitting GPU cache), not an approximation — it computes exact attention
- FlashAttention-2: 2x faster than v1, supports head dim up to 256, supports MQA and GQA
- Speculative decoding preserves the output distribution of the large model (for non-greedy: stochastic accept/reject)
- Standard attention complexity: O(N²); Reformer: O(N log N) via LSH; BigBird: O(N) via small-world graphs
- SwiGLU is used by Llama and PaLM; GELU by GPT-1 and BERT; original transformer used ReLU
- RMSNorm is used by Llama; it simplifies LayerNorm by removing the mean-centering step
- Causal masking alone can provide enough positional signal for a decoder to learn absolute position implicitly
- Random Feature Attention achieves linear-time attention by approximating softmax via Fourier random features (kernel approximation)
