# Trusted Proxy Module for Caddy

This module retrieves IP addresses from a specified URL. You must provide the URL in your configuration.

It is supported from Caddy v2.6.3 onwards.

## Example Configuration

Place the following configuration in the global options under the corresponding server options:

```caddy
trusted_proxies url {
    url https://www.cloudflare.com/ips-v4  # specify the URL to fetch the IP list
    url https://www.cloudflare.com/ips-v6  # You can use multiple URLs
    interval 12h
    timeout 15s
}
```

## Defaults

| Name     | Description                                             | Type     | Default    |
|----------|---------------------------------------------------------|----------|------------|
| url      | URL(s) to retrieve the IP list                          | string   | *required* |
| interval | Frequency at which the IP list is retrieved             | duration | 1h         |
| timeout  | Maximum time to wait for a response from URL            | duration | no timeout |
