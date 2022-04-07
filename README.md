# REMOVE

- Search and replace "[ROLE-NAME]"
- Search for "[CHANGE-ME]"
- Search for "[IE]" and update/remove as needed

# [ROLE-NAME]

[ROLE-NAME] is a role that (A brief description of the role goes here.)

## Requirements

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

[IE]

- This role leverages a custom module to scrape the version number
    - This module requires the `beautifulsoup` pip package

## Role Variables

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

[IE]
There is only a single default variable defined:

```yaml
ncspot_install_dir: /usr/local/bin
```

## Dependencies

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

[IE]

- Needs the scrape-module role from `git@github.com:bashfulrobot/scrape-module.git`

This will also install the *requirements* listed above

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

[IE]

```yaml
#### requirements.yaml

roles:
  # from galaxy
  # - name: hurricanehrndz.rustup

  # Personal roles on GitHub
  - src: git+ssh://git@github.com/bashfulrobot/scrape-module.git
    scm: git
    version: main
  - src: git+ssh://git@github.com/bashfulrobot/ncspot.git
    scm: git
    version: main

# You can also add collections
collections:
  - name: community.general

```

```yaml
##### playbook.yaml

---
- name: configuring desktop system
  hosts: localhost
  become: no
  roles:
    - scrape-module
    - ncspot

```

## License

MIT

## Author Information

An optional section for the role authors to include contact information, or a website (HTML is not allowed).

[IE]

- Bashfulrobot [Github](https://github.com/bashfulrobot)
- Bashfulrobot [Twitter](https://twitter.com/bashfulrobot)
