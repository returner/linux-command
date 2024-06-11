## docker 설치
1. 시스템 업데이트
```bash
sudo yum update -y
```
2. docker 저장소 추가
```bash
sudo yum install -y yum-utils
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```
3. docker 설치
```bash
sudo yum install -y docker-ce docker-ce-cli containerd.io
```
4. docker 서비스 시작및 활성화
```bash
# demon 시작하고 부팅시 자동 활성화
sudo systemctl start docker
sudo systemctl enable docker
```
5. 설치 확인
```bash
sudo docker --version
```
6. hello-world
```bash
sudo docker run hello-world
```