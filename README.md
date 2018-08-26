# tunnel

**tunnel** is a small wrapper around `ssh -fNL` which allows you to create,
stop, and restart ssh tunnels easily.

## Dependencies

None if you are on a standard linux distribution, else:

* nc
* ps
* ssh

## Usage

```
Usage: tunnel [options]

Displays tunnels status when launched with no options.

Options:

local-port  distant-port     creates a tunnel from your your ssh address on distant-port to localhost on local-port
stop, s     [local-port]     stops local-port tunnel or all tunnels if no port is specified
clean, c    [local-port]     removes local-port tunnel if stopped or all stopped tunnels if no port is specified
restart, r  [local-port]     restarts local-port tunnel if stopped or all stopped tunnels if no port is specified
config, cfg                  opens the configuration file with your default editor
```

### Example

```
$ tunnel
No active tunnel
$ tunnel 8080 22
$ tunnel
tunnel: 8080 -> 22 (server-1) OK
$ tunnel 8081 443
$ tunnel
tunnel: 8080 -> 22 (server-1) OK
tunnel: 8081 -> 443 (server-1) OK
$ tunnel stop 8081
$ tunnel
tunnel: 8080 -> 22 (server-1) OK
tunnel: 8081 -> 443 (server-1) KO
$ tunnel clean
$ tunnel
tunnel: 8080 -> 22 (server-1) OK
```
