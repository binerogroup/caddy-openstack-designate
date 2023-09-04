OpenStack Designate DNS module for Caddy
===========================

This package contains a DNS provider module for [Caddy](https://github.com/caddyserver/caddy). It can be used to manage DNS records in OpenStack Designate DNS zones.

## Caddy module name

```
dns.providers.openstack-designate
```

## Authenticating

See [the associated README in the libdns package](https://github.com/binerogroup/openstack-designate) for important information about credentials.

## Building

To compile this Caddy module, follow the steps describe at the [Caddy Build from Source](https://github.com/caddyserver/caddy#build-from-source) instructions and import the `github.com/binerogroup/caddy-openstack-designate` plugin

## Config examples

To use this module for the ACME DNS challenge, [configure the ACME issuer in your Caddy JSON](https://caddyserver.com/docs/json/apps/tls/automation/policies/issuer/acme/) like so:

```json
{
  "module": "acme",
  "challenges": {
    "dns": {
      "provider": {
        "name": "openstack-designate"
      }
    }
  }
}
```

or with the Caddyfile:

```
tls {
  dns openstack-designate { }
}
```
