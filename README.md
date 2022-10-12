# git_role
[![Ansible Role](https://img.shields.io/ansible/role/60363)](https://galaxy.ansible.com/charlesrocket/git)
[![molecule](https://github.com/charlesrocket/git_role/actions/workflows/molecule.yml/badge.svg?branch=master&event=push)](https://github.com/charlesrocket/git_role/actions/workflows/molecule.yml)
![score](https://img.shields.io/ansible/quality/60363)

Install Git on BSD/Linux machines with Ansible.

## Setup

Run `ansible-galaxy install charlesrocket.git` or use `requirements.yml`:

```
roles:
  - name: charlesrocket.git
```

## Example

```
- name: Playbook
  hosts: all

  roles:
    - charlesrocket.git
```

### `netrc` credential helper

* Requires `make`/`gmake`

To deploy the `netrc` helper define the following variables:

```
git_repo_local: "~/gitlab/git"
git_helper_destination: "~/bin"
git_netrc_helper: true
```
