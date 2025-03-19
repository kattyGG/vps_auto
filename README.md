
### search *.ssh 找公钥，upload。可以使用说是登录 ssh-rsa 

### 查看GPU用量
```sh
nvidia-smi
```

### `touch ~/.no_auto_tmux` 连接后是 tmux。需要退出后再执行其他  Ctrl +b  D 退出当前tmux
```sh
wget /upload.py 
tmux new-session -d -s upload   #新进程
tmux attach-session -t upload   #进入进程
python3 upload.py     # upload 程序
Ctrl +b  D     # 退出进程
tmux new-session -d -s cloudupload "cloudflared tunnel --url http://127.0.0.1:8109 >> /workspace/cloudupload.log 2>&1"
cat cloudupload.log
```
```sh
tmux attach-session -t cloudupload    #进进程
```


