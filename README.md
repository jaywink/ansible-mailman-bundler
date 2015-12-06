[![Galaxy](https://img.shields.io/ansible/role/6385.svg)](https://galaxy.ansible.com/list#/roles/6385)

## Mailman-Bundler role for Ansible

About [Mailman-Bundler](http://mailman-bundler.readthedocs.org/en/latest/).

Deploys the following:

* mailman3
* mailman web (Postorious & HyperKitty)

Mailman web is powered with Apache, PostgreSQL and uWSGI.

Both are launched via upstart scripts (`mailman` and `mailmanweb`).

### Status

This role is not production ready yet. See issues.

### Requirements

#### Operating system support

Tested only on Ubuntu 14.04. Probably works with anything that has similar packages.

#### Ansible

Created and tested with 1.9.4.

#### Ansible roles

* [Stouts.postfix](https://github.com/Stouts/Stouts.postfix) or a similar postfix setup.

### Configuration

See `defaults/main.yml` for possible options. Most of these are required in some way, at least for production usage.

### Manual steps not covered by role

To create an admin user for mailman-web:

    sudo su - mailman
    source venv/bin/activate
    cd mailman-bundler
    ./bin/mailman-web-django-admin createsuperuser

### License

MIT
