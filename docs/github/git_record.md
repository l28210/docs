# github操作

## 仓库更新

### branch为main

```
git add /filename
git commit -m "msg"
git push origin main
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
