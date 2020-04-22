# ansible-role-dkron
```
dkron_config:
  server: true
  bootstrap-expect: "{{ groups[ 'workers_group' ] | length }}"
  dc: eu
  bind-addr: "{{ansible_default_ipv4.address}}:8946"
  join: "{{ groups[ 'dkron_group' ] | map('extract', hostvars, ['ansible_default_ipv4', 'address']) | list }}"
```
