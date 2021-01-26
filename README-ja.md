
[English](README.md)| 日本語<br>
<br>
# Exastro ITAutomation docker <br>
このDockerfileは、Exastro ITAutomation（オールインワン）のインストール環境を提供します。<br>
注意: Exastro ITAutomationは、このdockerfileをビルドするだけではインストールされません。<br>
[インストール済みイメージはDocker-Hubからダウンロードしてください。](https://hub.docker.com/r/exastro/it-automation/)<br>
# How to build Exastro ITAutomation in a container
注意：ご使用の環境に応じてポート番号、言語やバージョンは変更してください。<br>
1. Dockerfileダウンロード<br>
`# git clone https://github.com/exastro-suite/it-automation-docker.git`<br>
1. 言語選択<br>
English ： `# cd it-automation-docker/X.X.X-en`<br>
Japanese ： `# cd it-automation-docker/X.X.X-ja`<br>
1. Dockerイメージビルド<br>
`# docker image build -t exastro/it-automation:X.X.X-ja .`<br>
1. コンテナ実行 <br>
`# docker run --privileged --add-host=exastro-it-automation:127.0.0.1 -d -p 8080:80 -p 10443:443 --name exastro01 exastro/it-automation:X.X.X-ja`<br>
   注意：インストール設定を変更する場合は、以下の「How to change installation settings」を実施して下さい。<br>
1. Exastro ITAutomationインストール<br>
v1.5.0<br>
`# docker exec -i -t exastro01  sh ita_builder_online.sh`<br>
v1.6.0~<br>
`# docker exec -i -t exastro01  sh ita_installer.sh`<br>
# How to change installation settings<br>
インストール時の設定を変更したい場合は、「5.Exastro ITAutomationインストール」を行わず、以下の手順で行ってください。
1. `# docker exec -i -t exastro01 /bin/bash` <br>
1. `# vi ita_answers.txt`<br>
[注意：ita_answers.txtの修正方法については、リンクのマニュアル（3.8 環境構築）を参照してください。](https://exastro-suite.github.io/it-automation-docs/asset/Learn_ja/ITA-online-install_ja.pdf)<br>
1. v1.5.0<br>
`# sh ita_builder_online.sh`<br>
v1.6.0~<br>
`# sh ita_installer.sh`<br>

# Exastro ITAutomation Installation settings<br>
このDockerfileを使用すると、以下の「ita_answers.txt」が設定されます。<br>
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
#yes : need<br>
#no  : no need<br>
ita_base:yes<br>
material:no<br>
createparam:yes<br>
hostgroup:yes<br>
ansible_driver:yes<br>
cobbler_driver:no<br>
openstack_driver:no<br>
terraform_driver:no<br>
