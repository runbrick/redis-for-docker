# Sentinel Redis for Docker [HOST 模式]

**此程序不是开箱即用,请勿直接使用,请勿直接使用,请勿直接使用.**

✨ redis 1 主 2 从 3 哨兵模式.用于测试我的 Jedis，并不是最完美的配置。

✨ 目录结构

```

├── ReadMe.md
├── clear.sh
├── config
│   ├── base
│   ├── default
│   ├── redis1.conf
│   ├── redis2.conf
│   ├── redis3.conf
│   ├── sentinel1.conf
│   ├── sentinel2.conf
│   └── sentinel3.conf
├── docker-compose.yml
└── logs

```

✨ 修改所有 `replica-announce-port` 的 ip 地址为服务器地址

✨ 使用前请先执行 `init.sh` 程序初始化配置文件

✨ 配置之后就可以执行 `docker-compose up` 进行生成容器了

✨✨ 注意: 请不要在 Mac 或者 Window 下环境运行,详情参阅 :
    - [https://blog.csdn.net/Mr0o0rM/article/details/80683115](https://blog.csdn.net/Mr0o0rM/article/details/80683115)
    - [https://redis.io/topics/sentinel](https://redis.io/topics/sentinel)
    - [https://redis.io/topics/replication#configuring-replication-in-docker-and-nat](https://redis.io/topics/replication#configuring-replication-in-docker-and-nat)

✨ 如果为腾讯云或者阿里云服务器,请关闭所有安全组或者开放需要的端口并且打开服务所需要的端口