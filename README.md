Configure logging on debian

run with 
ansible-playbook main.yml -e __cluster_name=(cluster name without k8s. prefix) -t (backup|setup|restore)


before running create ssh.cfg in root of this repo with   tsh config > ssh.cfg