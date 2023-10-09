1. Check local DNS Cache
2. ARP Query for DNS/Default Gateway
3. Default Gateway send his MAC to our Client
4. Ask DNS Server (Default Gateway) for A or AAAA record of www.h-brs.de (DNS)
5. Receive A and AAAA record from DNS Server/Default Gateway for www.h-brs.de (178.63.129.147)
6. Browser sendet HTTP Query (GET /index) from random local Port to IP (TCP)
7. Default Gateway notice the random out port. (NAT)
8. Webserver send Response to random Port of the default Gateway. (TCP)
9. Default Gateway sends to package back to our client. (TCP)

# DNS-UDP vs TCP

DNS queries are very short and have no long connection duration, it is sufficient to transmit the requests via UDP. The numerous TCP handshakes could otherwise unnecessarily burden a DNS server with TCP requests instead of DNS queries.
Delay and overhead are additional reasons for using UDP instead of TCP.

# NAT Shared-IPv4 Address

Since my brother and I use the same default gateway, we all have the same IPv4 address for the CCC web server. The sessions are distinguished by the different outgoing ports from the default gateway.

While my session goes out from port 1234 and targets port 80 of the CCC web server, my brother's session goes from 4321 to port 80. The acquired ticket was sent by the CCC web server to our shared IP address at port 4321.

However, I cannot acquire another ticket because a ticket has already been assigned to our IP.