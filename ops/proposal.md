# Proposal

Write here you proposal of the [asked architecture](README.md).

1) Protect your networkI
- Put a firewall between internal switches and the router connected to the outside (see https://www.supinfo.com/articles/resources/205098/2519/1.png and read http://www.lemagit.fr/conseil/Construire-une-architecture-de-securite-de-linformation-pas-a-pas)
- Install one or more servers only for http services (to low crashes and maintenance downtime)
- Install one or more servers for back-end application (to low crashes and maintenance downtime)
- Install one replicated DB server (see http://www.responsive-mind.fr/replication-mysql-master-master/)

2) Secure the servers
- Change the root password
- To avoid the bruteforce attack --> change the connection port (22) to another on sshd_config file
- Make an alert root logging notification each time when a root session is used
- stop unuseful services
- Use IPTables/Netfilter if you don't have a firewall
- Adjust "MaxClients" variable to use fairly RAM and avoid memory failure

3) Choose your Web service 
- NGINX is one of the most used
- read https://www.firelay.com/fr/using-nginx-load-balancing-zero-downtime-liferay-portals/

4) Backup solutions
- MysSQL --> https://blog.seboss666.info/2017/10/quelques-methodes-avancees-pour-faire-un-backup-mysqlmariadb/
- Backup linux servers using veeam --> https://www.veeam.com/blog/fr/announcing-linux-server-backup.html

5) Disaster recovery Plans
- Duplicate your site geographically, make them replicated between them (https://mapr.com/resources/disaster-recovery/assets/otherpageimages/TechBrief-DisasterRecovery-Fig4.png)
- Industrialize the build of the servers using tools like Chef, Ansible, Redhat satellite, to rebuild your site from scratch fastly with backup of the datas
- Use Cloud solutions (AWS, GC, Azure, OpenStack, Alibaba Cloud,...) it makes more reliable

6) Monitor the services
- Use a monitoring system like Check_MK, Nagios,
- Create dashboards to have necessary informations

Damien, I preferred to put links on similar solution that I imagined than to take time on Visio or LucidChart :-)

