## jenkins 설치
1. java 설치
```bash
sudo yum install -y java-11-openjdk-devel
```
2. jenkins 저장소 추가
```bash
sudo yum install -y wget
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
```
3. jenkins 설치
```bash
sudo yum install -y jenkins
```
4. 서비스 시작및 활성화
```bash
sudo systemctl start jenkins
sudo systemctl enable jenkins
```
5. 방화벽 설정 - 기본 8080
```bash
sudo firewall-cmd --permanent --zone=public --add-port=8080/tcp
sudo firewall-cmd --reload
```
6. 초기 설정
```bash
http://ip-address:8080
```
7. 관리자 비밀번호 확인
```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
## jenkins 기본포트 변경
1. jenkins 설정 파일 수정
```bash
sudo vi /etc/sysconfig/jenkins
```
```bash
# Port Jenkins is listening on.
JENKINS_PORT="8080" # <=여기를 변경
```
2. 서비스 재시작
```bash
sudo systemctl restart jenkins
```
3. 방화벽 설정 업데이트
```bash
sudo firewall-cmd --permanent --zone=public --add-port=8090/tcp
sudo firewall-cmd --reload
```
4. 기존 방화벽 규칙제거 (상황에 따라)
```bash
sudo firewall-cmd --permanent --zone=public --remove-port=8080/tcp
sudo firewall-cmd --reload
```
5. 접속 테스트
