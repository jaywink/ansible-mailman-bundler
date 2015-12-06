[![Galaxy](http://img.shields.io/badge/galaxy-jaywink.mailman-bundler-blue.svg?style=flat-square)](https://galaxy.ansible.com/list#/roles/6385)

## Mailman-Bundler role for Ansible

About [Mailman-Bundler](http://mailman-bundler.readthedocs.org/en/latest/).

Deploys the following:

* mailman3
* mailman web (Postorious & HyperKitty)

Mailman web is powered with Apache, PostgreSQL and uWSGI.

Both are launched via upstart scripts (`mailman` and `mailmanweb`).

### Status

This role is not production ready yet. Some TODO's:

* Currently HTTP only is served. HTTPS via LetsEncrypt coming up.
* Mailman3 should use the PostgreSQL database.
* Mailman-web uWSGI config is crazy
* Mailman3 upstart config needs work
* Mailman3 configuration cannot be done yet

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
