# 临时租用vps的常用命令行

### search *.ssh 找公钥，upload。可以使用说是登录 ssh-rsa 

### 查看GPU用量
```sh
nvidia-smi
```

### `touch ~/.no_auto_tmux` 连接后是 tmux。需要退出后再执行其他  Ctrl +b  D 退出当前tmux

```sh
wget ****safetensors/upload.py 
tmux new-session -d -s upload   #新进程
tmux attach-session -t upload   #8109进入进程
python3 upload.py     # upload 程序
Ctrl +b  D     # 退出进程
tmux new-session -d -s cloudupload "cloudflared tunnel --url http://127.0.0.1:8109 >> /workspace/cloudupload.log 2>&1"
tmux new-session -d -s cloud8188 "cloudflared tunnel --url http://127.0.0.1:8188 >> /workspace/cloud8188.log 2>&1"

cat cloudupload.log
Ctrl +b  D     # 退出进程
```

杀进程
```sh
kill $(ps aux | grep "python -m http.server 8390" | grep -v grep | awk '{print $2}')
kill $(ps aux | grep "cloudflared tunnel --url http://localhost:8390 --metrics localhost:28390" | grep -v grep | awk '{print $2}')
```


```sh
tmux new-session -d -s runllm   #新进程,,运行python程序
tmux attach-session -t runllm
```

查看文件夹下的所有子文件夹大小：
```sh
du -h --max-depth=1 /path/to/directory
du -h --max-depth=1 comfyui_controlnet_aux/
du -h --max-depth=1 /workspace/ComfyUI/models/
```





