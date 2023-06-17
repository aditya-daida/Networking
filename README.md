
# Networking for DevOps

Networking Concepts usefull for Devops


##  OSI Model
			Layer 1: Physical
			Layer 2: Data Link
			Layer 3: Network
			Layer 4: Transport
			Layer 5: Session
			Layer 6: Presentation
			Layer 7: Application

##  TCP/IP
			Application
			Transport
			Network
			Network Interface
##   Ports and Protocols
      Port Number   	  Process     	Usage
      22	              SSH	      Secure shell, remote access, and file transfer
      53	              DNS	      Resolving domain names into IP addresses
      80	              HTTP	    Serving web pages
      443               HHTPs	    Serving web pages in a secure manner
      3306            	MySQL	    Database connections

##  IP Subnetting, CIDR
	Prefix	    Netmask             Number of addresses	   Relation to class	
	/32	    255.255.255.255              1	                  Class C/256
	/25	    255.255.255.128             128                   Class C/2
	/24	    255.255.255.0               256                   Class C		
	/23	    255.255.254.0               512	                  Class C*2
	/16	    255.255.0.0                65,536                 Class C*256 = Class B
	/15	    255.254.0.0                131,072                Class B*2	
	/8	    255.0.0.0	              16,777,216              Class B*256 = Class A

##  OSI Model
			Layer 1: Physical
			Layer 2: Data Link
			Layer 3: Network
			Layer 4: Transport
			Layer 5: Session
			Layer 6: Presentation
			Layer 7: Application

## Domain Name System (DNS)

The Domain Name System (DNS) is a fundamental component of the internet infrastructure that translates human-readable domain names into the numerical IP addresses used by computers to identify and communicate with each other. DNS serves as a distributed database or directory that allows users to access websites, send emails, and perform various network activities using domain names instead of having to remember the specific IP addresses associated with each resource.

Here's an overview of how DNS works:

Domain Names: Domain names are hierarchical and organized from right to left, with the top-level domain (TLD) at the rightmost position (e.g., .com, .org, .net) followed by the second-level domain (SLD) and subsequent subdomains (e.g., example.com, subdomain.example.com).

DNS Resolvers: When a user enters a domain name in a web browser or initiates any network activity, the user's device sends a DNS query to a DNS resolver (also called a recursive resolver). The resolver is typically provided by the user's internet service provider (ISP) or can be a public resolver like Google DNS or Cloudflare DNS.

DNS Recursion: The resolver initiates a recursive process to resolve the DNS query. It first checks if the queried information is already present in its cache. If not, it contacts the root DNS servers.

Root DNS Servers: The root DNS servers are a crucial part of the DNS hierarchy. They maintain a list of authoritative DNS servers for the top-level domains (TLDs). There are a limited number of root DNS servers worldwide.

TLD DNS Servers: Based on the TLD in the query, the root DNS server responds with the IP address of the authoritative DNS server for that specific TLD.

Authoritative DNS Servers: The resolver then contacts the authoritative DNS server responsible for the domain name's zone. These servers are operated by domain owners or their DNS service providers. They store the DNS records containing the mapping of domain names to IP addresses or other relevant information.

DNS Records: The authoritative DNS server checks its records and responds to the resolver with the requested information, such as the IP address associated with the domain name.

DNS Response: The resolver receives the IP address from the authoritative DNS server and caches it for future use. It then returns the IP address to the user's device.

Network Communication: With the obtained IP address, the user's device can now establish a connection with the appropriate server hosting the desired resource, such as a website, email server, or any other network service.

DNS operates behind the scenes, enabling users to access internet resources by simply entering domain names instead of IP addresses. It plays a crucial role in ensuring the efficient and reliable functioning of the internet.
## HTTP
### HTTP Methods

HTTP methods, also known as HTTP verbs, are used in the Hypertext Transfer Protocol (HTTP) to indicate the desired action to be performed on a resource. Most commonly used HTTP methods:

1. GET: Retrieves a representation of a resource identified by a given URL. It is a safe and idempotent method, meaning that multiple identical requests will produce the same result as a single request.

2. POST: Submits data to be processed to a specified resource. It is often used to create new resources or send data to a server for further processing. POST requests are not idempotent, as sending the same request multiple times may result in multiple resources being created.

3. PUT: Updates a resource identified by a specific URL with the enclosed representation. It is used to replace or create a resource at the given URL. PUT requests are idempotent, meaning that sending the same request multiple times will have the same effect as a single request.

4. DELETE: Deletes the specified resource identified by the given URL. It removes the resource from the server. Like PUT, DELETE requests are idempotent.

5. PATCH: Partially updates a resource identified by a specific URL. It is used to apply partial modifications to a resource. Unlike PUT, which replaces the entire resource, PATCH updates only the specified changes.

6. HEAD: Performs a similar function to GET but retrieves only the headers of a resource, without the actual content. It is often used to obtain meta-information about a resource, such as its size or modification date.

7. OPTIONS: Retrieves the HTTP methods supported by a given URL or resource. It allows the client to determine which methods are allowed for a specific resource.

### HTTP Response Codes

HTTP response codes are three-digit numbers that indicate the status of a request made by a client to a server over the Hypertext Transfer Protocol (HTTP). Here's a short summary of some common HTTP response codes:

1xx Informational:
- 100 Continue: The initial part of the request has been received, and the client can proceed with sending the remainder.

2xx Success:
- 200 OK: The request was successful, and the server has returned the requested content.
- 201 Created: The request has been fulfilled, resulting in the creation of a new resource.
- 204 No Content: The server successfully processed the request, but there is no content to return.

3xx Redirection:
- 301 Moved Permanently: The requested resource has been permanently moved to a new location.
- 302 Found: The requested resource has been temporarily moved to a different location.
- 304 Not Modified: The resource has not been modified since the last request, and the cached version is still valid.

4xx Client Errors:
- 400 Bad Request: The server cannot understand the request due to malformed syntax or other client-side error.
- 401 Unauthorized: The request requires user authentication.
- 404 Not Found: The requested resource could not be found on the server.

5xx Server Errors:
- 500 Internal Server Error: A generic server error occurred, indicating that something went wrong on the server.
- 503 Service Unavailable: The server is currently unavailable or overloaded, often due to maintenance or high traffic.
- 504 Gateway Timeout: The server acting as a gateway or proxy did not receive a timely response from an upstream server.

### HTTP Headers
HTTP headers allow the client to add additional information to a request for purposes such as authentication, caching, and specifying the type of client device sending the request. Headers are widely used to control traffic and implement features such as canary releases, blue-green deployments, and a/b testing.

Headers fall into 4 general contexts:

General Header: A header that works for both response and requests messages.
Request Header: A header that only applies to request messages from a client.
Response Header: A header that only applies to responses from a server.
Entity Header: A header that gives information about the entity itself or the resource requested.
Headers are case-insensitive in the structure Name: Value.

## Network Troubleshooting Tools
Ping

```bash
usage: ping [options] destination
```
Traceroute
```bash
usage: traceroute [options] destination
```    
Telnet
```bash
usage: telnet [options] [host] [port]
```
Curl
```bash
usage: curl https://example.com
```
Dig
```bash
usage: dig example.com
```
Netstat
```bash
usage: netstat [options]
```
Nmap
```bash
usage: nmap -p <ports> <target>
```
