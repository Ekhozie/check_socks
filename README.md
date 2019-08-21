# check_socks

Nagios/Icinga plugin to monitor socks proxy

## Configuration

Define command

```sh
# 'check_socks' command definition
define command{
    command_name   check_socks
    command_line   /usr/lib/nagios/plugins/check_socks -b '$ARG1$' -l '$ARG2$'
}
```

Define service

```sh
# Define a service to check socks proxy
define service{
    use                             generic-service
    host_name                       hostname
    service_description             Socks proxy
    check_command                   check_socks!<local_address>!<local_port>
}
```

## Requirements

curl must be installed on the host.
