Failover for OpenVPN L3 channel from client with 2 uplinks. VPN channels with similar routes, but different metrics are established over both uplinks. If one if VPN connection fails, it's routes are deleted, and other connection routes begin to work.

You can not get this behaviour with config 'route' option, because it establishes routes even if connection is not realy alive. This is why you need scripts.

I tried to make scripts convenient: routes are written to separate file, so you may have one script, and many tunnel configs with routes file for each pair. Example:

```
# First failover connection

tun1_1.conf
tun1_2.conf
tun1.routes

# Second failover connection

tun2_1.conf
tun2_2.conf
tun2.routes

# Script

ovpn-routes
```

**P.S.** If this code is useful for you - don't forget to put a star on it's [github repo](https://github.com/selivan/opvn-2uplinks-failover).
