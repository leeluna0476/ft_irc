# ft_irc
An IRC(Internet Relay Chat) server developed in C++ 98.

`./ircserv <port> <password>`
## Features
- KICK - Eject a client from the channel
- INVITE - Invite a client to a channel
- TOPIC - Change or view the channel topic
- MODE - Change the channel's mode
  - i: Set/remove Invite-only channel
  - t: Set/remove the restrictions of the TOPIC command to channel operators
  - k: Set/remove the channel key (password)
  - o: Give/take channel operator privilege
  - l: Set/remove the user limit to channel
