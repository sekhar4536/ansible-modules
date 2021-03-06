# ansible-modules
Custom modules that I developed for Ansible.

## How to use

* It is pretty easy to integrate these modules into your code; the [official doc](https://docs.ansible.com/ansible/2.5/dev_guide/developing_modules.html) provides several approaches to doing this.
* However, one approach you can follow is as follows. This is also repository-independent i.e. you can use these modules across multiple repositories.
  * `git clone` this repository; for example, to `/home/username/ansible-modules`
  * Edit your `ansible.cfg` file to contain the `library` key ( [reference](https://docs.ansible.com/ansible/2.5/reference_appendices/config.html#default-module-path) )

```
[defaults]
library=/home/username/ansible-modules
```

## Verifying that the module is loaded

You can verify the path from where the module was loaded by running ansible-playbook with `-vvv`. You will see the words `using module file`:

```
TASK [prometheus-grafana : win_docker_container] ******************************************************************************************************************************************************************
task path: /home/vish/foo/roles/prometheus-grafana/tasks/main.yml:14
Using module file /home/vish/ansible-modules/win_docker_container.ps1
...
```

## About the modules

| Module Name | What it does |
|-------------|--------------|
| [`win_docker_container`](win_docker_container.ps1) | Starts, or Stops/Removes Docker Containers on Windows Server 2016. |
