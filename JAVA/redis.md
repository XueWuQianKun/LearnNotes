### redis集群密码修改

> 注：

> 修改配置文件的密码后，redis的实际密码未修改，以下可以修改redis集群密码，实测可用

> #### 1、登录redis 

```shell
redis-cli -c -h 地址 -p 端口
```

> #### 2、认证

```shell
auth 密码
```

> #### 3、修改密码

```shell
config set masterauth 新密码 
config set requirepass 新密码 
config rewrite
```

