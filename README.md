# ssmtp

[![Build Status](https://drone.osshelp.ru/api/badges/ansible/ssmtp/status.svg)](https://drone.osshelp.ru/ansible/ssmtp)

Simple role for Ansible, which installs ssmtp

## Usage (example)

### Install and configure

```yaml
    - role: ssmtp
```

### Configure only

```yaml
    - role: ssmtp
      ssmtp_setup: configure
      ssmtp_from_line_override: true
```

### Old example

```yaml
 roles:
    - role: ssmtp
      ssmtp_rewrite_domain: example.com
      ssmtp_from_line_override: true
      ssmtp_use_tls: true
      ssmtp_use_start_tls: true
      ssmtp_tls_certs:
        - {key: TLSCert, value: '/path/to/certificate'}
        - {key: TLSKey, value: '/path/to/key'}
      ssmtp_credentials:
        - {key: AuthUser, value: 'user'}
        - {key: AuthPass, value: 'strong_password'}
```

## Available parameters

### Main

| Param | Default | Description |
| -------- | -------- | -------- |
| `ssmtp_setup` | `full` | Setup mode. See [OSSHelp KB article](https://oss.help/kb4895) |
| `ssmtp_packages` | `[ssmtp, mailutils]` | SSMTP packages |
| `ssmtp_hostname` | `{{ inventory_hostname }}` | SSMTP hostname |
| `ssmtp_mailhub` | `mail-relay` | Mail relay host |
| `ssmtp_rewrite_domain` | - | SSMTP rewrite domain |
| `ssmtp_from_line_override` | `false` | SSMTP From line override |

### Misc

| Param | Default | Description |
| -------- | -------- | -------- |
| `ssmtp_use_tls` | `false` | Use TLS|
| `ssmtp_use_start_tls` | `false` | Use StartTLS |
| `ssmtp_tls_certs` | `[]` | Certs |
| `ssmtp_credentials` | `[]` | Credentials |

## FAQ

...

## Useful links

- [Official documentation](https://www.systutorials.com/docs/linux/man/5-ssmtp.conf/)

## TODO

- ...

## License

GPL3

## Author

OSSHelp Team, see <https://oss.help>
