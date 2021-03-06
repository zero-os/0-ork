# Zero-OS ORK

The ORK monitors CPU consumption, memory consumption and interface packets/bytes transmission rate and takes action if 
the consumption exceeds the defined thresholds.

ORK acts on processes, vms and network interfaces to restore the resources consumption to allowed limits. It kills
processes and vms eating up the cpu and memory. It also squeezes (and shutsdown if needed) network interfaces exceeding 
the allowed packets/bytes transmission rate.


## How to build
```shell
git clone https://github.com/zero-os/0-ork
cd 0-ork
go build
```

## How to run

`./0-ork --level DEBUG`
- `--level` : specifies the log level and defaults to INFO

## Disable ORK

To disable ork from monitoring and taking any actions, add `ork=development` in the kernel parameters of the host on which
ork is running.

To disable a specific monitoring, add `ork=<nomonitor>` in the kernel parameters where `<nomonitor>` can be any of the following:

* `nocpu`: disables cpu monitoring
* `nomem`: disables memory monitoring
* `nonetwork`: disables network monitoring
* `nofairusage`: disables fairusage monitoring