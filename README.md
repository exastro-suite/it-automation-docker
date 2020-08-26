# Exastro ITAutomation docker
This Dockerfile provides the Exastro ITAutomation installation environment (all-in-one).<br>
notes: Exastro ITAutomation is not installed just by building this dockerfile<br>
# How to build Exastro ITAutomation in a container
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
language:English or Japanese<br>
DB settings db_name : ita_db<br>
db_root_password : ita_root_password<br>
db_username : ita_db_user<br>
db_password : ita_db_password<br>

# ita_answers.txt
#Select install mode. ("Install" or "Uninstall")<br>
#e.g) install_mode:Install<br>
install_mode:Install<br>

#Enter install directory.<br>
#e.g) ita_directory:/exastro/exastro<br>
ita_directory:/exastro<br>

#Select language. ("en_US" or "ja_JP")<br>
#e.g) ita_language:ja_JP<br>
ita_language:en_US(Dockerfile-X.X.X-en)<br>
ita_language:ja_JP(Dockerfile-X.X.X-ja)<br>

#Select Operation System. ("RHEL7" or "RHEL8")<br>
#e.g) ita_os:RHEL8<br>
ita_os:RHEL8<br>

#Enter the MariaDB root user's password<br>
#e.g) db_root_password:sample_root_passwordsample_root_password<br>
db_root_password:sample_root_password<br>

#Decide the database name, username, and password for ITA.<br>
#e.g) db_name:sample_db_namesample_db_name<br>
db_name:sample_db_name<br>
#e.g) db_username:sample_db_usernamesample_db_username<br>
db_username:sample_db_username<br>
#e.g) db_password:sample_db_passwordsample_db_password<br>
db_password:sample_db_password<br>

#Select the target you need to install.<br>
