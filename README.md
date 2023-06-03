Role Name
=========

Minimal role to install docker on a host. Intended for use in my homelab.

Requirements
------------

None

Dependencies
------------

None

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml 
docker_ce_package: "docker-ce"
```
The name of the docker package to install. This can be used to install a specific version of docker.

```yaml
docker_daemon_options:
  insecure-registries:
    - "registry.example.com"
    - "registry.example.com:5000"
```
Custom `dockerd` options can be configured through this dictionary representing the json file `/etc/docker/daemon.json`.


Example Playbook
----------------

```yaml
- hosts: all
  vars:
    docker_ce_package: "docker-ce=5:23.0.1-1~ubuntu.20.04~focal"
    docker_daemon_options:
      insecure-registries:
        - "registry.example.com"
        - "registry.example.com:5000"
  roles:
    - ecshreve.docker
```

License
-------

MIT

Author Information
------------------

This role was created in 2023 by [Eric Shreve](github.com/eshreve)
