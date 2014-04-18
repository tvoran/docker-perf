docker-perf
===========

Performance monitoring for applications in docker containers

Overview
--------

docker-perf uses ansible to setup/install docker and collectd clients on a set
of hosts, and then launch a docker container running a collectd server which
uses carbon/graphite to store performance statistics from the collectd clients.

Setup
-----

Install ansible:

    pip install ansible

Fill in a hosts file with hostnames and IPs for the [docker] and
[docker-master] groups. (Refer to hosts.example).

Then deploy the system using ansible:

    ansible-playbook deploy.yml

Host groups
-----------

The [docker] group should include all hosts that will be running docker
containers, and the [docker-master] group should consist of one of the [docker]
hosts that will be running the collectd/graphite container.

The host names in the hosts file can be arbitrary, though using the actual
instance names helps when matching ansible output to reality.
