Configure logging on debian

run with 
ansible-playbook main.yml -e __cluster_name=(cluster name without k8s. prefix) -t (backup|setup|restore)