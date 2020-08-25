# Exastro ITAutomation docker
This Dockerfile provides the Exastro ITAutomation installation environment (all-in-one).<br>
notes: Exastro ITAutomation is not installed just by building this dockerfile<br>
# How to Install Exastro ITAutomation in Container
1. Download the required version of Dockerfile<br>
`git clone it-automation-docker/XXXXX or wget XXXXXXXXXXXXXX`<br>
1. Build Docker Image<br>
`docker image build -t exastro/it-automatio:tagname .`<br>
1. run container <br>
`docker run --privileged -d -p 8080:80 -p 10443:443 --name exastro01 exastro/it-automation:tagname`<br>
notes: Change the port number according to your environment.<br>
1. Install Exastro ITAutomation<br>
`docker exec -i -t exastro01  sh ita_builder_online.sh`<br>
# How to change installation settings<br>
If you want to change the installation settings, do not perform "4. Install Exastro IT Automation" and follow the procedure below.
1. `docker exec -i -t exastro01 /bin/bash` <br>
1. `vi ita_answers.txt`<br>
[notes:See the link manual(3.5 Configuration) for how to modify the answer file](https://exastro-suite.github.io/it-automation-docs/asset/Learn/ITA-online-install_en.pdf)<br>
1. `sh ita_builder_online.sh`<br>

# Exastro ITAutomation Installation settings<br>
The installation settings listed in the docker file.<br>
Base Image :CentOS8<br>
language:<br>
English (image name : X.X.X-en)<br>
Japanese (imagename : X.X.X-ja)<br>
DB settings db_name : ita_db<br>
db_root_password : ita_root_password<br>
db_username : ita_db_user<br>
db_password : ita_db_password<br>

# ita_answers.txt
#Select install mode. ("Install" or "Uninstall")
#e.g) install_mode:Install
install_mode:Install

#Enter install directory.
#e.g) ita_directory:/exastro/exastro
ita_directory:/exastro

#Select language. ("en_US" or "ja_JP")
#e.g) ita_language:ja_JP
ita_language:ja_JP(image name : X.X.X-ja)
ita_language:ja_JP(image name : X.X.X-ja)

#Select Operation System. ("RHEL7" or "RHEL8")
#e.g) ita_os:RHEL8
ita_os:RHEL8

#Enter the MariaDB root user's password
#e.g) db_root_password:sample_root_passwordsample_root_password
db_root_password:sample_root_password

#Decide the database name, username, and password for ITA.
#e.g) db_name:sample_db_namesample_db_name
db_name:sample_db_name
#e.g) db_username:sample_db_usernamesample_db_username
db_username:sample_db_username
#e.g) db_password:sample_db_passwordsample_db_password
db_password:sample_db_password

#Select the target you need to install.
