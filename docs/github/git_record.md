# github操作

## 仓库更新

### branch为main

```
git add /filename
git commit -m "msg"
git push origin main
```

- 查看工作区改动
```
git checkout
```


- 查看远程分支

```
git branch -a
```

- 查看本地分支

```
git branch
```

- 连接超时

原因：Git所设端口与代理不一致

- 修改Git网络设置

```
git config --global http.proxy http://127.0.0.1:7890 
git config --global https.proxy http://127.0.0.1:7890
```

- 取消代理
```
git config --global --unset http.proxy
git config --global --unset https.proxy
```

- 查看代理

```
git config --global --get http.proxy
git config --global --get https.proxy
```

### 密码失效
```
remote: Invalid username or password. fatal: 'https://github.com/l28210/docs.git/' 鉴权失败
```
- 需要重新生成token

- 查看远程分支联系
```
git remote -v
```

### git pull
```
Username for 'https://www.usilab.cn': liaojiahui
Password for 'https://liaojiahui@www.usilab.cn': 
来自 https://www.usilab.cn/git/liaojiahui/Aruco_Location
 * branch            master     -> FETCH_HEAD
error: 您对下列文件的本地修改将被合并操作覆盖：
	README.md
请在合并前提交或贮藏您的修改。
正在终止
```

