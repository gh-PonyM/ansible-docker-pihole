# Role ansible_docker_pihole

This role was generated be role deploy-docker-compose-template

## docker-compose.yml template

```yaml
---
version: '3'
services:
  pihole:
    container_name: pihole
    image: pihole/pihole:{{ ph_releases['pihole'] }}
    ports:
    - '{{ ph_host_port_pihole_53 }}:53/tcp'
    - '{{ ph_host_port_pihole_53 }}:53/udp'
    - '{{ ph_host_port_pihole_80 }}:80/tcp'
    dns:
    - 9.9.9.9
    - 9.9.9.10
    environment:
      TZ: '{{ ph_tz }}'
      WEBPASSWORD: '{{ ph_webpassword }}'
      PIHOLE_DNS: '{{ ph_pihole_dns }}'
      DNSSEC: '{{ ph_dnssec }}'
      DNS_BOGUS_PRIV: '{{ ph_dns_bogus_priv }}'
      DNS_FQDN_REQUIRED: '{{ ph_dns_fqdn_required }}'
      DHCP_ACTIVE: '{{ ph_dhcp_active }}'
      WEBTHEME: '{{ ph_webtheme }}'
      PIHOLE_UID: '{{ ph_pihole_uid }}'
      PIHOLE_GID: '{{ ph_pihole_gid }}'
      CUSTOM_CACHE_SIZE: '{{ ph_custom_cache_size }}'
      IPv6: '{{ ph_ipv6 }}'
      VIRTUAL_HOST: '{{ ph_virtual_host }}'
      FTLCONF_LOCAL_IPV4: '{{ ph_ftlconf_local_ipv4 }}'
    volumes:
    - '{{ ph_pihole_mount_dir }}:/etc/pihole'
    - '{{ ph_dnsmasq_d_mount_dir }}:/etc/dnsmasq.d'
    cap_add:
    - NET_ADMIN
    restart: unless-stopped

```
## Defaults

| Variable | default  | ENV | used by | is secret |
| -------- |----------|-----| ------- |-----------|
| `ph_custom_cache_size` | 10000 | `CUSTOM_CACHE_SIZE` | pihole | False |
| `ph_dhcp_active` | false | `DHCP_ACTIVE` | pihole | False |
| `ph_dns_bogus_priv` | true | `DNS_BOGUS_PRIV` | pihole | False |
| `ph_dns_fqdn_required` | true | `DNS_FQDN_REQUIRED` | pihole | False |
| `ph_dnssec` | true | `DNSSEC` | pihole | False |
| `ph_ftlconf_local_ipv4` | localhost | `FTLCONF_LOCAL_IPV4` | pihole | False |
| `ph_ipv6` | true | `IPv6` | pihole | False |
| `ph_pihole_dns` | 9.9.9.9;9.9.9.10 | `PIHOLE_DNS` | pihole | False |
| `ph_pihole_gid` | 1000 | `PIHOLE_GID` | pihole | False |
| `ph_pihole_uid` | 1000 | `PIHOLE_UID` | pihole | False |
| `ph_tz` | Europe/Berlin | `TZ` | pihole | False |
| `ph_virtual_host` | localhost | `VIRTUAL_HOST` | pihole | False |
| `ph_webpassword` | set a secure password here or it will be random | `WEBPASSWORD` | pihole | True |
| `ph_webtheme` | default-dark | `WEBTHEME` | pihole | False |
| `ph_host_port_pihole_53` | 53 | `host_port_pihole_53` | pihole | False |
| `ph_host_port_pihole_80` | 80 | `host_port_pihole_80` | pihole | False |
| `ph_releases` | {'pihole': 'latest'} | `` | None | False |
