# BLOG 
https://qwen.ai/blog?id=4074cca80393150c248e508aa62983f9cb7d27cd&from=research.latest-advancements-list

# KEY FEATURE
## Hybrid Architecture: Gated DeltaNet + Gated Attention
Linear Attention

we mix Gated DeltaNet with standard attention at a 3:1 ratio (75% layers use Gated DeltaNet, 25% keep standard attention).

increase head_dim from 128 to 256.

Apply rotary position encoding only to the first 25% of position dimensions

## Ultra-Sparse MoE: Activating Only 3.7% of Parameters
Qwen3-Next expands to 512 total experts, combining 10 routed experts + 1 shared expert.

## Training-Stability-Friendly Designs
QK norm

Zero-Centered RMSNorm 零中心rmsnorm.

## Multi-Token Prediction
