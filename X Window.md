## X Window
1. 부팅시 GUI 모드로 설정
```bash
sudo systemctl set-default graphical.target
```
2. 부팅시 터미널 모드로 설정
```bash
sudo systemctl set-default multi-user.target
```
3. 터미널 모드에서 재부팅 없이 즉시 GUI 시작
```bash
sudo systemctl start graphical.target
```

