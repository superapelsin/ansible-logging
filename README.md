### Configure logging on debian

Run with 
ansible-playbook main.yml -t (backup|setup|restore)

### Tags

backup - backup current config files

setup - configure logging and restart services

restore - restore last backup configs and restart services


### Setup ssh.conf
before running create ssh.cfg in root of this repo with   tsh config > ssh.cfg

sample: 

```
# Begin generated Teleport configuration for tp.wb.ru by tsh

# Common flags for all teleport hosts
Host * tp.wb.ru
    UserKnownHostsFile "/Users/ilyapivovarov/.tsh/known_hosts"
    IdentityFile "/Users/ilyapivovarov/.tsh/keys/tp.wb.ru/pivovarov.ilya2"
    CertificateFile "/Users/ilyapivovarov/.tsh/keys/tp.wb.ru/pivovarov.ilya2-ssh/teleport-cert.pub"
    HostKeyAlgorithms rsa-sha2-512-cert-v01@openssh.com,rsa-sha2-256-cert-v01@openssh.com,ssh-rsa-cert-v01@openssh.com

# Flags for all teleport hosts except the proxy
Host * !tp.wb.ru
    Port 3022
    ProxyCommand "/usr/local/bin/tsh" proxy ssh --cluster=teleport --proxy=tp.wb.ru:443 %r@%h:%p

# End generated Teleport configuration
```