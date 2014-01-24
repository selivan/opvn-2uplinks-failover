# DESCRIPTION

Failover for OpenVPN L3 channel from client with 2 uplinks. VPN channels with similar routes, but different metrics are established over both uplinks. If one if VPN connection fails, it's routes are deleted, and other connection routes begin to work.

You can not get this behaviour with config 'route' option, because it establishes routes even if connection is not realy alive. this is why you need scripts.
