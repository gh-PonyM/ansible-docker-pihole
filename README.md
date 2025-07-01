# Role ansible_docker_pihole

Generated ansible role docker using docker compose for ansible_docker_pihole

## Installation

Install the role using `ansible-galaxy` using a `requirements.yml` file:

```yaml

roles:
- src: https://github.com/gh-PonyM/ansible_docker_pihole.git
  version: main
  name: ansible_docker_pihole
  scm: git
```

## docker-compose.yml template

The original [docker-compose.yml](docker-compose.yml) was transformed into an [ansible template](templates/docker-compose.yml)

## Defaults

Extracted from the original `docker-compose.yml` including environment configurations, the generated defaults are:

| Variable | default  | ENV | used by | is secret |
| -------- |----------|-----| ------- |-----------|
| `ph_custom_cache_size` | 10000 | `CUSTOM_CACHE_SIZE` | pihole | False |
| `ph_dhcp_active` | false | `DHCP_ACTIVE` | pihole | False |
| `ph_dns_bogus_priv` | true | `DNS_BOGUS_PRIV` | pihole | False |
| `ph_dns_fqdn_required` | true | `DNS_FQDN_REQUIRED` | pihole | False |
| `ph_dnssec` | true | `DNSSEC` | pihole | False |
| `ph_ftlconf_local_ipv4` | localhost | `FTLCONF_LOCAL_IPV4` | pihole | False |
| `ph_host_port_pihole_53` | 53 | `host_port_pihole_53` | pihole | False |
| `ph_host_port_pihole_80` | 80 | `host_port_pihole_80` | pihole | False |
| `ph_ipv6` | true | `IPv6` | pihole | False |
| `ph_pihole_dns` | 9.9.9.9;149.112.112.112 | `PIHOLE_DNS` | pihole | False |
| `ph_pihole_gid` | 1000 | `PIHOLE_GID` | pihole | False |
| `ph_pihole_uid` | 1000 | `PIHOLE_UID` | pihole | False |
| `ph_releases` | {'pihole': 'latest'} | `None` | None | False |
| `ph_tz` | Europe/Berlin | `TZ` | pihole | False |
| `ph_virtual_host` | localhost | `VIRTUAL_HOST` | pihole | False |
| `ph_webpassword` | set a secure password here or it will be random | `WEBPASSWORD` | pihole | True |
| `ph_webtheme` | default-dark | `WEBTHEME` | pihole | False |
