OSI (Open Systems Interconnection) Model :

The OSI (Open Systems Interconnection) Model is a conceptual framework that divides
network communication into 7 distinct layers. Each layer handles a specific networking job and
passes data to the layers directly above and below it.
Here is a clean, point-wise set of notes covering all 7 layers from top (Layer 7) to bottom (Layer
1), including their functions, data units, and examples.

Quick Memory Tricks (Mnemonics)
Top to Bottom (7 to 1): All People Seem To Need Data Processing
Bottom to Top (1 to 7): Please Do Not Throw Sausage Pizza Away

Layer 7: Application Layer
Primary Function: Provides direct network services and an interface for end-user software
applications.
What Happens Here: It enables apps (like web browsers or email clients) to communicate
over the network. Note that this is not the app itself, but the protocols the app uses.
Data Unit (PDU): Data
Common Protocols & Examples: HTTP/HTTPS (web browsing), SMTP/IMAP (email), FTP
(file transfer), DNS (domain names).

Layer 6: Presentation Layer
Primary Function: Translates, encrypts, and compresses data so different systems can
understand each other.
What Happens Here: Acts as the network's translator. It formats text, images, and videos,
handles encryption/decryption for security, and compresses data to speed up transfers.
Data Unit (PDU): Data
Common Formats & Protocols: SSL/TLS (encryption), JPEG, PNG, MP4, ASCII, UTF-8.

