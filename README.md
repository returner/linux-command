# linux-command
## rocky linux
### git install
1. 패키지 업데이트
```bash
sudo yum update -y
```
2. git 패키지 설치
```bash
sudo yum install git -y
```
3. 설치 확인
```bash
git --version
```
4. 추가 설정
```bash
git config --global user.name "Your.Name"
git config --global user.email "Your@email.com"
```

### IP 주소 확인
```bash
ip addr show
```
```bash
hostname -I
```
```bash
ifconfig
# 만약 패키지 설치가 안되있다면
# sudo yum install net-tools -y
```
```bash
# network manager 사용
nmcli device show [인터페이스 이름]
```
