English | [日本語](README.ja.md)<br>
<br>
# Exastro ITAutomation docker <br>
This Dockerfile provides the Exastro ITAutomation installation environment (all-in-one).<br>
Notes: Exastro ITAutomation is not installed just by building this dockerfile.[Download the installed image from Docker-Hub](https://hub.docker.com/r/exastro/it-automation/).<br>
# How to build Exastro ITAutomation in a container
1. Download the required version of Dockerfile<br>
`# git clone https://github.com/exastro-suite/it-automation-docker.git`<br>
1. Build Docker Image<br>
English ： `# cd it-automation-docker/1.5.0-en`<br>
Japanese ： `# cd it-automation-docker/1.5.0-en`<br>
`# docker image build -t exastro/it-automation:tagname .`<br>
1. run container <br>
`# docker run --privileged --add-host=exastro-it-automation:127.0.0.1 -d -p 8080:80 -p 10443:443 --name exastro01 exastro/it-automation:tagname`<br>
Notes: Change the port number according to your environment.<br>
       If you want to change the installation settings, please follow “How to change installation settings” in below.<br>
1. Install Exastro ITAutomation<br>
`# docker exec -i -t exastro01  sh ita_builder_online.sh`<br>
# How to change installation settings<br>
If you want to change the installation settings, do not perform "4. Install Exastro IT Automation" and follow the procedure below.
1. `# docker exec -i -t exastro01 /bin/bash` <br>
1. `# vi ita_answers.txt`<br>
[notes:See the link manual(3.5 Configuration) for how to modify the answer file](https://exastro-suite.github.io/it-automation-docs/asset/Learn/ITA-online-install_en.pdf)<br>
1. `# sh ita_builder_online.sh`<br>

# Exastro ITAutomation Installation settings<br>
If you use this Dockerfile, the following "ita_answers.txt" will be set.<br>
<br>
**ita_answers.txt**<br>
#Select install mode. ("Install" or "Uninstall")<br>
#e.g) install_mode:Install<br>
install_mode:Install<br>

#Enter install directory.<br>
#e.g) ita_directory:/exastro<br>
ita_directory:/exastro<br>

#Select language. ("en_US" or "ja_JP")<br>
#e.g) ita_language:ja_JP<br>
ita_language:ja_JP()<br>

#Select Operation System. ("RHEL7" or "RHEL8")<br>
#e.g) ita_os:RHEL8<br>
ita_os:RHEL8<br>

#Enter the MariaDB root user's password<br>
#e.g) db_root_password:ita_root_passwordsample_root_password<br>
db_root_password:ita_root_password<br>

#Decide the database name, username, and password for ITA.<br>
#e.g) db_name:ita_dbsample_db_name<br>
db_name:ita_db<br>
#e.g) db_username:ita_db_usersample_db_username<br>
db_username:ita_db_user<br>
#e.g) db_password:ita_db_passwordsample_db_password<br>
db_password:ita_db_password<br>

#Select the target you need to install.<br>
