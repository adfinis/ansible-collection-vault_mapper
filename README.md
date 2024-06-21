# Ansible Collection - adfinis.vault_mapper

![License](https://img.shields.io/github/license/adfinis/ansible-collection-vault_mapper)
![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/adfinis/ansible-collection-vault_mapper/ansible-lint.yml)
[![adfinis.vault_mapper on Ansible Galaxy](https://img.shields.io/badge/collection-adfinis.vault_mapper-blue)](https://galaxy.ansible.com/ui/repo/published/adfinis/vault_mapper/)


A collection of roles to generate templated secrets from HashiCorp Vault.

## Roles

### `adfinis.vault_mapper.vault`

Common tasks to perform operations on HashiCorp Vault.

### `adfinis.vault_mapper.to_k8s`

Specifics for Kubernetes resources.

#### Usage example

Add to `requirements.yml`:

```yaml
collections:
  - name: adfinis.vault_mapper
    version: 1.0.0
```

Install requirements:

```
apt install python3-hvac
ansible-galaxy collection install -r requirements.yml
```


See `playbook.yaml` and `templates/` in `example/`

Playbook execution is local and will create manifests in `./generated/to_k8s/{{ system }}` directory. At end of playbook execution, it will display commands to execute for applying or inspecting the generated resources:

```
TASK [to_k8s : Commands for dev] ***************************************************************************************************************************
ok: [localhost] => {
    "msg": [
        "Compare: kubectl diff -k generated/to_k8s/dev",
        "Apply dry run: kubectl apply -k generated/to_k8s/dev --dry-run=server",
        "Apply: kubectl apply -k generated/to_k8s/dev"
    ]
}
```

## License

[GPL-3.0-or-later](https://github.com/adfinis-sygroup/ansible-collection-vault_mapper/blob/main/LICENSE)

## Author Information

The Ansible collection `adfinis.vault_mapper` was written by:

* Adfinis AG | [Website](https://www.adfinis.com/) | [GitHub](https://github.com/adfinis)

