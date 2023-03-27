# IPFS Cluster

Features:
  - Automatic crdt and peers configuration.
  - Downloads binaries for updates via local IPFS gateway, if already installed.
  - Supports x86_64 and aarch64.


## Requirements

- Target system uses systemd


## Role Variables

- `ipfs_cluster_version`: (it's obvious)
- `ipfs_cluster_secret`: Required. Create one using `od -vN 32 -An -tx1 /dev/urandom | tr -d ' \n'` (see also: [docs](/ipns/cluster.ipfs.io/documentation/reference/configuration/#manual-secret-generation))
- `ipfs_cluster_peer_ip`: Peer IP (default: `ansible_default_ipv4`)


## Dependencies

- [ansible-role-ipfs](https://codeberg.org/etam/ansible-role-ipfs)


## Example Playbook

```yml
- hosts: ipfs
  roles:
    - ipfs
    - ipfs-cluster
```


## License

[GPL-3.0-or-later](COPYING.txt)


## Author Information

Adam "etam" Mizerski <adam@mizerski.pl> https://etam-software.eu
