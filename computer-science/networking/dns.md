- Domain name system
- hostname <-> IP
- distributed, hierarchical DB:
    - Root DNS server
    - top-level domain DNS server (TLD)
    - authoritative DNS server
- process to translate www.amazon.com -> IP address:
    1. client contacts Root DNS which returns IP of TLD server for domain .com
    2. client contacts TLD which return IP of authoritative DNS server
    3. client contacts authoritative DNS server for the IP
    
- Local DNS server
    - DNS server of ISP (company, university ..)
    - when a host connect to ISP, it provides host with an IP of one of its local DNS server
    
- DNS record type
    - A: host -> IP
    - NS: domain -> authoritative DNS hostname
    - CNAME
    - MX
    
- DNS use UDP port 53 to serve DNS query
    - fast
    - DNS request is usually small, fit UDP segment
    - reliability can be added in application layer by retry      
