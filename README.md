# Running Zulip in Docker with Ansible

This project assumes you have a working knowledge of Docker and Ansible.

It is based on the official Zulip docker-compose file, but with some modifications to make it work with Ansible.
The upstream git repository is https://github.com/zulip/docker-zulip.

This playbook expects a running traefik instance to handle the reverse proxy.
In fact, it is configured to work with the [MASH-project](https://github.com/mother-of-all-self-hosting/mash-playbook).

## Usage

1. Clone this repository
2. There is an example-vars.yml file that you can copy to your prefered vars.yml variant and modify to your needs.
3. Run the playbook.

## Upgrade

To upgrade Zulip, change the version in the `docker-compose.yml` file and run the playbook.
There are multiple docker containers that need to be updated.
Read the `docker-compose.yml` file and zulip upgrade notes in the zulip-docker-repository carefully.

## Known issues

After first initial run, 'settings.py' is created as a directory.
This needs to be manually changed to a file (`rm -r settings.py && touch settings.py`)
