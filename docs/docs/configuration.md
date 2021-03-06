# Configuration

Settings for Dcron can be specified in three ways: Using a `config/dcron.json` config file, using env variables starting with `DCRON_` or using command line arguments.

## Command line options

* `-node` - Name of the node, must be unique in the cluster. By default this is the hostname of the machine.

* `-bind` - The address that Dcron will bind to for communication with other Dcron nodes. By default this is "0.0.0.0:8946". Dcron nodes may have different ports. If a join is specified without a port, we default to locally configured port. Dcron uses both TCP and UDP and use the same port for both, so if you have any firewalls be sure to allow both protocols. If this configuration value is changed and no port is specified, the default of "8946" will be used.

* `-http-addr` - The address where the web UI will be binded. By default `:8080`

* `-etcd-machines` - Comma separated addresses of the etcd machines to use. Could be one or several. By default `127.0.0.1:2379`

* `-tag` - The tag flag is used to associate a new key/value pair with the agent. The tags are gossiped and can be used to provide additional information such as roles, ports, and configuration values to other nodes. Multiple tags can be specified per agent. There is a byte size limit for the maximum number of tags, but in practice dozens of tags may be used. Tags can be changed during a config reload.

* `-server` - If this agent is a Dcron server, just need to be present. Absent by default.
