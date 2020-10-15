# Sentinel Redis for Docker

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

✨ 使用前请先执行 `init.sh` 程序初始化配置文件

✨ 配置之后就可以执行 `docker-compose up` 进行生成容器了

