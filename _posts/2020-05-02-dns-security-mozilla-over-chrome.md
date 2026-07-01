---
title: "DNS Security: Mozilla over Chrome?"
date: 2020-05-02
categories: 
  - "home"
  - "tech"
tags: 
  - "chrome"
  - "dns"
  - "dnssec"
  - "doh"
  - "dot"
  - "dtls"
  - "firefox"
  - "mitm"
  - "mozilla"
  - "qubes"
  - "rfc"
  - "tails"
  - "tcp"
  - "trusted-recursive-resolver"
  - "udp"
coverImage: "/images/dns.png"
---

There are a number of ways to safely browse the internet. One could use a proxy server, _**TOR**_ proxy, _**VPN**_, or use an operating system that uses those principles. _**TAILS**_ and _**Qubes**_ are the popular ones that comes to my mind. All these solutions are available and things are sorted if you are a techie. For an average user, security has to bundled by default. Until 2005, the internet engineering task force (_IETF_) was not at all interested in securing the very basic such as _DNS_ lookup.

A _DNS_ lookup (domain name to IP address mapping) is a plain text query over a _UDP_ or _TCP_ connection on **port 53**. _DNS_ cache poisoning is one of many attacks possible in this scenario. In 2005, request for comments 4033 [_**RFC4033**_](https://tools.ietf.org/html/rfc4033) was put forward for consideration. The _Domain Name System Security Extensions_ (_**DNSSEC)**_ was introduced. The intention was to authenticate the origin of data and maintain its integrity. It would mean to create a chain of authentication and each _**DNSSEC**_ resolver has to sign its resource records with its public key and records have to be validated upto root resolver. This could fall into a bogus (invalid trust chain), indeterminate (some portion is valid), insecure (trust chain breaks at a non-existent **DS** record), and secure (a valid full trust chain) category. The major drawback is that all ISPs/registrars have to agree to support it. Plus, there’s always a threat of denial of service attacks. An attacker can use _**DNSSEC**_ mechanism itself to send updated messages and force security-aware name server to re-sign the resource record sets (RRsets). The request and response queries are not secure at all. Some proposals exist such as _**[DNSCurve](https://tools.ietf.org/html/rfc7858#ref-DNSCurve)**_, _**[DNSCRYPT](https://tools.ietf.org/html/rfc7858#ref-DNSCRYPT-WEBSITE)**_, [_**Confidential DNS**_](https://tools.ietf.org/html/rfc7858#ref-CONFIDENTIAL-DNS), and [_**IPSECA**_](https://tools.ietf.org/html/rfc7858#ref-IPSECA). These measures if utilized along with _**DNSSEC**_ could provide some level of security. Additionally, a proposal came for using _DNS over Datagram Transport Layer Security_ (_**DTLS**_) [_**DNSoD**_](https://tools.ietf.org/html/rfc7858#ref-DNSoD). There have been several updates to that **RFC** itself since then but none of them provide a comprehensive secure solution.

A compiled version of security concerns is available for reference, [_**RFC7626**_](https://tools.ietf.org/html/rfc7626). It summarizes what all needs to be taken care of. Following that, in 2016, _**DNS over Transport Layer**_ security (**DoT**) was proposed [RFC7858](https://tools.ietf.org/html/rfc7858). In this, requests and responses are encrypted with a **TLS** handshake between a stub (client) and recursive-name resolver (server) over port 853 by default. The initial connection is over **TCP** and after successful connection **TLS** handshake is required. The session could be over any other port provided client and server are configured as such. However, there’s a catch, a stub (client) doesn’t necessarily need to authenticate the server. This opens the door to _man-in-the-middle_ (_**MitM**_) attacks.

In 2018, **DNS** over **HTTPS** (_**DoH**_) was put forward for comments in [_**RFC8484**_](https://tools.ietf.org/html/rfc8484). This introduces the same principles of _**DNS-over-TLS**_ but also mandates that the server needs to be authenticated. The connection is established over **HTTPS** on a regular **HTTPS** port 443. By far, _**DoH**_ is the most secure way to browse the internet. The proposal was partly put forward by _**Mozilla**_ and the very reason it’s my favorite internet browser. _**Mozilla**_ has provided its own wiki [_**Trusted Recursive Resolver**_](https://wiki.mozilla.org/Trusted_Recursive_Resolver) to guide users how to setup _**DoH**_.
