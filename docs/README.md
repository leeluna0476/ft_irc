# Mandatory Part
![](pics/requirements.png)

C++ 98로 IRC 서버를 개발해야 한다.
[Internet Relay Chat](https://en.wikipedia.org/wiki/IRC)

클라이언트를 개발해서는 안된다.

서버 간 통신을 처리해서는 안된다.

실행 파일은 다음과 같이 실행될 것이다:
`./ircserv <port> <password>`

- **port**: IRC 서버가 들어오는 IRC 연결을 수신할 포트 번호.
- **password**: IRC 서버에 연결할 비밀번호. 서버에 연결을 시도하는 모든 클라이언트에게 필요하다.

> subject와 evaluation scale에는 `poll()`이 언급되지만 `select()`, `kqueue()`, `epoll()` 등 상응하는 함수를 사용할 수 있다.

## Requirements
- 서버는 다중 클라이언트를 동시에 처리할 수 있어야 하며 중단되지 말아야 한다.
- Forking은 허용되지 않는다. 모든 I/O 동작은 **non-blocking**으로 동작해야 한다.
- 이 모든 작업(read, write, but also listen, and so forth)을 처리하는 데 오직 하나의 `poll()`(또는 상응하는 것)만 사용할 수 있다.

> non-blocking 파일 디스크립터를 사용해야 하기 때문에 `poll()`(또는 상응하는 것) 없이 `read/recv` 또는 `write/send` 함수들을 사용하는 것이 가능하지만, 이것은 시스템 자원을 더 많이 소모한다. 그렇기에 만일 `poll()`(또는 상응하는 것)을 사용하지 않고 그 어떤 파일 디스크립터에 `read/recv` 또는 `write/send`를 사용한다면 점수는 0이 될 것이다.

- IRC 클라이언트는 여러 종류가 있다. 그 중 하나를 참고하라. 이는 평가 때 사용될 것이다.
- 클라이언트는 서버에 오류 없이 접속해야 한다.
- 클라이언트와 서버 간 통신은 TCP/IP (v4 of v6)로 이루어져야 한다.
- 서버에서 클라이언트를 사용하는 것은 실제 IRC 서버와 비슷하게 동작해야 한다. 그러나 다음 기능만 구현하면 된다:
  - 클라이언트를 사용해서 인증, 닉네임 설정, 사용자 이름 설정, 채널 참여, 비공개 메시지를 주고받을 수 있어야 한다.
  - 한 클라이언트가 채널에 보낸 메시지는 해당 채널에 참여한 모든 클라이언트에게 전달되어야 한다.
  - 운영자와 일반 사용자가 있어야 한다.
  - 다음과 같은 명령들을 구현해야 한다.
    - KICK - Eject a client from the channel
    - INVITE - Invite a client to a channel
    - TOPIC - Change or view the channel topic
    - MODE - Change the channel's mode
      - i: Set/remove Invite-only channel
      - t: Set/remove the restrictions of the TOPIC command to channel operators
      - k: Set/remove the channel key (password)
      - o: Give/take channel operator privilege
      - l: Set/remove the user limit to channel
- 깔끔한 코드를 작성해야 한다.

### For MacOS only
> MacOS는 `write()`를 다른 UnixOS들처럼 구현하지 않기 때문에, `fcntl()`을 사용하는 것을 허용한다. 다른 UnixOS들과 비슷하게 동작하도록 하기 위해 파일 디스크립터를 non-blocking 모드로 사용해야 한다.

> 파일 디스크립터는 다음과 같은 형태로만 사용할 수 있다:
> `fcntl(fd, F_SETFL, O_NONBLOCK);`
> 다른 모든 플래그는 금지된다.
