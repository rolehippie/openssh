# openssh

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/openssh) [![General Workflow](https://github.com/rolehippie/openssh/actions/workflows/general.yml/badge.svg)](https://github.com/rolehippie/openssh/actions/workflows/general.yml) [![Readme Workflow](https://github.com/rolehippie/openssh/actions/workflows/readme.yml/badge.svg)](https://github.com/rolehippie/openssh/actions/workflows/readme.yml) [![Galaxy Workflow](https://github.com/rolehippie/openssh/actions/workflows/galaxy.yml/badge.svg)](https://github.com/rolehippie/openssh/actions/workflows/galaxy.yml) [![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/openssh)](https://github.com/rolehippie/openssh/blob/master/LICENSE) [![Ansible Role](https://img.shields.io/ansible/role/51437)](https://galaxy.ansible.com/rolehippie/openssh)

Ansible role to configure a hardened openSSH daemon.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of content

- [Default Variables](#default-variables)
  - [openssh_accept_env_vars](#openssh_accept_env_vars)
  - [openssh_address_family](#openssh_address_family)
  - [openssh_allow_agent_forwarding](#openssh_allow_agent_forwarding)
  - [openssh_allow_groups](#openssh_allow_groups)
  - [openssh_allow_tcp_forwarding](#openssh_allow_tcp_forwarding)
  - [openssh_allow_users](#openssh_allow_users)
  - [openssh_authorized_keys_file](#openssh_authorized_keys_file)
  - [openssh_authorized_principals](#openssh_authorized_principals)
  - [openssh_authorized_principals_file](#openssh_authorized_principals_file)
  - [openssh_banner](#openssh_banner)
  - [openssh_challenge_response_authentication](#openssh_challenge_response_authentication)
  - [openssh_client_alive_count_max](#openssh_client_alive_count_max)
  - [openssh_client_alive_interval](#openssh_client_alive_interval)
  - [openssh_client_allow_agent_forwarding](#openssh_client_allow_agent_forwarding)
  - [openssh_client_gssapi_authentication](#openssh_client_gssapi_authentication)
  - [openssh_client_gssapi_delegate_credentials](#openssh_client_gssapi_delegate_credentials)
  - [openssh_client_hostbased_authentication](#openssh_client_hostbased_authentication)
  - [openssh_client_password_authentication](#openssh_client_password_authentication)
  - [openssh_client_port](#openssh_client_port)
  - [openssh_client_x11_forwarding](#openssh_client_x11_forwarding)
  - [openssh_compression](#openssh_compression)
  - [openssh_deny_groups](#openssh_deny_groups)
  - [openssh_deny_users](#openssh_deny_users)
  - [openssh_extra_dirs](#openssh_extra_dirs)
  - [openssh_gateway_ports](#openssh_gateway_ports)
  - [openssh_general_dirs](#openssh_general_dirs)
  - [openssh_gssapi_authentication](#openssh_gssapi_authentication)
  - [openssh_gssapi_cleanup_credentials](#openssh_gssapi_cleanup_credentials)
  - [openssh_gssapi_key_exchange](#openssh_gssapi_key_exchange)
  - [openssh_gssapi_strict_accept_or_check](#openssh_gssapi_strict_accept_or_check)
  - [openssh_host_keys](#openssh_host_keys)
  - [openssh_hostbased_authentication](#openssh_hostbased_authentication)
  - [openssh_ignore_rhosts](#openssh_ignore_rhosts)
  - [openssh_ignore_user_known_hosts](#openssh_ignore_user_known_hosts)
  - [openssh_kerberos_authentication](#openssh_kerberos_authentication)
  - [openssh_kerberos_get_afs_token](#openssh_kerberos_get_afs_token)
  - [openssh_kerberos_or_local_passwd](#openssh_kerberos_or_local_passwd)
  - [openssh_kerberos_ticket_cleanup](#openssh_kerberos_ticket_cleanup)
  - [openssh_listen_addresses](#openssh_listen_addresses)
  - [openssh_log_level](#openssh_log_level)
  - [openssh_login_grace_time](#openssh_login_grace_time)
  - [openssh_match_address](#openssh_match_address)
  - [openssh_match_group](#openssh_match_group)
  - [openssh_match_user](#openssh_match_user)
  - [openssh_max_auth_tries](#openssh_max_auth_tries)
  - [openssh_max_sessions](#openssh_max_sessions)
  - [openssh_max_startups](#openssh_max_startups)
  - [openssh_moduli_minimum](#openssh_moduli_minimum)
  - [openssh_password_authentication](#openssh_password_authentication)
  - [openssh_permit_empty_passwords](#openssh_permit_empty_passwords)
  - [openssh_permit_root_login](#openssh_permit_root_login)
  - [openssh_permit_tunnel](#openssh_permit_tunnel)
  - [openssh_permit_user_environment](#openssh_permit_user_environment)
  - [openssh_port](#openssh_port)
  - [openssh_print_last_log](#openssh_print_last_log)
  - [openssh_print_motd](#openssh_print_motd)
  - [openssh_pubkey_authentication](#openssh_pubkey_authentication)
  - [openssh_remote_hosts](#openssh_remote_hosts)
  - [openssh_revoked_keys](#openssh_revoked_keys)
  - [openssh_revoked_keys_file](#openssh_revoked_keys_file)
  - [openssh_sftp_chroot_directory](#openssh_sftp_chroot_directory)
  - [openssh_sftp_enabled](#openssh_sftp_enabled)
  - [openssh_sftp_group](#openssh_sftp_group)
  - [openssh_sftp_password_authentication](#openssh_sftp_password_authentication)
  - [openssh_strict_modes](#openssh_strict_modes)
  - [openssh_syslog_facility](#openssh_syslog_facility)
  - [openssh_tcp_keep_alive](#openssh_tcp_keep_alive)
  - [openssh_trusted_user_ca_keys](#openssh_trusted_user_ca_keys)
  - [openssh_trusted_user_ca_keys_file](#openssh_trusted_user_ca_keys_file)
  - [openssh_use_dns](#openssh_use_dns)
  - [openssh_use_pam](#openssh_use_pam)
  - [openssh_valid_ciphers](#openssh_valid_ciphers)
  - [openssh_valid_kex](#openssh_valid_kex)
  - [openssh_valid_macs](#openssh_valid_macs)
  - [openssh_x11_forwarding](#openssh_x11_forwarding)
  - [openssh_x11_use_localhost](#openssh_x11_use_localhost)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Default Variables

### openssh_accept_env_vars

List of accepted environment variables

#### Default value

```YAML
openssh_accept_env_vars:
  - LANG
  - LC_*
```

### openssh_address_family

Address family to bind to

#### Default value

```YAML
openssh_address_family: any
```

### openssh_allow_agent_forwarding

Allow agent forwarding

#### Default value

```YAML
openssh_allow_agent_forwarding: true
```

### openssh_allow_groups

List of groups to allow SSH login

#### Default value

```YAML
openssh_allow_groups: []
```

### openssh_allow_tcp_forwarding

Allow TCP forwarding

#### Default value

```YAML
openssh_allow_tcp_forwarding: true
```

### openssh_allow_users

List of users to allow SSH login

#### Default value

```YAML
openssh_allow_users: []
```

### openssh_authorized_keys_file

Authorized keys file

#### Default value

```YAML
openssh_authorized_keys_file:
  - .ssh/authorized_keys
```

### openssh_authorized_principals

List of authorized principles

#### Default value

```YAML
openssh_authorized_principals: []
```

#### Example usage

```YAML
openssh_authorized_principals:
  - path: /etc/ssh/auth_principals/root
    principals:
      - root
    owner: root
    group: root
    dirowner: root
    dirgroup: root
  - path: /etc/ssh/auth_principals/example
    principals:
      - webserver
      - master
  - path: /etc/ssh/auth_principals/foobar
    state: absent
```

### openssh_authorized_principals_file

Path to trusted user ca keys file

#### Default value

```YAML
openssh_authorized_principals_file: none
```

#### Example usage

```YAML
openssh_authorized_principals_file: /etc/ssh/auth_principals/%u
```

### openssh_banner

Enable or disable a banner

#### Default value

```YAML
openssh_banner: none
```

### openssh_challenge_response_authentication

Challenge response authentication

#### Default value

```YAML
openssh_challenge_response_authentication: false
```

### openssh_client_alive_count_max

Max client alive count

#### Default value

```YAML
openssh_client_alive_count_max: 3
```

### openssh_client_alive_interval

Client alive interval

#### Default value

```YAML
openssh_client_alive_interval: 300
```

### openssh_client_allow_agent_forwarding

Allow agent forwarding for client connections

#### Default value

```YAML
openssh_client_allow_agent_forwarding: '{{ openssh_allow_agent_forwarding }}'
```

### openssh_client_gssapi_authentication

GSSAPI authentication for client connections

#### Default value

```YAML
openssh_client_gssapi_authentication: '{{ openssh_gssapi_authentication }}'
```

### openssh_client_gssapi_delegate_credentials

Delegate GSSAPI credentials for client connections

#### Default value

```YAML
openssh_client_gssapi_delegate_credentials: false
```

### openssh_client_hostbased_authentication

Hostbased authentication for client connections

#### Default value

```YAML
openssh_client_hostbased_authentication: '{{ openssh_hostbased_authentication }}'
```

### openssh_client_password_authentication

Password authentication for client connections

#### Default value

```YAML
openssh_client_password_authentication: '{{ openssh_password_authentication }}'
```

### openssh_client_port

Port to which ssh client should connect

#### Default value

```YAML
openssh_client_port: 22
```

### openssh_client_x11_forwarding

Allow x11 forwarding for client connections

#### Default value

```YAML
openssh_client_x11_forwarding: '{{ openssh_x11_forwarding }}'
```

### openssh_compression

Enable compression

#### Default value

```YAML
openssh_compression: false
```

### openssh_deny_groups

List of groups to deny SSH login

#### Default value

```YAML
openssh_deny_groups: []
```

### openssh_deny_users

List of users to deny SSH login

#### Default value

```YAML
openssh_deny_users: []
```

### openssh_extra_dirs

List of extra directories to create

#### Default value

```YAML
openssh_extra_dirs: []
```

#### Example usage

```YAML
openssh_extra_dirs:
  - path: /path/to/dir
    owner: root
    group: root
    mode: u=rwx,g=,o=
    state: present
```

### openssh_gateway_ports

Allow gateway ports

#### Default value

```YAML
openssh_gateway_ports: false
```

### openssh_general_dirs

List of general directories to create

#### Default value

```YAML
openssh_general_dirs: '{{ openssh_default_dirs }}'
```

#### Example usage

```YAML
openssh_general_dirs:
  - path: /path/to/dir
    owner: root
    group: root
    mode: u=rwx,g=,o=
    state: present
```

### openssh_gssapi_authentication

Enable GSSAP authentication

#### Default value

```YAML
openssh_gssapi_authentication: false
```

### openssh_gssapi_cleanup_credentials

GSSAPI cleanup credentials

#### Default value

```YAML
openssh_gssapi_cleanup_credentials: true
```

### openssh_gssapi_key_exchange

GSSAP key exchange

#### Default value

```YAML
openssh_gssapi_key_exchange: false
```

### openssh_gssapi_strict_accept_or_check

GSSAPI strict accept or check

#### Default value

```YAML
openssh_gssapi_strict_accept_or_check: true
```

### openssh_host_keys

List of ports to listen to

#### Default value

```YAML
openssh_host_keys:
  - name: ssh_host_ed25519_key
  - name: ssh_host_rsa_key
```

#### Example usage

```YAML
openssh_host_keys:
  - name: ssh_host_dsa_key
    key: "{{ vaulted_ssh_host_dsa_key }}"
    pub: "{{ vaulted_ssh_host_dsa_key_pub }}"
```

### openssh_hostbased_authentication

Hostbased authentication

#### Default value

```YAML
openssh_hostbased_authentication: false
```

### openssh_ignore_rhosts

Ignore rhosts

#### Default value

```YAML
openssh_ignore_rhosts: true
```

### openssh_ignore_user_known_hosts

Ignore user known hosts

#### Default value

```YAML
openssh_ignore_user_known_hosts: true
```

### openssh_kerberos_authentication

Enable kerberos authentication

#### Default value

```YAML
openssh_kerberos_authentication: false
```

### openssh_kerberos_get_afs_token

Kerberos get afs token

#### Default value

```YAML
openssh_kerberos_get_afs_token: false
```

### openssh_kerberos_or_local_passwd

Kerberos or local passwwd

#### Default value

```YAML
openssh_kerberos_or_local_passwd: false
```

### openssh_kerberos_ticket_cleanup

Kerberos ticket cleanup

#### Default value

```YAML
openssh_kerberos_ticket_cleanup: true
```

### openssh_listen_addresses

List of addresses to bind to

#### Default value

```YAML
openssh_listen_addresses:
  - 0.0.0.0
  - '::'
```

### openssh_log_level

Logging level

#### Default value

```YAML
openssh_log_level: INFO
```

### openssh_login_grace_time

Login grace time

#### Default value

```YAML
openssh_login_grace_time: 30s
```

### openssh_match_address



#### Default value

```YAML
openssh_match_address: []
```

#### Example usage

```YAML
openssh_match_address:
  - address: 192.168.1.1
    rules:
      - PermitRootLogin yes
```

### openssh_match_group



#### Default value

```YAML
openssh_match_group: []
```

#### Example usage

```YAML
openssh_match_group:
  - group: wheel
    rules:
      - PasswordAuthentication yes
```

### openssh_match_user



#### Default value

```YAML
openssh_match_user: []
```

#### Example usage

```YAML
openssh_match_user:
  - user: john
    rules:
      - PasswordAuthentication yes
```

### openssh_max_auth_tries

Max allowed authentication tries

#### Default value

```YAML
openssh_max_auth_tries: 3
```

### openssh_max_sessions

Max allowed sessions

#### Default value

```YAML
openssh_max_sessions: 10
```

### openssh_max_startups

Define max startups restriction

#### Default value

```YAML
openssh_max_startups: 60:30:120
```

### openssh_moduli_minimum

Minimum size of allowd primes

#### Default value

```YAML
openssh_moduli_minimum: 2048
```

### openssh_password_authentication

Enable password authentication

#### Default value

```YAML
openssh_password_authentication: false
```

### openssh_permit_empty_passwords

Permit empty passwords

#### Default value

```YAML
openssh_permit_empty_passwords: false
```

### openssh_permit_root_login

Permit root login

#### Default value

```YAML
openssh_permit_root_login: false
```

### openssh_permit_tunnel

Permit tunnels

#### Default value

```YAML
openssh_permit_tunnel: false
```

### openssh_permit_user_environment

Permit user environment

#### Default value

```YAML
openssh_permit_user_environment: false
```

### openssh_port

Port to bind the daemon to

#### Default value

```YAML
openssh_port: 22
```

### openssh_print_last_log

Print last login

#### Default value

```YAML
openssh_print_last_log: true
```

### openssh_print_motd

Print a message of the day

#### Default value

```YAML
openssh_print_motd: false
```

### openssh_pubkey_authentication

Enable pubkey authentication

#### Default value

```YAML
openssh_pubkey_authentication: true
```

### openssh_remote_hosts

List of client remote hosts

#### Default value

```YAML
openssh_remote_hosts: []
```

#### Example usage

```YAML
openssh_remote_hosts:
  - names:
      - host1
      - host1.example.com
    options:
      - StrictHostKeyChecking no
```

### openssh_revoked_keys

List of revoked keys

#### Default value

```YAML
openssh_revoked_keys: []
```

### openssh_revoked_keys_file

Path to revoked keys file

#### Default value

```YAML
openssh_revoked_keys_file: /etc/ssh/revoked_keys
```

### openssh_sftp_chroot_directory

Chroot directory for SFTP access

#### Default value

```YAML
openssh_sftp_chroot_directory: /home/%u
```

### openssh_sftp_enabled

Enable SFTP functionality matched by group

#### Default value

```YAML
openssh_sftp_enabled: false
```

### openssh_sftp_group

Group used to match SFTP access

#### Default value

```YAML
openssh_sftp_group: sftponly
```

### openssh_sftp_password_authentication

Allow password authentication for SFTP access

#### Default value

```YAML
openssh_sftp_password_authentication: false
```

### openssh_strict_modes

Enable strict mode

#### Default value

```YAML
openssh_strict_modes: true
```

### openssh_syslog_facility

Syslog facility

#### Default value

```YAML
openssh_syslog_facility: AUTHPRIV
```

### openssh_tcp_keep_alive

Keep TCP alive

#### Default value

```YAML
openssh_tcp_keep_alive: false
```

### openssh_trusted_user_ca_keys

List of trusted user ca keys

#### Default value

```YAML
openssh_trusted_user_ca_keys: []
```

### openssh_trusted_user_ca_keys_file

Path to trusted user ca keys file

#### Default value

```YAML
openssh_trusted_user_ca_keys_file:
```

#### Example usage

```YAML
openssh_trusted_user_ca_keys_file: /etc/ssh/trusted_user_ca_keys
```

### openssh_use_dns

Use DNS

#### Default value

```YAML
openssh_use_dns: true
```

### openssh_use_pam

Use PAM

#### Default value

```YAML
openssh_use_pam: true
```

### openssh_valid_ciphers

List of ciphers accepted by the server

#### Default value

```YAML
openssh_valid_ciphers:
  - chacha20-poly1305@openssh.com
  - aes256-gcm@openssh.com
  - aes128-gcm@openssh.com
  - aes256-ctr
  - aes192-ctr
  - aes128-ctr
```

### openssh_valid_kex

Map of kexs accepted by the server

#### Default value

```YAML
openssh_valid_kex:
  - curve25519-sha256@libssh.org
  - diffie-hellman-group-exchange-sha256
```

### openssh_valid_macs

List of macs accepted by the server

#### Default value

```YAML
openssh_valid_macs:
  - hmac-sha2-512-etm@openssh.com
  - hmac-sha2-256-etm@openssh.com
  - umac-128-etm@openssh.com
```

### openssh_x11_forwarding

Allow X11 forwarding

#### Default value

```YAML
openssh_x11_forwarding: false
```

### openssh_x11_use_localhost

Use localhost for X11

#### Default value

```YAML
openssh_x11_use_localhost: true
```

## Discovered Tags

**_always_**

**_openssh_**


## Dependencies

- None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
