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

✨ 初始化完毕请修改 `config/*conf` 中的所有 `192.168.3.3` 改为你自己的IP.

✨ 配置之后就可以执行 `docker-compose up` 进行生成容器了

✨ 之后就可以使用 Jedis 实现链接了

```java

    HashSet<String> sentinelHost = new HashSet<String>();
    sentinelHost.add("127.0.0.1:26379");
    sentinelHost.add("127.0.0.1:26380");
    sentinelHost.add("127.0.0.1:26381");
    JedisSentinelPool pool = new JedisSentinelPool("mymaster",sentinelHost);
    Jedis jedis = pool.getResource();
    jedis.set("key01","valuePool");
    System.out.println(jedis.get("key01"));

    jedis.close();
    pool.close();


    // 返回结果 valuePool

```