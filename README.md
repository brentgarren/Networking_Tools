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
    
  </pre><br>
	
	
---------------------------------------------
	
<br><pre>
The logical follow-up to the ping command is 'traceroute'. Traceroute can be used to map the path your request takes as it heads to the target machine.  
  
The internet is made up of many, many different servers and end-points, all networked up to each other. This means that, in order to get to the content you actually want, you first need to go through a bunch of other servers. Traceroute allows you to see each of these connections -- it allows you to see every intermediate step between your computer and the resource that you requested. The basic syntax for traceroute on Linux is this: `traceroute <destination>`

By default, the Windows traceroute utility (`tracert`) operates using the same ICMP protocol that ping utilises, and the Unix equivalent operates over UDP. This can be altered with switches in both instances.

	NAME
       traceroute - print the route packets trace to network host

SYNOPSIS
       traceroute [-46dFITUnreAV] [-f first_ttl] [-g gate,...]
               [-i device] [-m max_ttl] [-p port] [-s src_addr]
               [-q nqueries] [-N squeries] [-t tos]
               [-l flow_label] [-w waittimes] [-z sendwait] [-UL] [-D]
               [-P proto] [--sport=port] [-M method] [-O mod_options]
               [--mtu] [--back]
               host [packet_len]
       traceroute6  [options]
       tcptraceroute  [options]
       lft  [options]

DESCRIPTION
       traceroute  tracks the route packets taken from an IP network on their way to a given
       host. It utilizes the IP protocol's time to live (TTL) field and attempts  to  elicit
       an ICMP TIME_EXCEEDED response from each gateway along the path to the host.

       traceroute6 is equivalent to traceroute -6

       tcptraceroute is equivalent to traceroute -T
</pre><br>

----------------------------------------

<br><pre>

Domain Names -- the unsung saviours of the internet.

Can you imagine how it would feel to remember the IP address of every website you want to visit? Horrible thought.

Fortunately, we've got domains.

We'll talk a little bit more about how this works in the next task, but for now suffice to know that a domain translates into an IP address so that we don't need to remember it (e.g. you can type tryhackme.com, rather than the TryHackMe IP address). Domains are leased out by companies called Domain Registrars. If you want a domain, you go and register with a registrar, then lease the domain for a certain length of time. 

Enter Whois.

Whois essentially allows you to query who a domain name is registered to. In Europe personal details are redacted; however, elsewhere you can potentially get a great deal of information from a whois search.

There is a [web version](https://www.whois.com/whois/) of the whois tool if you're particularly adverse to the command line. Either way, let's get started!

_(Note: You may need to install whois before using it. On Debian based systems this can be done with_ `sudo apt update && sudo apt-get install whois`_)_

Whois lookups are very easy to perform. Just use `whois <domain>` to get a list of available information about the domain registration:
	NAME
       whois - client for the whois directory service

SYNOPSIS
       whois  [  {  -h  |  --host  }  HOST  ] [ { -p | --port } PORT ] [ -abBcdGHIKlLmMrRx ]
       [ -g SOURCE:FIRST-LAST ] [ -i  ATTR[,ATTR]...  ]  [  -s  SOURCE[,SOURCE]...  ]  [  -T
       TYPE[,TYPE]... ] [ --verbose ] [ --no-recursion ] OBJECT

       whois -q KEYWORD

       whois -t TYPE

       whois -v TYPE

       whois --help

       whois --version

DESCRIPTION
       whois searches for an object in a RFC 3912 database.

       This version of the whois client tries to guess the right server to ask for the spec‐
       ified object. If no guess can be made it will connect  to  whois.networksolutions.com
       for NIC handles or whois.arin.net for IPv4 addresses and network names.
       
 </pre><br>

----------------------------------

<pre>
Dig allows us to manually query recursive DNS servers of our choice for information about domains:
dig < domain > @< dns-server-ip >
</pre><br>

----------------------------------
