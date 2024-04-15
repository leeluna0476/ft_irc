# ft_irc
> Internet Relay Chat 또는 IRC는 인터넷의 텍스트 기반 통신 프로토콜이다.  공개 또는 비공개가 가능한 실시간 통신을 제공한다.  유저들은 직접적으로 메세지를 주고받고 그룹 채널에 참여할 수 있다.

> IRC 클라이언트들은 채널에 참여하기 위해 IRC 서버에 연결한다. IRC 서버들은 서로 연결되어 하나의 네트워크를 형성한다.

## Mandatory Part
<!--|||-->
<!--|---|---|-->
<!--|Program name|ircserv|-->
<!--|Turn in files|Makefile, *.{h, hpp}, *.cpp, *.tpp, *.ipp, an optional configuration file|-->
<!--|Makefile|NAME, all, clean, fclean, re|-->
<!--|Arguments|port: The listening port password: The connection password|-->
<!--|External functs.|Everything in C++ 98 socket, close, setsockopt, getsockname, getprotobyname, gethostbyname, getaddrinfo, freadaddrinfo, bind, connect, listen, accept, htons, htonl, ntohs, ntohl, inet_addr, inet_ntoa, send, recv, signal, sigaction, lseek, fstat, fcntl, poll (or equivalent)|-->
<!--|Libft authorized|n/a|-->
<!--|Description|An IRC server in C++ 98|-->
