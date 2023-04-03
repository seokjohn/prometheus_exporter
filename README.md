# xops monitoring
use 
- prometheus
- 'cadvisor'
- 'node_exporter'
- 'dcgm_exporter'
- 'cadvisor'

## Install
### Docker nvidia-container-toolkit 설치
```
> istribution=$(. /etc/os-release;echo $ID$VERSION_ID) \
   && curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add - \
   && curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list
> sudo apt-get update && sudo apt-get install -y nvidia-container-toolkit
> sudo systemctl restart docker
```
### Setting
```
web.yml 파일 생성 및 id, pwd 설정
ex)
basic_auth_users:
  admin: 1234
```
### Run
```
# run 
docker compose -f xops_monitoring.yml up -d
# stop
docker compose -f xops_monitoring.yml down
```