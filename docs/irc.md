# IRC
[Internet Relay Chat](https://en.wikipedia.org/wiki/IRC)

Internet Relay Chat(이하 IRC)은 텍스트 기반의 실시간 채팅 시스템이다.

IRC는 *채널*이라고 불리는 토론 포럼에서의 그룹 통신을 위해 설계되었지만, 일대일 비공개 통신은 물론 채팅, 파일 공유를 포함한 데이터 전송도 허용한다.

IRC는 텍스트 형태의 통신을 용이하게 하기 위해 application layer protocol로 구현되어 있다. 

채팅은 client-server networking model로 동작한다. 사용자들은 다양한 클라이언트로 서버에 접속한다.

IRC 프로토콜은 RFC(Requests For Comments)를 통해 공개되어 있다.

현존하는 모든 클라이언트-서버 IRC 프로토콜들은 IRC2server의 irc2.8 버전에서 구현된 프로토콜에서 나왔다. 이 프로토콜은 [RFC 1459 - Internet Relay Chat: Server Protocol](https://datatracker.ietf.org/doc/html/rfc1459) 문서에 규정되어 있다.

```
                          1--\
                              A        D---4
                          2--/ \      /
                                B----C
                               /      \
                              3        E

   Servers: A, B, C, D, E         Clients: 1, 2, 3, 4
```
