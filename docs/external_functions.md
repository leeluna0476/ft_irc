# External Functions
- Everything in C++ 98

```cpp
// sys/socket.h
int	socket(int domain, int type, int protocol);
int	setsockopt(int socket, int level, int option_name, const void *option_value, socklen_t option_len);
int	getsockname(int socket, struct sockaddr *restrict address, socklen_t *restrict address_len);
int	bind(int socket, const struct sockaddr *address, socklen_t address_len); 
int	connect(int socket, const struct sockaddr *address, socklen_t address_len);
int	listen(int socket, int backlog);
int	accept(int socket, struct sockaddr *restrict address, socklen_t *restrict address_len);
ssize_t	send(int socket, const void *buffer, size_t length, int flags);
ssize_t	recv(int socket, void *buffer, size_t length, int flags);

// unistd.h
int	close(int filedes);
off_t	lseek(int fildes, off_t offset, int whence);

// netdb.h
struct protoent*	getprotobyname(const char *name);
struct hostent*		gethostbyname(const char *name);
int			getaddrinfo(const char *hostname, const char *servname, const struct addrinfo *hints, struct addrinfo **res);
void			freeaddrinfo(struct addrinfo *ai);

// arph/inet.h
uint16_t	htons(uint16_t hostshort);
uint32_t	htonl(uint32_t hostlong);
uint16_t	ntohs(uint16_t netshort);
uint32_t	ntohl(uint32_t netlong);
in_addr_t	inet_addr(const char *cp);
char*		inet_ntoa(struct in_addr in);

// signal.h
void	(*signal(int sig, void (*func)(int)))(int);
int	sigaction(int sig, const struct sigaction *restrict act, struct sigaction *restrict oact);

// sys/stat.h
int	fstat(int fildes, struct stat *buf);

// fcntl.h
int	fcntl(int fildes, int cmd, ...);

// poll.h
int	poll(struct pollfd fds[], nfds_t nfds, int timeout); // or equivalent
```
