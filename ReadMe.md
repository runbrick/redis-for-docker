# Sentinel Redis for Docker

✨ redis 1 主 2 从 3 哨兵模式.用于测试我的 Jedis，并不是最完美的配置。

✨ 请自己清理 sentinel.conf 中的 `sentinel myid` 运行时候重新生成新的 ID

✨ 使用的时候请修改 sentinel*.conf 文件中的 `sentinel monitor mymaster xx 6379 2` 改为 `sentinel monitor mymaster redisMaster 6379 2` 让哨兵自动解析

✨ 目录结构

```
├── config
│   ├── default
│   │   ├── redis.conf
│   │   └── sentinel.conf
│   ├── redis1.conf
│   ├── redis2.conf
│   ├── redis3.conf
│   ├── sentinel1.conf
│   ├── sentinel2.conf
│   └── sentinel3.conf
├── docker-compose.yml ----------- 启动文件
└── logs
    ├── redis -------------------- redis 日志
    └── sentinel ----------------- 哨兵日志
```
✨ config - sentinel*.conf 默认配置

```conf

# sentinel auth-pass mymaster 123456
sentinel monitor mymaster redisMaster 6379 2 
logfile "/var/log/redis/sentinel.log"

```



因为 sentinel 在运行的时候会自动更改 `sentinel monitor mymaster` 获取 docker 的真实 IP . 在使用的时候请配置好 IP 获取设置为 `redisMaster` 

所有配置都是为了测试我的 Jedis. 如果线上使用请修改 redis 和 sentinel 为合理配置并强烈推荐设置密码.



**此程序不是开箱即用,请勿直接使用,请勿直接使用,请勿直接使用.**