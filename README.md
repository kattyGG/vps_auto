
### search *.ssh 找公钥，upload。可以使用说是登录 ssh-rsa 

### 查看GPU用量
```sh
nvidia-smi
```

### `touch ~/.no_auto_tmux` 连接后是 tmux。需要退出后再执行其他  Ctrl +b  D 退出当前tmux
```sh
wget /upload.py 
tmux new-session -d -s upload
tmux attach-session -t upload
python3 upload.py 
Ctrl +b  D
tmux new-session -d -s cloudupload "cloudflared tunnel --url http://127.0.0.1:8188 >> /workspace/cloudupload.log 2>&1"
cat cloudupload.log
```


