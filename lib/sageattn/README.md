# install on H20
```
image: nvcr.io/nvidia/pytorch:25.06-py3

export TORCH_CUDA_ARCH_LIST="90"
git clone flash-attention 
cd flash-attention/
cd hopper
python setup.py install

cd SageAttention
pip install -e .
python bench_qk_int8_pv_fp8_cuda_sm90.py
```