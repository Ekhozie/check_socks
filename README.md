# check_socks

Nagios/Icinga plugin to monitor socks proxy

## Nagios configuration

Define command

```sh
# 'check_socks' command definition
define command{
    command_name   check_socks
    command_line   /usr/lib/nagios/plugins/check_socks -i '$ARG1$' -p '$ARG2$'
}
```

Define service

```sh
# Define a service to check socks proxy
define service{
    use                             generic-service
    host_name                       hostname
    service_description             Socks proxy
    check_command                   check_socks!<ip>!<port>
}
```

*Replace `<ip>` and `<port>` with your values*

## Script usage

```
Usage:
    --help     = Print this message
    -i         = Proxy IP address (default 127.0.0.1)
    -p         = Proxy port (default 1080)
    --target   = Url to check socks proxy (default https://www.google.com)
    --max-time = Maximum time in seconds that you allow the whole operation to take (default 10)
```

## Requirements

curl must be installed on the host.
