## [1.2.1](https://github.com/de-it-krachten/ansible-role-nginx/compare/v1.2.0...v1.2.1) (2022-05-16)


### Bug Fixes

* /etc/nginx/config.d is now created after nginx installation ([334f2a8](https://github.com/de-it-krachten/ansible-role-nginx/commit/334f2a8a345a44f2255c2ccce29fbe810b4139b0))

# [1.2.0](https://github.com/de-it-krachten/ansible-role-nginx/compare/v1.1.1...v1.2.0) (2022-05-08)


### Features

* add support for Ubuntu 22.04 ([bf670cb](https://github.com/de-it-krachten/ansible-role-nginx/commit/bf670cb9292ee2789b36756763378e97a9563812))
* optional default server configuration ([1439968](https://github.com/de-it-krachten/ansible-role-nginx/commit/1439968887c2693e092f881d83b3551cb278d4fd))

## [1.1.1](https://github.com/de-it-krachten/ansible-role-nginx/compare/v1.1.0...v1.1.1) (2022-04-10)


### Bug Fixes

* update config permissions from 755 -> 644 ([b014227](https://github.com/de-it-krachten/ansible-role-nginx/commit/b01422796f7b3439386cda40f12904c13ba8a744))

# [1.1.0](https://github.com/de-it-krachten/ansible-role-nginx/compare/v1.0.0...v1.1.0) (2022-03-12)


### Bug Fixes

* add forgotten 'nginx_locations' ([ba3ec86](https://github.com/de-it-krachten/ansible-role-nginx/commit/ba3ec862069f25665afd4b3a08712a74ac5603cc))
* RHEL7 (and family) still depend on Python 2.7 for passlib ([b86861f](https://github.com/de-it-krachten/ansible-role-nginx/commit/b86861f4c09c253900b79044f642092303b8c6e0))


### Features

* add support for htpasswd ([7d22700](https://github.com/de-it-krachten/ansible-role-nginx/commit/7d2270083b5ad6b7c6362f5fe16e49b8ae447e0f))

# 1.0.0 (2022-03-07)


### Features

* initial release ([da3dde5](https://github.com/de-it-krachten/ansible-role-nginx/commit/da3dde5ef53c7e9d07ab02cbc81d3278eeb7d784))