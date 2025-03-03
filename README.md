# playbooks retailor.io

Includes ansible playbooks for provisioning & configuring retailor server nodes.

## run

Directory `plays/` contains all available plays. To run a play specify the inventory file and the play. This runs for all hosts specified in `inventory.ini` in order to keep state updated, to run on a single host pass flag `-l web2`.

```bash
ansible-playbook -i inventory plays/tailscale.yml
```

Specifying a single host:

```bash
ansible-playbook -i inventory plays/firewall.yml -l cache
```

## install

Install using homebrew, apt or another package manager:

MacOS:

```bash
brew install ansible-playbook
```

Ubuntu:

```bash
(sudo) apt install ansible-playbook
```
