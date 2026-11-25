andrewrothstein.alpine-glibc-shim
=========
![Build Status](https://github.com/andrewrothstein/ansible-alpine-glibc-shim/actions/workflows/build.yml/badge.svg)

Mostly pieced together from [alpine-pkg-glibc](https://github.com/sgerrand/alpine-pkg-glibc) and [docker-alpine-glibc](https://github.com/frol/docker-alpine-glibc). Ideally allows me to use glibc compiled stuffs on Alpine Linux.

Requirements
------------

See [meta/main.yml](meta/main.yml)

Role Variables
--------------

`alpine_glibc_shim_provider` selects how glibc support is provided:

* `gcompat` (default): installs Alpine's own `gcompat` package. Maintained and signed by Alpine, works on all architectures. It is a compatibility layer, not a full glibc, so test your binaries.
* `sgerrand`: installs the unofficial [alpine-pkg-glibc](https://github.com/sgerrand/alpine-pkg-glibc) packages (x86_64 only, last release 2.35-r1). Only this provider supports `alpine_glibc_shim_generate_locale`.

See [defaults/main.yml](defaults/main.yml)

Dependencies
------------

See [meta/main.yml](meta/main.yml)

Example Playbook
----------------

```yml
- hosts: servers
  roles:
    - andrewrothstein.alpine-glibc-shim
```

License
-------

MIT

Author Information
------------------

Andrew Rothstein <andrew.rothstein@gmail.com>
