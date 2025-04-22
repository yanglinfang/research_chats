<summary>测试环境</summary>

### Docker

First build docker 
`docker build -t my-vllm .`

then run with gpu enabled: 
`docker run --gpus all -p 8000:8000 my-vllm --concurrency 8 --max-batch-tokens 4096`

if not working, try this instead
`docker run --gpus all -p 8000:8000 my-vllm --gpu-memory-utilization 0.90 --max-num-batched-tokens 4096 --max-num-seqs 128`
