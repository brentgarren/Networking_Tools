# Networking_Tools

Ping


The ping command is used when we want to test whether a connection to a remote resource is possible. Usually this will be a website on the internet, but it could also be for a computer on your home network if you want to check if it's configured correctly. Ping works using the ICMP protocol, which is one of the slightly less well-known TCP/IP protocols that were mentioned earlier. The ICMP protocol works on the Network layer of the OSI Model, and thus the Internet layer of the TCP/IP model. The basic syntax for ping is `ping <target>`. 
	Usage: ping <modifier> <target>
<br><pre>
Options:<br>
    -t             Ping the specified host until stopped.<br>
                   To see statistics and continue - type Control-Break;<br>
                   To stop - type Control-C.<br>
    -a             Resolve addresses to hostnames.<br>
    -n count       Number of echo requests to send.<br>
    -l size        Send buffer size.<br>
    -f             Set Don't Fragment flag in packet (IPv4-only).<br>
    -i TTL         Time To Live.<br>
    -v TOS         Type Of Service (IPv4-only. This setting has been deprecated<br>
                   and has no effect on the type of service field in the IP
                   Header).<br>
    -r count       Record route for count hops (IPv4-only).<br>
    -s count       Timestamp for count hops (IPv4-only).<br>
    -j host-list   Loose source route along host-list (IPv4-only).<br>
    -k host-list   Strict source route along host-list (IPv4-only).<br>
    -w timeout     Timeout in milliseconds to wait for each reply.
    -R             Use routing header to test reverse route also (IPv6-only).<br>
                   Per RFC 5095 the use of this routing header has been<br>
                   deprecated. Some systems may drop echo requests if<br>
                   this header is used.<br>
    -S srcaddr     Source address to use.<br>
    -c compartment Routing compartment identifier.<br>
    -p             Ping a Hyper-V Network Virtualization provider address.<br>
    -4             Force using IPv4.<br>
    -6             Force using IPv6.<br>
    <br>
    
    </pre>
    ---------------------------------------------
