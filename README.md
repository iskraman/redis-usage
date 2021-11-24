# redis-usage
Redis 설치 및 명령어 사용법

## Install
테스트를 위해 우분투 서버 기준 Redis Server와 Client를 설치하고 server를 백그라운드로 실행한다.
client를 실행시키고 ping 명령으로 통신이 잘되는지 확인한다.
```shell
$> sudo apt-get install redis-server redis-tools
$> redis-server &
                _._
           _.-``__ ''-._
      _.-``    `.  `_.  ''-._           Redis 4.0.9 (00000000/0) 64 bit
  .-`` .-```.  ```\/    _.,_ ''-._
 (    '      ,       .-`  | `,    )     Running in standalone mode
 |`-._`-...-` __...-.``-._|'` _.-'|     Port: 6379
 |    `-._   `._    /     _.-'    |     PID: 1252
  `-._    `-._  `-./  _.-'    _.-'
 |`-._`-._    `-.__.-'    _.-'_.-'|
 |    `-._`-._        _.-'_.-'    |           http://redis.io
  `-._    `-._`-.__.-'_.-'    _.-'
 |`-._`-._    `-.__.-'    _.-'_.-'|
 |    `-._`-._        _.-'_.-'    |
  `-._    `-._`-.__.-'_.-'    _.-'
      `-._    `-.__.-'    _.-'
          `-._        _.-'
              `-.__.-'


$> redis-cli
127.0.0.1:6379> PING
PONG

```

## Strings
```
127.0.0.1:6379> set mykey myvalue
OK
127.0.0.1:6379> get mykey
"myvalue"
```

