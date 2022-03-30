# Ansible Role: motd

Ansible role to manage `/etc/motd` and `/etc/issue(.net)`.

The files a provided by the templates under [`templates/`](templates).

## Installation

Example `requirements.yml` file for `ansible-galaxy`:

```yaml
roles:
  # My homelab roles
  - src: https://github.com/joshbeard/ansible-role-motd.git
    scm: git
    version: '0.1.0'
    name: jbeard.motd
```

Install with `ansible-galaxy -r requirements.yml`

## Usage

### Variables

| Variable             | Description
| -------------------- | ------------
| `manage_motd`        | Boolean toggling managing the motd file.
| `manage_issue_files` | Boolean toggling managing the issue and issue.net files.
| `motd_src`           | Path to template for the `/etc/motd` file.
| `issue_src`          | Path to template for the `/etc/issue` file.
| `issue_net_src`      | Path to template for the `/etc/issue.net` file.

### Example Configuration

```yaml
# Use a custom template, relative to the playbook dir
motd_src: "{{ playbook_dir }}/templates/motd-custom"
```
