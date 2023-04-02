Coder v2 Install
=========

This Ansible role installs Coder v2 on Ubuntu. It takes care of downloading the appropriate `.deb` package (either `amd64` or `arm64`), installing it, configuring the `coder.env` file, and enabling the service in `systemctl`.

Requirements
------------

- Ubuntu 18.04 (Bionic), 20.04 (Focal) or 22.04 (Jammy)
- Ansible 2.9 or higher

Role Variables
--------------

| Variable          | Default      | Required | Description                                           |
|-------------------|--------------|:--------:|-------------------------------------------------------|
| `coder_access_url`| *(none)*     |    ✅    | The access URL for the Coder instance.                |
| `coder_http_address` | `0.0.0.0:80` |  ❌  | The HTTP address for the Coder instance.              |
| `coder_tls_enable`| `false`      |    ❌    | Whether to enable TLS for the Coder instance.         |
| `coder_tls_address` | `0.0.0.0:443` |  ❌  | The TLS address for the Coder instance (included only if TLS is enabled). |


Dependencies
------------

None.

Example Playbook
----------------

```yaml
- hosts: servers
  vars:
    coder_access_url: "https://your-coder-access-url.example.com"
  roles:
    - thehedgefrog.coder_v2_install
```

License
-------

MIT
