# ft_irc
An IRC(Internet Relay Chat) server in C++ 98.

`./ircserv <port> <password>`

## Commands
- *At the beginning of the connection*
    - **`PASS`**
        - `PASS <password>`
            - Enter the connection password.
    - **`NICK`**
        - `NICK <nickname>`
            - Set a nickname.
    - **`USER`**
        - `USER <username> <mode> <unused> <real name>`
            - Set a username, a mode, an unused character, and real name.
- **`JOIN`**
    - `JOIN <channel> [ <key> ]`
        - Create a new channel
        - Join an existing channel
- **`PRIVMSG`**
    - `PRIVMSG <*user*> <message>`
        - Send private messages to another user.
    - `PRIVMSG <*channel*> <message>`
        - Send private messages to a channel - everyone on the channel receives the message.
- **`TOPIC`**
    - `TOPIC <channel> <topic>` , `TOPIC <channel> :<topic>`
        - Set a topic on the channel.
    - `TOPIC <channel> :`
        - Clear the topic on the channel.
    - `TOPIC <channel>`
        - Check the topic on the channel.
- **`INVITE`**
    - `INVITE <user> <channel>`
        - Invite a user to the channel.
- **`KICK`**
    - `KICK <channel> <user>`
        - Kick a user from the channel.
- **`MODE`**
    - `MODE <channel>`
        - Show the channel modes.
    - `MODE <channel> +i`
        - Set the channel to invite-only.
        - `-i`
    - `MODE <channel> +t`
        - Set the restrictions of the TOPIC command to channel operators.
        - `-t`
    - `MODE <channel> +k <key>`
        - Set the channel key.
        - `-k`
        - Nothing happens if `MODE <channel> +k`.
    - `MODE <channel> +o <user>`
        - Set the user as an operator of the channel.
        - `-o`
    - `MODE <channel> +l <number of limit>`
        - Set user limits to the channel.
        - `-l`

<!-- ---

- test with `nc`
    
    ```bash
    # Make an access to ircserv
    nc -c <host> <port> # -c sends CR+LF(Carriage return, Line feed) as line ending
    
    # Start!
    PASS <password> # Enter a password for connection. ***authenticate***
    NICK <nickname> # Set a nickname.
    USER <username> <mode> <unused> <real name> # Set a username, mode, any character, and real name
    
    # Successfully entered to ircserv
    JOIN <channel> # Create a new channel / Join an existing channel
    PRIVMSG <user> <message> # Send a private message to another user.
    PRIVMSG <channel> <message> # Send a private message to a channel. Must be forwarded to every other client that joined the channel.
    
    # If you're an operator
    MODE <channel> +it # Set the channel 'invite-only' and restrict the TOPIC command to channel operators
    KICK <channel> <user> # Kick a user from channel. The user cannot enter to channel unless being invited.
    INVITE <user> <channel> # Invite a user to channel.
    TOPIC <channel> : # Check the channel topic.
    TOPIC <channel> <topic> # Set the channel topic.
    
    # ...
    ```
    
-->
---

[RFC 2812: Internet Relay Chat: Client Protocol](https://datatracker.ietf.org/doc/html/rfc2812#section-3)

[RFC 2813: Internet Relay Chat: Server Protocol](https://datatracker.ietf.org/doc/html/rfc2813)

[RFC 2811: Internet Relay Chat: Channel Management](https://datatracker.ietf.org/doc/html/rfc2811)
