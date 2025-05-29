# Minimal Implementations


## Bidirectional LaCT Layer
The Bidirectional LaCT layer is the simplest to understand, it's conceptually similar to full sequence attention. It updates the SwiGLU-MLP fast weights using all key-value tokens, then applies these updated weights to all queries to produce the output.  See a simple implementation in `bidirectional_lact_layer.py`.


## Causal LaCT Layer with in-layer Sliding Window Attention

To handle 1D ordered sequence, like text, we need per-token causality in the modelling. This layer performs the apply-update operations iteratively over a sequence, using a predefined chunk size. A sliding window attention mechanism with shared QKV is applied, and the results are summed. See the implementation in  `causal_lact_with_sliding_window_attn.py`




