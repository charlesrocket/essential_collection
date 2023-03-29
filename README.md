# essential_collection
[![Ansible Role](https://img.shields.io/ansible/collection/2396)](https://galaxy.ansible.com/charlesrocket/essential)
[![molecule](https://github.com/charlesrocket/essential_collection/actions/workflows/ci.yml/badge.svg?branch=trunk&event=push)](https://github.com/charlesrocket/essential_collection/actions/workflows/ci.yml)

### Install

`requirements.yml`:

```
collections:
  - name: charlesrocket.essential
```

## `dotfiles`
#### Requirements
`git` on managed machines

### Example

```
- name: Playbook
  hosts: all

  roles:
    - charlesrocket.essential.dotfiles
```

### Set variables

```
dotfiles_repo: "https://github.com/charlesrocket/dotfiles.git" # dotfiles
dotfiles_repo_version: openbsd # branch to track
dotfiles_repo_accept_hostkey: false # StrictHostKeyChecking=no
dotfiles_repo_force: false # force git clone
dotfiles_repo_local_destination: "~/git/dotfiles" # local repo path
dotfiles_home: "~" # local dotfiles path
dotfiles_files: # files to track
  - .config/mc/ini
  - .zshrc
```

## `git`
### Example

```
- name: Playbook
  hosts: all

  roles:
    - charlesrocket.essential.git
```

### Credential helper

Define the following variables to deploy the credential helper:

```
git_repo_destination: "~/gitlab/git" # git repository destination
git_helper_directory: "~/bin" # helper directory
git_helper: ["netrc"]
```

* Add `git_repo_shallow: true` to use shallow clone.
* Add `git_repo_force: true` to override local modifications.
