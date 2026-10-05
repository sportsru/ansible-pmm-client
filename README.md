# pmm_client

This role installs and configures the Percona Monitoring and Management Client.

## Variables

See `defaults/main.yml` for all variables. Version related:

- `pmm_client_version` / `pmm_client_version_revision` [default: `3.8.1` / `1`]: Package version to install (`pmm-client=3.8.1-1.<release>`); the major version selects the repository (`pmm3-client`)
- `pmm_client_server_version` [optional, e.g. `3.8.1`]: PMM Server version; the role fails if `pmm_client_version` is newer
- `pmm_client_hold` [default: `true`]: Hold the package (`apt-mark hold`), so `apt upgrade` does not change its version; it is unheld automatically when `pmm_client_version` changes
- `pmm_client_repository_url`, `pmm_client_repository_name`, `pmm_client_repository_keyring`, `pmm_client_repository_key_id`, `pmm_client_repository_keyring_manage`: APT repository and the keyring of its `signed-by` (the Percona key is added to it by default)
- `pmm_client_no_log` [default: `true`]: Hide credentials in the output of the `pmm-admin` tasks

## Author Information

- Based on the Ansible role from [Timo Runge](https://github.com/timorunge/ansible-pmm-client)
- Heavily modified by: Mikhail Konyakhin
