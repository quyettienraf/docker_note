# docker_note
## 1. Run docker with CUDA
- Download docker image cuda runtime:
```bash
docker pull nvidia/cuda:11.8.0-runtime-ubuntu22.04
```
- run container in window
```bash
docker run -itd --name test_cuda -p 5000:5000 --gpus all -v ${PWD}:/home/data_docker nvidia/cuda:11.8.0-runtime-ubuntu22.04
```
# vss-checkin

# server 109
3000  -> 9300
5000  -> 9500
5005  -> 9505

# build docker file
```bash
docker build -t vss_checkin:verion1 -f Dockerfile .
```
# exec docker container 
```bash
docker exec -it "docker_container_name" /bash
```
- example: 
```bash
docker exec -it checkin_container /bash
```

# run folder docker 
```bash
docker run -itd --name "docker_container_name" -p 5000:5000 --mount source=ai-checkin,destination=/home/ vss_checkin:verion1
```
- example: 
```bash
docker run -itd --name checkin_container -p 5000:5000 --mount type=bind,source="$(pwd)"/ai-checkin,destination=/home vss_checkin:verion1
```

# restart docker container
```bash
docker restart "my_container"
```
- example: 
```bash
docker restart checkin_container
```

# stop container 
```bash
docker stop my_container
```
- ex: 
```bash
docker stop checkin_container
```

# show log container 
```bash
sudo docker logs -f checkin_container
```

