Ansible Role: locale
====================

An Ansible role that configures locale settings and virtual console keyboard.


Table of Contents
-----------------

<!-- toc -->

- [Requirements](#requirements)
- [Role Variables](#role-variables)
  * [Language](#language)
  * [Virtual Console Keyboard](#virtual-console-keyboard)
  * [Virtual Console Font](#virtual-console-font)
- [Dependencies](#dependencies)
- [Example Playbook](#example-playbook)
  * [Top-Level Playbook](#top-level-playbook)
  * [Role Dependency](#role-dependency)
- [License](#license)
- [Author Information](#author-information)

<!-- tocstop -->


Requirements
------------

- Ansible 2.9


Role Variables
--------------

### Language

```yml
system_language: 'en_US.UTF-8'
```

### Virtual Console Keyboard

```yml
system_keyboard_keytable: 'de-latin1-nodeadkeys'
system_keyboard_layout: 'de'
system_keyboard_model: 'pc105'
system_keyboard_type: 'pc'
system_keyboard_variant: 'nodeadkeys'
system_keyboard_options: 'terminate:ctrl_alt_bksp Ctrl+Alt+Backspace'
system_keyboard_backspace_behaviour: 'guess'
```

### Virtual Console Font

```yml
system_font: 'latarcyrheb-sun16'
```


Dependencies
------------

None.


Example Playbook
----------------

Add to `requirements.yml`:

```yml
---

- src: idiv_biodiversity.locale

...
```

Download:

```console
$ ansible-galaxy install -r requirements.yml
```

### Top-Level Playbook

Write a top-level playbook:

```yml
---

- name: head server
  hosts: head

  roles:
    - role: idiv_biodiversity.locale
      tags:
        - locale

...
```

### Role Dependency

Define the role dependency in `meta/main.yml`:

```yml
---

dependencies:

  - role: idiv_biodiversity.locale
    tags:
      - locale

...
```


License
-------

MIT


Author Information
------------------

This role was created in 2017 by [Christian Krause][author] aka [wookietreiber
at GitHub][wookietreiber], HPC cluster systems administrator at the [German
Centre for Integrative Biodiversity Research (iDiv)][idiv].


[author]: https://www.idiv.de/en/groups_and_people/employees/details/61.html
[idiv]: https://www.idiv.de/
[wookietreiber]: https://github.com/wookietreiber
