# Solution Highlights

* Immutable environment AMI based deployments and updates using Autoscaling groups. 
* AMI baking is done Via Ansible.
* Anisble scirpts can be ran against local workstation VM.

# Non-System Requirements For Running

* Permission to access this GIT repo (which you have if you see this)
* Valid AWS Access Key pair.

# System Requirements For Running

* SHH public key located at following system location: ~/.ssh/id_rsa.pub. See aws_create_ami.yml if you need to change location.
* GIT Installed. 
* This GIT repo cloned to system.
* Tools Installed:
  * Ansible. (ansible-playbook)
  * Python Boto. (pip)
  * Python Boto3. (pip)
  * AWS CLI. (pip)
  
Optional:
[Disable SSH Host Checking](http://bencane.com/2013/07/22/ssh-disable-host-checking-for-scripts-automation/)

Note: Fresh ubuntu 16.04 environment was used to test solution; Run the setup_environment_debian script in sudo mode:
```
$sudo bash setup_environment_debian
```

# How To Run

## Preparing System Environment.
1. Review "System Requirements For Running" section of this document.
2. Inject aws access keys:
```
$aws configure
```

## Baking AMI.

1. Execute AMI baking command:

```
$ansible-playbook aws_create_ami.yml --extra-vars "targetenv=aws sshconfiguser=centos"
```
Note: You may get SSH host checking prompt.
2. Wait awhile (3-5 minutes)
3. Note down the AMI ID from Anisble output:

```
TASK [debug] *******************************************************************
ok: [localhost] => {
    "msg": "AMI ID ami-17ed5d6f"
}
```

## Creating Infrastrcture.



## Baking AMI Locally

# Assignment Requirements I didn't Fullfill Due to Time.



# Things I Would Done if I Had More Time.

# Things I have Done if I Unlimited Time.

# Other Notes

# 3rd Party Tools/Libraries
