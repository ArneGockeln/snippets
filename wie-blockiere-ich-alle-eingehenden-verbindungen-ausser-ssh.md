---
title: "Wie blockiere ich alle eingehenden Verbindungen ausser SSH?"
---

Auf meinen Linux Machinen nutze ich iptables als Firewall. Mit den folgenden Regeln aktzeptiert der Server keine eingehenden Verbindungen, außer SSH und solche die von Innen heraus erstellt wurden.

```
# iptables: drop all incoming connections except SSH
# ensure the loopback is not affected
$ iptables -A INPUT -i lo -j ACCEPT

# allow all incoming traffic for established connections
$ iptables -A INPUT -m state --state RELATED,ESTABLISHED -j ACCEPT

# allow tcp ssh connections on port 22
$ iptables -A INPUT -p tcp -m tcp --dport 22 -j ACCEPT

# drop all other incoming connections
$ iptables -A INPUT -j DROP

# set INPUT chain to drop policy
$ iptables -P INPUT DROP
```
