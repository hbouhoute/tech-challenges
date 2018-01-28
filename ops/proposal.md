# Proposal

Write here you proposal of the [asked architecture](README.md).

1) Secure the servers
- Change the root password
- To avoid the bruteforce attack --> change the connection port (22) to another on ssgd_config file
- Make an alert root logging notification each time when a root session is used
- stop unuseful services
- Use IPTables/Netfilter if you don't have a firewall
- Adjust "MaxClients" variable to use fairly RAM and avoid memory failure
