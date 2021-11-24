# redis-usage
Redis 설치 및 명령어 사용법

## Install
테스트를 위해 우분투 서버 기준 Redis Server와 Client를 설치하고 server를 백그라운드로 실행한다.<br>
client를 실행시키고 ping 명령으로 통신이 잘되는지 확인하고 CLI에서 명령어 사용법을 학습한다.
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

## Basic Concepts
Redis는 대표적인 NoSQL이며 메모리 DB, 캐쉬, Pub/Sub 기능등을 지원한다.<br>
Redis는 아래와 같이 5가지 Data type이 존재하며, key와 value의 쌍으로 이루어 진다.<br>
이때, String은 Key와 Value가 1:1 관계이고 나머지는 1:N의 관계로 이루어 진다.<br>

|Data Type|KEY|VALUE|
|------|---|---|
|Strings|key|value|
|Lists|key|value, value2, ...|
|Sets|key|value, value2, ...|
|Sorted Sets|key|value, value2, ...|
|Hashes|key|value, value2, ...|



## Strings

|명령어|설명|
|------|---|
|set key value|key에 value를 설정|
|get key|key의 value을 출력|
|exists key|key가 존재하는지 확인, 존재하면 1, 없으면 0|
|del key [key ...]|key를 삭제|
|keys pattern|정규 표현식을 활용해 키를 검색|


```
// mykey에 myvalue값을 할당한다.
127.0.0.1:6379> set mykey myvalue
OK

// mykey의 값을 조회한다.
127.0.0.1:6379> get mykey
"myvalue"
```





