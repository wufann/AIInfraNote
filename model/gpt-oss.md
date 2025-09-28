# BLOG
https://openai.com/index/introducing-gpt-oss/

# key feature

## MXFP4 quant
Blackwell
三种 fp4 mxfp4 nvfp4：
fp4： e2m1 软件fp4，没有硬件处理scale的单元.

### mxfp4 和 nvfp4对比
mxfp4 [-6,6] e2m1 32个数一个scale，scale是8bit的e8m0,  
|            |            |             |                                  |
| ---------- | ---------- | ----------- | -------------------------------- |
| Difference | Group size | Scale dtype | Additional per  <br>tensor scale |
| MXFP4      | 32         | 8 bit E8M0  | No                               |
| NVFP4      | 16         | FP8 E4M3    | Yes                              |



## hybrid attention
swa sliding window attn + normal attn