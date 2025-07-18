# Tutor ansible role
[![Ansible Lint](https://github.com/Abstract-Tech/ansible-role-tutor/actions/workflows/ci.yml/badge.svg)](https://github.com/Abstract-Tech/ansible-role-tutor/actions/workflows/ci.yml)
A role to deploy & configure openedx managed by tutor

# Role variables

| Variable          | Required | Default | Choices                                 | Comments                                    |
|-------------------|----------|---------|-----------------------------------------|---------------------------------------------|
| tutor_version     | no       | 15.3.1  | https://pypi.org/project/tutor/#history |                                             |
| tutor_config_repo | yes      |         |                                         | Bring your own                              |
| tutor_secrets     | yes      |         |                                         | Get secrets from your config in YAML format |

tutor_secrets example: 

```yaml
JWT_RSA_PRIVATE_KEY: "-----BEGIN RSA PRIVATE KEY-----\n...\n-----END RSA PRIVATE KEY-----"
CMS_OAUTH2_SECRET: "..."
ID: "..."
MYSQL_ROOT_PASSWORD: "..."
OPENEDX_MYSQL_PASSWORD: "..."
OPENEDX_SECRET_KEY: "..."
```


# Example playbook

```yaml
- hosts: all
  roles:
    - tutor
```
