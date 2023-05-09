# [1.7.0](https://github.com/de-it-krachten/ansible-role-nginx/compare/v1.6.0...v1.7.0) (2023-05-09)


### Features

* Move to namespaced role names ([5ee9ef2](https://github.com/de-it-krachten/ansible-role-nginx/commit/5ee9ef2d58f244ab42f95d9bb818aa3aad2cb1ea))
* Move to OS specific defaults ([1722d8a](https://github.com/de-it-krachten/ansible-role-nginx/commit/1722d8a4e2578a0f3966a0df6c0b7f41ca0b28aa))

# [1.6.0](https://github.com/de-it-krachten/ansible-role-nginx/compare/v1.5.1...v1.6.0) (2022-10-12)


### Features

* Move to FQCN ([c4c60fb](https://github.com/de-it-krachten/ansible-role-nginx/commit/c4c60fb071edf56a39cb36b10a89d09d358852e5))
* Update CI to latest standards ([331a1d6](https://github.com/de-it-krachten/ansible-role-nginx/commit/331a1d6037c8de27078c601cdd0bc60dc3fa8b7d))

## [1.5.1](https://github.com/de-it-krachten/ansible-role-nginx/compare/v1.5.0...v1.5.1) (2022-09-25)


### Bug Fixes

* Save webserver info for other playbooks/roles to use ([0eb515b](https://github.com/de-it-krachten/ansible-role-nginx/commit/0eb515b151e289475ec868c5c9303b7afae4e819))

# [1.5.0](https://github.com/de-it-krachten/ansible-role-nginx/compare/v1.4.0...v1.5.0) (2022-07-28)


### Features

* Implement ansible-lint v6 support ([48bd6e2](https://github.com/de-it-krachten/ansible-role-nginx/commit/48bd6e2ed24379d0c60fab8c75361de48ef524e7))

# [1.4.0](https://github.com/de-it-krachten/ansible-role-nginx/compare/v1.3.0...v1.4.0) (2022-07-04)


### Features

* Add support for RHEL9 ([c0a9419](https://github.com/de-it-krachten/ansible-role-nginx/commit/c0a9419397445d5a8bed03509c384134d600dfc1))

# [1.3.0](https://github.com/de-it-krachten/ansible-role-nginx/compare/v1.2.1...v1.3.0) (2022-05-31)


### Bug Fixes

* make it possible to exclude vhost creation ([3450605](https://github.com/de-it-krachten/ansible-role-nginx/commit/34506058c5b65837a76814302dacc7a59b6fb68a))


### Features

* move vhost code into separate task list ([9c7526f](https://github.com/de-it-krachten/ansible-role-nginx/commit/9c7526f93bc21df4845a1fa0a5c94a652e23f0e0))

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
