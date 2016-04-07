Role Name: sardpost.java8
=========================

Ansible role for installing Oracle Java JDK 8 (jdk-8u77) on EL 7 platform (RHEL/Centos 7).
It checks if Openjdk is installed and removes it (when "openjdk:" variable in defaults/main.yml
is set to 1 (default)). The jre_url in defaults/main.yml specifies the download url.

        jre_url: http://download.oracle.com/otn-pub/java/jdk/8u77-b03/jdk-8u77-linux-x64.rpm

The commented get_url task ("Downloading Java 8 sdk") in the EL.yml works only under Ansible 2.
Ansible 2 supports the 'header' option in get_url module which is necessary to pass the cookie to
download the Oracle Java JDK official RPM.

Requirements
------------
Platform: RHEL/Centos 7


Dependencies
------------
No dependencies

Example Playbook
----------------
```yml
      - name: Install Java 8
        hosts: test_lab
        remote_user: centos
        sudo: yes

        roles:
        - sardpost.java8
```
Version:
--------
0.1

License
-------
GPLv3

Author Information
------------------
Davide M. Puggioni
