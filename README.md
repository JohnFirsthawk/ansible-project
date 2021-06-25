Procedure
* create connection with jenkins server with ssh
* take root access and then access to jenkins workspace
```bash
sudo su
su jenkins
cd
cd workspace
```
* check that ansible-project is in workspace
*check connectictivy with deployment vm
* run 
```bash
ansible -m ping all
```


## Create self-signed certificates
```bash
cd files/certs
openssl req -x509 -newkey rsa:4096 -keyout server.key -out server.crt -days 365 -nodes -subj '/C=GR/O=myorganization/OU=it/CN=myorg.com'
```



* run the playbook that install django-project from git in deployment server
```bash
ansible-playbook playbooks/django-project-install.yml
```

* postgres
install postgresql role
```bash
ansible-galaxy install geerlingguy.postgresql
```
## Docker
```bash
ansible-galaxy install geerlingguy.docker
ansible-galaxy install geerlingguy.pip

```
## Jenkins
```bash
ansible-galaxy install geerlingguy.jenkins
ansible-galaxy install geerlingguy.java

```

## Links
* [apt module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)
* [file module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/file_module.html)
* [copy module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/copy_module.html)
* [service module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/service_module.html)
* [debconf module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/debconf_module.html)

* [ansible postgres role](https://galaxy.ansible.com/geerlingguy/postgresql)
