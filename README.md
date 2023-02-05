# docker_note
## 1. Run docker with CUDA
- Download docker image cuda runtime:
```bash
docker pull nvidia/cuda:11.8.0-runtime-ubuntu22.04
```
- run container
```bash
docker run -itd --name test_cuda -p 5000:5000 --gpus all -v ${PWD}:/home/data_docker nvidia/cuda:11.8.0-runtime-ubuntu22.04
```
