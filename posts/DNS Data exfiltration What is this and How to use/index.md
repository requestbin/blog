*Summary: To test or exploit blind RCE, XXE,… the first thing which you think usually is outbound connection. Unfortunate, many importance servers are dropped the outbound connection. In such cases, you can use the DNS protocol to exfiltrate data. In this topic, I will talk about that technique. There are 2 parts:*

*1. What is DNS Data exfiltration and how does it work.*

*2. I will introduce my new product (the http://requestbin.net) which have a tool for Data exfiltration through DNS protocol.*

# 1. What is DNS Data exfiltration and how does it work?

## What is DNS Data exfiltration?

Actually, this is not new technical, according to the Akamai, this technique is about 20 years old. In a simple definition, DNS Data exfiltration is way to exchange data between 2 computers without any directly connection, the data is exchanged through DNS protocol on intermediate DNS servers.

![ảnh](https://user-images.githubusercontent.com/10446854/164511548-99fd63cd-ca88-4373-8843-7ea703da84f5.png)

## How does it work?

Back to basic, please follow a DNS resolution flow:
![ảnh](https://user-images.githubusercontent.com/10446854/164511883-42ef1f15-3eca-4324-b8cf-8d3e4c44927b.png)

If you have managed a domain, please notice at step 9 and 11, client’s DNS Server (for example 8.8.8.8) will connect to a name servers returned from step 8 and 10; These name servers is settable via the Registrar’s DNS manager (for example: Go Daddy, Name Cheap,…). By setting the name servers (use NS records) be your own server, you can inspect to the request from client’s DNS Server.

![ảnh](https://user-images.githubusercontent.com/10446854/164511916-cb7857ff-96dd-4789-9cc8-2c4c2958ed06.png)

Follow above settings, if ns1.requestbin.net is yours, you can view all subdomain which client requested. Attacker will put data into subdomain and receive it at the name server side. So, that is way to send data from victim (client) to attacker (the name server).

![ảnh](https://user-images.githubusercontent.com/10446854/164511956-7296c3eb-da16-4fa8-ac1d-14fc74a7738e.png)

In above example, the attacker wants to leak the password from compromised machine. The domain exfiltration.com is attacker’s and already set NS record to a server he owns. The malware in this case will make a dns resolution a domain which includes text content of the password is subdomain of the exfiltration.com. After that, attacker will view log at name server to get the password.

## How to send data from outside to inside?

Similar to above technique, the client still make a dns resolution to exfiltration.com. However, instead of responding an A record, attacker’s name server will response a CNAME or TXT record which allow large unstructured strings to be sent from attacker to victim.

![ảnh](https://user-images.githubusercontent.com/10446854/164512022-a72d1606-7b59-40c4-821b-4675ecf1cb4b.png)

## So, about DNS Tunnel?

Of course, when you can send and receive data on DNS protocol, you can make a tunnel on that. With that technique, you will ssh, remote desktop or connect to any services of internal server. I will talk more about this technique in another topic.

In case you are interested in this, please read some bellow artices:

![DNS Data Exfiltration — How it works](https://community.infoblox.com/t5/Community-Blog/DNS-Data-Exfiltration-How-it-works/ba-p/3664)

![Data Exfiltration (Tunneling) Attacks against Corporate Network](https://pentest.blog/data-exfiltration-tunneling-attacks-against-corporate-network/)

# 2. How to use DNS Data exfiltration?

Follow the first part, to use the DNS Data exfiltration, you must at least have a domain and a name server which is setup to dns package inspection. It’s not complicate but not easy for anyone.

So, I have built a website (http://requestbin.net/dns) which supports to check some cases like blind RCE, XXE,.. and supports to send/receive data between outside and inside. And in particular, it’s very easy to use.

![ảnh](https://user-images.githubusercontent.com/10446854/164512412-c1e1d77e-e7d4-4882-9260-5af540e48d4c.png)

When visit the website, you maybe feel familiar about the interface. My website is based on requestb.in (https://github.com/Runscope/requestbin) which was down someday before and the code of DNS Data exfiltration is based on DNSBin (https://github.com/HoLyVieR/dnsbin)

In case you’re interested in this code, please visit the repository:

https://github.com/mxcxvn/requestbin.net

Any feedback is welcomed, please contact me at mxcxvn[at]gmail[dot]com
