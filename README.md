ldap-authentication
=========

A brief description of the role goes here.

Requirements
------------

 Setup SSSD  to allow for ldap authentication

Role Variables
--------------

  - domain: DNS FQDN of the domain to configure in sssd
  - ldap_host_name: FQDN of the ldap server
  - domain_dn: Base domain dn in the directory to search for users.
  - do_ssl: enable SSL connection to the LDAP directory
  - do_sssd: single|multiple - enable a single or multiple domains for authentication. If there is already
      a domain configured on the target host, use multiple. This defaults to single. 
  - do_bind: Boolean. Enable SSSD to bind to the directory as a user instead of anonymous binds.
      - sssd_bind_user: DN of the user to bind as
      - sssd_bind_pass: Password of the user
  - run_handlers: Set to False if you do not want to restart SSSD after configuration.
  
Dependencies
------------

 There needs to be a working LDAP directory for this role to function correctly. There are no other external dependencies.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      vars:
        do_bind: no
        domain: example.net
        domain_dn: dc=example,dc=net
      roles:
         - { role: ldap-authentication,  }

License
-------

GPLv3

Author Information
------------------

Iain M Conochie <iain@tharoid.co.uk>
