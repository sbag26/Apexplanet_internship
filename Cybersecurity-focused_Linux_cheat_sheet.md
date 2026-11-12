Cybersecurity-focused Linux cheat sheet
A cybersecurity-focused Linux cheat sheet centers on reconnaissance, privilege escalation
auditing, network traffic analysis, and log forensics. Below are the essential commands grouped
by defensive and offensive security workflows.
User, Group & Privilege Auditing
id / whoami Display your current username, user ID (UID), and group memberships.
sudo -l List the exact commands your current user is permitted to run with root privileges.
cat /etc/passwd View all local user accounts, their home directories, and default login
shells.
cat /etc/shadow Inspect password hashes and expiration policies (requires root access).
find / -perm -4000 2>/dev/null Locate all SUID binaries on the system, a common
vector for local privilege escalation.
getcap -r / 2>/dev/null Search the filesystem for binaries granted special Linux
capabilities.
Network Recon & Socket Inspection
ss -tulnp Show all listening TCP and UDP ports alongside the exact process names and
PIDs bound to them.
lsof -i :<port> Identify which specific process is holding open a given network port.
ip neigh / arp -a View the local ARP cache to discover neighboring devices on the same
subnet.
ip route Display the kernel routing table and default gateway.
nmap -sC -sV -oA scan <target> Run a default script and version detection scan against
a target and save results in all formats.
nc -lvnp <port> Start a Netcat listener on a specific port to catch reverse shells or receive
file transfers.
Packet Capture & Traffic Analysis
tcpdump -i <eth0> -nn -w capture.pcap Capture raw packets on a specific interface
without DNS resolution and save to a .pcap file.
tcpdump -r capture.pcap 'tcp port 80' Read a saved packet capture file and filter
exclusively for HTTP traffic.
curl -v -k <https://target> Send a verbose web request while ignoring SSL/TLS
certificate warnings to inspect raw headers.
dig +short <domain> ANY Query DNS records for a target domain.
whois <domain> Retrieve domain registration details, name servers, and ownership
contacts.
Log Forensics & Threat Hunting
last -a View a history of recent user logins, session durations, and source IP addresses.
lastb Display failed login attempts (requires root access; reads from /var/log/btmp).
journalctl -u ssh --since "1 hour ago" Query systemd logs for SSH service activity
over the past hour.
grep -i "failed\|error\|unauthorized" /var/log/auth.log Filter authentication logs
for signs of brute-force attacks or unauthorized access.

find / -mtime -1 2>/dev/null Locate all files modified within the last 24 hours to spot
unauthorized changes or dropped payloads.
ls -la /tmp /var/tmp /dev/shm Inspect world-writable directories commonly abused by
attackers to stage scripts and binaries.
Process, Persistence & Integrity Checks
ps -ef --forest Display running processes in a hierarchical tree view to spot suspicious
parent-child relationships.
crontab -l List scheduled background tasks (cron jobs) for the current user.
ls -la /etc/cron* Check system-wide scheduled task directories for malicious
persistence mechanisms.
systemctl list-units --type=service --state=running List all currently active
background services.
sha256sum <file> Generate a cryptographic hash of a file to verify its integrity or check it
against threat intelligence databases.
Firewall & Hardening Controls
ufw status verbose Check the active rules and default policies of the Uncomplicated
Firewall (Debian/Ubuntu).
iptables -L -n -v List all active low-level Netfilter packet filtering rules with packet
counters.
chattr +i <file> Make a critical configuration file immutable so not even the root user can
modify or delete it without removing the attribute first.
ssh-keygen -t ed25519 Generate a modern, high-security Ed25519 SSH key pair for
passwordless authentication.
