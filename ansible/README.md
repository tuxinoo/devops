# Requirements

```bash
sudo apt update 
sudo apt install direnv python3 python3-pip python3-venv -y
echo 'eval "$(direnv hook bash)"' >> ~/.bashrc
source ~/.bashrc
```

# Dependencies

```bash
pip3 install -r requirements.txt
# ou
make env
```

# Ansible Galaxy

## Création d'un rôle

```
ansible-galaxy init sample-role
```