Layer 5: Session Layer
Primary Function: Establishes, manages, and terminates communication sessions
between two devices.
What Happens Here: Opens a connection channel, keeps it active while data is exchanged,
places checkpoints (so large downloads don't restart from zero if interrupted), and closes the
session cleanly.
Data Unit (PDU): Data
Common Protocols & Examples: NetBIOS, RPC (Remote Procedure Call), PPTP, APIs.

Layer 4: Transport Layer

Primary Function: Delivers data reliably and completely from one device to another across
the network.
What Happens Here: Breaks large data into smaller chunks (segments), manages flow
control (preventing overload), and checks for errors. It uses port numbers to send data to the
right application.
Data Unit (PDU): Segment (TCP) or Datagram (UDP)
Common Protocols: TCP (reliable, connection-oriented, guaranteed delivery) and UDP
(fast, connectionless, best for streaming/gaming).

Layer 3: Network Layer
Primary Function: Handles logical addressing and determines the best physical path
(routing) for data to travel across different networks.
What Happens Here: Assigns IP addresses to devices and routes packets from the source
network to the destination network across the internet.
Data Unit (PDU): Packet
Common Protocols & Devices: IP (IPv4, IPv6), ICMP (ping), Routers, Layer 3 Switches.

Layer 2: Data Link Layer
Primary Function: Handles node-to-node data transfer on the same local network and
detects physical transmission errors.
What Happens Here: Uses hardware MAC addresses to deliver frames between devices
on a local network (LAN). It consists of two sublayers: LLC (Logical Link Control) and MAC
(Media Access Control).
Data Unit (PDU): Frame
Common Protocols & Devices: Ethernet, Wi-Fi (802.11), ARP, Switches, Bridges.

Layer 1: Physical Layer
Primary Function: Transmits raw binary data (1s and 0s) over a physical medium.
What Happens Here: Converts digital bits into electrical signals, light pulses, or radio
waves and sends them across physical hardware.
Data Unit (PDU): Bit
Common Hardware & Media: Ethernet cables (Cat5e/Cat6), fiber-optic cables, radio
frequencies (Wi-Fi signals), Hubs, Repeaters.

Quick Revision Summary Table
Layer Name Key Role Addressing / Unit Key Hardware /
Protocol
7 Application End-user network services Data HTTP, DNS, SMTP
6 Presentation Encryption, translation,

compression Data TLS/SSL, JPEG,

ASCII

5 Session Opens, maintains, closes

connections Data NetBIOS, RPC

4 Transport Reliable delivery & port

numbers

Port Numbers /
Segments TCP, UDP

3 Network Logical addressing & routing IP Address /

Packets Routers, IP, ICMP

2 Data Link Local device-to-device

delivery

MAC Address /
Frames Switches, Ethernet

1 Physical Sends raw 1s and 0s over

hardware Bits Cables, Fiber, Hubs

TCP/IP Model :

Layer 4: Application Layer (Top)
Primary Function: Combines the top three layers of the OSI model (Application,
Presentation, and Session) to handle user-facing network services, data formatting, and session
control.
What Happens Here: Allows software applications to send and receive data over the
network.
Key Protocols:
HTTP / HTTPS: Powers web browsing (HTTPS adds TLS encryption).
DNS (Domain Name System): Translates human-friendly domain names (like google.com)
into IP addresses.
SMTP / IMAP / POP3: Handles sending and receiving emails.
DHCP: Automatically assigns IP addresses to devices joining a network.
SSH / FTP: Secures remote server logins (SSH) and transfers files (FTP).

Layer 3: Transport Layer
Primary Function: Manages end-to-end communication between devices and directs data
to the right application using port numbers.
What Happens Here: Breaks data into smaller pieces, manages flow control, and ensures
reliability when needed.
Key Protocols:
TCP (Transmission Control Protocol): Connection-oriented and reliable. It uses a 3-way
handshake (SYN, SYN-ACK, ACK) to establish a connection, guarantees packets arrive in
order, and resends lost data. Used for web browsing, emails, and file transfers.
UDP (User Datagram Protocol): Connectionless and fast. It sends data without checking if
it arrived, avoiding handshake delays. Used for live video streaming, online gaming, and voice
calls (VoIP).

Layer 2: Internet Layer
Primary Function: Handles logical addressing and routes data packets across different
networks to reach their final destination.
What Happens Here: Equivalent to the OSI Network Layer. It determines the best path
across routers on the internet.
Key Protocols:
IP (Internet Protocol - IPv4 & IPv6): Assigns unique logical IP addresses to every device
and wraps data into packets for delivery.

ICMP (Internet Control Message Protocol): Sends diagnostic and error messages (used
by tools like ping and traceroute).
ARP (Address Resolution Protocol): Maps a known logical IP address to a physical
hardware MAC address on a local network.

Layer 1: Network Access / Link Layer (Bottom)
Primary Function: Combines the OSI Data Link and Physical layers to manage how data is
physically sent over local hardware.
What Happens Here: Handles MAC addressing, error detection on the physical wire, and
converting digital bits into electrical, optical, or radio signals.
Key Technologies & Standards: Ethernet (wired LAN), Wi-Fi / IEEE 802.11 (wireless
LAN), fiber-optic links, and network interface cards (NICs).

OSI Model vs. TCP/IP Model Comparison
TCP/IP Layer (4
Layers) Equivalent OSI Layers (7 Layers) Core Responsibility
4. Application Application, Presentation, Session

(Layers 5–7)

User apps, encryption, data formatting,
and sessions.

3. Transport Transport (Layer 4) Reliable/fast delivery (TCP/UDP) and

port numbers.

2. Internet Network (Layer 3) IP addressing and routing across

networks.

1. Network Access Data Link, Physical (Layers 1–2) MAC addressing, frames, and physical

cables/signals.

DNS (Domain Name System) and HTTP/HTTPS (Hypertext Transfer Protocol / Secure) are
core Application Layer protocols that make browsing the web possible. DNS acts as the
internet's phonebook, while HTTP/HTTPS acts as the language browsers and web servers use
to exchange web pages.

DNS (Domain Name System)
What it is: A decentralized naming system that translates human-readable domain names
(like example.com) into machine-readable IP addresses (like 93.184.216.34).
Port & Transport: Uses Port 53. Primarily uses UDP for fast standard lookups, and
switches to TCP for large data transfers (like DNS zone transfers) or when responses exceed

size limits.
How a DNS Lookup Works (Step-by-Step):
Browser/OS Cache: Your device first checks its local memory to see if it recently visited the
site.
Recursive Resolver: If not cached, the query goes to a resolver (usually run by your ISP or
a public provider like 8.8.8.8).
Root Server: Directs the resolver to the right Top-Level Domain (TLD) server (such as .com,
.org, or .in).
TLD Server: Points the resolver to the specific domain's Authoritative Name Server.
Authoritative Name Server: Holds the actual DNS records and returns the final IP address
to your browser.
Common DNS Record Types:
A / AAAA Record: Maps a domain name to an IPv4 (A) or IPv6 (AAAA) address.
CNAME Record: Alias record that points one domain name to another domain name.
MX Record: Directs emails to the domain's mail servers.
TXT Record: Stores text notes, often used for domain ownership verification and email
security (SPF, DKIM).
Security Threats & Defenses: Vulnerable to DNS Spoofing / Cache Poisoning
(redirecting users to fake sites) and DDoS attacks. Protected using DNSSEC (adds
cryptographic signatures) and DoH / DoT (encrypts DNS queries).

2. HTTP vs. HTTPS
What HTTP is: The foundational request-response protocol used to transfer web pages,
images, and videos between a client (web browser) and a web server.
What HTTPS is: The secure version of HTTP. It wraps standard HTTP traffic inside TLS
(Transport Layer Security) encryption (formerly SSL) to protect data in transit.
Key Differences:
Feature HTTP HTTPS
Default Port Port 80 Port 443
Security Sends data in plain text (readable

by anyone intercepting traffic). Encrypts all data using TLS/SSL.

CIA Triad
Impact

Offers zero Confidentiality or
Integrity.

Protects Confidentiality (encryption) and
Integrity (prevents tampering).

Authentication Does not verify the website's

identity.

Uses Digital Certificates (issued by
Certificate Authorities) to prove the site is
genuine.

Common HTTP Request Methods:
GET: Requests data from a server (e.g., loading a webpage).
POST: Sends data to a server to create or process something (e.g., submitting a login form).
PUT / DELETE: Updates existing resources or removes data on the server.
Common HTTP Status Codes:
200 OK: Request succeeded.
301 / 302: Page redirected to another URL.
403 Forbidden: Server understands the request, but access is denied.
404 Not Found: Requested page does not exist.
500 Internal Server Error: Something broke on the web server side.

Quick Revision Summary
How they work together: When you type a URL into a browser, DNS runs first to find the
server's IP address (Port 53), and then HTTPS connects to that IP address (Port 443) to

securely load the webpage.
Security rule of thumb: Never enter passwords or payment details on an HTTP site
because attackers on the same network can sniff the traffic in plain text.

IP Addressing, Subnetting, and NAT work together at the Network Layer (Layer 3) to identify
devices, organize networks efficiently, and connect private local networks to the public internet.
Here is a concise, informative set of study notes covering all three concepts.

IP Addressing
What it is: A unique logical label assigned to every device on a network so data packets
know where to go and where they came from.
IPv4 vs. IPv6:
IPv4: Uses 32 bits written as four decimal numbers separated by dots (e.g., 192.168.1.1).
Supports about 4.3 billion addresses, which has led to address exhaustion.
IPv6: Uses 128 bits written in hexadecimal separated by colons (e.g.,

2001:0db8:85a3::8a2e:0370:7334). Provides a virtually unlimited pool of addresses and built-
in security features.

Public vs. Private IP Addresses:
Public IPs: Globally unique addresses routable on the open internet (assigned by an ISP).
Private IPs: Free, non-routable addresses used strictly inside local networks
(homes/offices). Common ranges: 10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16.
Static vs. Dynamic: Static IPs are manually set and never change (ideal for servers).
Dynamic IPs are automatically leased for a set time via DHCP (ideal for user laptops and
phones).

Subnetting
What it is: The process of dividing one large IP network into smaller, logical sub-networks
(subnets).
How it works: An IP address has two parts: the Network ID (identifies the street) and the
Host ID (identifies the specific house). A Subnet Mask (like 255.255.255.0) or CIDR notation
(like /24) tells devices where the Network ID ends and the Host ID begins.
Reserved Addresses in Every Subnet:
Network Address: The very first IP (e.g., .0), which identifies the subnet itself.
Broadcast Address: The very last IP (e.g., .255), used to send data to all devices on that
subnet simultaneously.
Formula for usable host IPs: \(2^h - 2\) (where h is the number of host bits). For a /24
network (8 host bits), 28 - 2 = 254 usable device IPs.
Why Organizations Use It:
Reduces Network Congestion: Keeps broadcast traffic trapped inside small local groups
instead of flooding the whole company.
Improves Security: Allows administrators to isolate sensitive departments (like Finance or
HR) from guest Wi-Fi using firewall rules.
Saves IP Space: Allocates only the number of IPs each department actually needs.

NAT (Network Address Translation)
What it is: A router feature that translates private local IP addresses into a public IP
address (and vice versa) when traffic crosses between a local network and the public internet.
Why it exists: Because private IPs cannot travel across the public internet, and IPv4
doesn't have enough public addresses for every individual phone, laptop, and smart TV.
Common Types of NAT:
Static NAT: Maps one private IP to one dedicated public IP (1-to-1). Often used for internal
web servers that need external access.
Dynamic NAT: Maps private IPs to a pool of available public IPs on a first-come, first-served
basis.
PAT (Port Address Translation / NAT Overload): The most common form used in home
and office routers. It allows hundreds of private devices to share a single public IP by
tracking each device's traffic using unique source port numbers.
Security Benefit: Acts as a basic shield by hiding internal device IP addresses from outside
attackers, though it is not a replacement for a stateful firewall.

Quick Revision Summary
IP Address: Gives each device a unique identity.
Subnetting: Splits big networks into smaller, safer, faster neighborhoods.
NAT: Acts as the front-desk receptionist at the router, letting an entire private building share
one public street address on the internet.
