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
* Wildcard Records
	* a setup such that any subdomain will return the same IP address
* IP Routing
	* IP Routing Overview and Troubleshooting
		* router connects different subnets
		* tracert on a name or ip address -> what's the route + timings of each hop
		* pathping -> performs tests on each link, lost packets for example
		* subnet is a combination of IP + subnet mask
			* 4 octets eg. 255.255.255.000
			* where the subnet mask is on it represents a network, where it is off it represents a node on that network
			* defines a range of valid ip addresses on the same subnet
			* 255.255.255.000  = 192.168.12.0 - 192.168.12.255
			* if a machine needs to access an ip within that range it can go directly, otherwise it needs to use the default route
		* route table => how to find other subnets
			* route command, 'route print' prints the route table
			* default gateway comes from network configuration
		* NAT -> Network Address Translation to convert public IP to private IP address
* Port Connectivity
	* TCP and UDP 
		* TCP involves a session and confirms each data set, any missing data set is re transmitted
		* UDP does not establish a session, just sends, great for situations where lost data doesn't matter (video conferencing)
	* Testing Port Connectivity
		* telnet (tcp) with a domain name and port number (pluralsight.com 80)
		* no UDP session so difficult to figure out if a UDP port is open
		* nmap will do port scanning
		* netstat will show on this machine what ports are being used by what process
	* Firewalls
		* determines what connections/traffic/ports are allowed in
		* can set rules by exe, port, tcp/udp etc.
	* NAT and Private IP's
		* public IP to private IP translation
		* a service listening for traffic won't be routable, need to setup port forwarding (traffic for port x -> a particular IP)
* Network Capture
	* Wireshark -> any traffic
	* Fiddler -> HTTP