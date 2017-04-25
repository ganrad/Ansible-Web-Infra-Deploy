# Install and Deploy Web Infrastructure components using Red Hat Ansible

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

## Description
This project aims to provide Ansible based automation scripts for automating the deployment of a 2-tier web infrastructure topology.  Components within tier-1 constitute web / proxy servers that usually front-end backend application servers.  Tier-2 components represent application server instances.  For this project, the widely popular and battle tested Apache Web/Httpd server will be deployed in tier-1.  And for tier-2, the tried and true Apache Tomcat server will be used as the backend Java application server.  Rationale behind choosing these components - Apache Web Server powers approx. 65-70% of the web sites on the internet.  And Apache Tomcat has close to 70% penetration in the enterprise data center.

The steps outlined in the following section (below) explain how to use the Ansible scripts to deploy a farm of Apache Web and Tomcat servers across multiple remote nodes (machines). 

