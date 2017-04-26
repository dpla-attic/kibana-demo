# kibana-demo

This is a **demonstration** of a Kibana and Rsyslog installation, to assist us
at the DPLA with deciding whether and how to use these applications for
centralizing our system and application logging.

## Versions Represented

The ELK stack software versions match those that are currently supported by AWS.

Elasticsearch: 5.1.x
Kibana: 5.1.x
Logstash: 5.1.x
Rsyslog: 8.26.0 (latest available, adiscon/v4-stable repo)

## Installation

Run `vagrant up` and the VM will be created and provisioned.

After running `vagrant up` and having Ansible provision the system, you can
see the Kibana interface at `http://192.168.50.20:5601/`.  You'll be prompted to
configure an index pattern.  Select the default pattern that you're presented
with and click "continue."  You should then be able to click "Discover" in the
left-hand navigation and see some log messages.

You should be able to use a utility like `logger(1)` to send a syslog message
from your host environment to your VM, so that it gets parsed and inserted into
Elasticsearch for Kibana to find.

Example, SSHed in to the VM:
```
ubuntu@logtest:~$ logger "Test message"
```
