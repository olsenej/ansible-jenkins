# How to:

+ sudo yum install git

+ git clone

+ sudo install_ansible.sh

+ Add hosts to inventory/hosts

+ ansible-playbook playbooks/main.yml -i inventory/hosts --ask-vault-pass --tags "first_run"

The first time you run this it will not install plugins because SSH isn't enabled through Jenkins. Follow the steps
below in the TO DO:

#### TO DO

These steps need to be done manually still.


+ Enable SSH connections on random port in web ui:
    - Manage Jenkins >
    - Configure Global Security >
    - SSH Server >
    - Random Port


+ Enable CAS Authentication in web ui:
    - Manage Jenkins >
    - Configure Global Security >
    - Security Realm >
        - CAS
        - CAS Server URL: https://sso.davenport.edu/cas/
        - CAS Protocol: CAS 1.0
        - Enable Single Sign-Out
    - Authorization >
        - Add jenkins user to matrix 
        - Grant Overall Administrator permission to jenkins user


+ Add jenkins user in web ui:
    - Manage Jenkins >
    - Manage Users >
    - Create User


+ Add jenkins public SSH key to user in web ui:
    - Copy from /var/lib/jenkins/.ssh/id_rsa.pub >
    - Paste into SSH Public Keys



#### Run ansible-playbook again using:
  + ansible-playbook playbooks/main.yml -i inventory/hosts --ask-vault-pass --tags "second_run"
