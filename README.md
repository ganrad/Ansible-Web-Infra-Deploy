# Use Ansible to Install and Deploy a 2-tier Web Application Infrastructure

Ansible is a simple agentless automation technology that has caught the world of software configuration management by storm!  Ansible allows IT operators to automate repetitive infrastructure tasks such as installation, configuration and deployment of software using a simple yet powerful automation language *YAML*.  Ansible is an open source project and is the core automation engine powering Red Hat Ansible Tower.  Ansible provides close to 800+ (at the time of this writing) pre-built modules that can be used to automate complex infrastructure tasks ranging from web/application deployment to configuration management to workflow orchestration.

**Important Note:** This project assumes readers are familiar with writing simple Ansible automation scripts using the YAML language and/or have prior experience working with IT infrastructure automation tools such as Chef and Puppet.

For easy and quick reference, readers can refer to the following on-line resources as needed.

1.  [Open Source Ansible](https://www.ansible.com/)
2.  [Red Hat Ansible / Tower](https://www.redhat.com/en/technologies/management/ansible)
3.  [Ansible Documentation](https://docs.ansible.com/)
4.  [Red Hat JBoss Web Server](https://access.redhat.com/documentation/en/red-hat-jboss-web-server/)
5.  [Red Hat JBoss Core Services](https://access.redhat.com/documentation/en/red-hat-jboss-core-services/)
6.  [Apache Httpd](https://httpd.apache.org/)
7.  [Apache Tomcat 8](https://tomcat.apache.org/tomcat-8.0-doc/index.html)
8.  [YAML](http://yaml.org/)
9.  [mod_cluster Load Balancer](http://mod-cluster.jboss.org/)

## Description
This project provides Ansible based automation scripts for implementing a multi-server (node) 2-tier enterprise/web application architecture/topology.  Typically, in a 2-tier web application architecture, components within tier-1 constitute web / proxy servers.  These servers act as a reverse proxy and include a load balancer component which intelligently distributes the incoming http requests to backend application server instances running on multiple machines.  Tier-2 components in this topology represent application server instances.  Ansible is used to automate the installation, configuration and deployment of infrastructure components in both tiers.

For this project, the widely popular and battle tested Apache Web/Httpd server will be deployed in tier-1.  And for tier-2, the tried and true Apache Tomcat server will be used as the backend Java application server.  Rationale behind choosing these components -

a.  Apache Web (Httpd) Server currently powers approximately 70% of the web sites on the internet.  
b.  Apache Tomcat has close to 70% penetration in the enterprise data center.

Red Hat Inc., provides tested, certified and supported versions of the two most trusted web application runtime/server components listed above.  *Red Hat JBoss Web Server* (JWS) is a software bundle that comprises of the following components -

a.  Apache Web/Httpd Server (v2.4.x)
b.  Apache Tomcat application servers (v7.x & v8.x)
c.  Apache Portable Runtime (APR) native library
d.  Load balancer plugins - mod_jk and mod_cluster.  ('mod_cluster' requires minimal configuration and is an intelligent load balancer.  Refer to the mod_cluster project website for more details). 

JWS v3.1 was used to implement and test the 2-tier web application deployment topology described above.

The steps outlined in the following sections (below) explain in detail how to configure the provided Ansible playbooks in order to deploy a farm of Apache Web and Apache Tomcat servers across multiple remote nodes (machines). 

