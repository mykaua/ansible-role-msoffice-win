# ansible-role-msoffice-win


Ansible Common Role template for Windows server.
Installing MS Office 2019 to Windows Server 2019

### Requirements

* Minimal Version of the ansible for installation: 2.9
* Supported OS:
    * Windows server 2019

### Variables:
  * default/main.yml

| Variables      | Default |type |Descrription     |
| :---        |    :----:   |:----: |  ---: |
| office_license_key |  | string | license key for activating MS Office 2019|
| remote_install_path | C:\Scripts | string | Location of configuration and install packages |
| product_id | Standard2019Volume | string | [Which products to install](https://docs.microsoft.com/en-us/office365/troubleshoot/installation/product-ids-supported-office-deployment-click-to-run) |   



### Example Playbook
```
---
- name: Install MS Office 2019
  hosts: all
  roles:
    - role: ansible-role-msoffice-win
      vars:
        - office_license_key: XXXX-XXXX-XXXX-XXXX-XXXX
        - remote_install_path: C:\Scripts
        - product_id: Standard2019Volume
```

##### Author Information
  * author: Mykola Raryk
  * description: Ansible role for installing MS Office 2019 on windows server 2019
  * company:

#### Aditional information

winrm - https://raw.githubusercontent.com/ansible/ansible/v2.10.0/examples/scripts/ConfigureRemotingForAnsible.ps1

winrm varibales:

ansible_connection: winrm
ansible_winrm_server_cert_validation: ignore
ansible_port: 5986
ansible_winrm_transport: credssp
ansible_winrm_message_encryption: always
