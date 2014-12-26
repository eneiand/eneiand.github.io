#### Networking Basics
* Overview of Network Request
  * convert url to ip address by asking DNS
  * new client on a network gets an IP address by asking DHCP Server
  * Windows 2000 + ? A failed DHCP gives IP of 169.254.....
#### Name Resolution
* How does DNS work?
  * step by step starting with the DNS (Name Server) your client is configured with
  * sevans.info? DNS asks ROOT NS, then .info NS, then sevans.info NS, then answers client
    * hierarchy of name servers, each knows about the layer of NS below it 
* nslookup
  * a tool for performing dns lookup on the command line 
  * change dns server with "server" command
* DNS Caching 
  * local machine and DNS servers cache ip records
  * ipconfig /displaydns
  * dns record changes take a while to get flushed through as a result
* Hosts File
  * override dns lookups
  * system32/etc/hosts
  * contents appears in the cache
* DNS Record Types
  *  A -> name to IP Address
  *  set type in nslookup to query for other record types
  *  NS -> nameservers for the domains, eg name servers for microsoft.com
  *  MX -> mail exchanger, where to send mail to
  *  CNAME -> alias (canonical name)
  *  AAAA -> IPv6 A record
