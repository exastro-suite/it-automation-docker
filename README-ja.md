
[English](README.md)| 日本語<br>
<br>
# Exastro ITAutomation docker <br>
このDockerfileは、Exastro ITAutomation（オールインワン）のインストール環境を提供します。<br>
注釈: Exastro ITAutomationは、このdockerfileをビルドするだけではインストールされません。<br>
[Docker-Hubからインストールイメージをダウンロードしてください。](https://hub.docker.com/r/exastro/it-automation/).<br>
# How to build Exastro ITAutomation in a container
1. Dockerfileをダウンロードして下さい。<br>
`# git clone https://github.com/exastro-suite/it-automation-docker.git`<br>
1. 言語を選択しDockerイメージを作成してください。<br>
English ： `# cd it-automation-docker/1.5.0-en`<br>
Japanese ： `# cd it-automation-docker/1.5.0-en`<br>
`# docker image build -t exastro/it-automation:tagname .`<br>
1. コンテナを実行して下さい。 <br>
`# docker run --privileged --add-host=exastro-it-automation:127.0.0.1 -d -p 8080:80 -p 10443:443 --name exastro01 exastro/it-automation:tagname`<br>
注釈：ご使用の環境に応じてポート番号を変更してください。<br>
    インストール時の設定を変更する場合は、以下の「インストール設定の変更方法」を実施して下さい。<br>
1. Exastro ITAutomationをインストールして下さい。<br>
`# docker exec -i -t exastro01  sh ita_builder_online.sh`<br>
# How to change installation settings<br>
インストール時の設定を変更したい場合は、「4。Exastro IT Automationのインストール」を行わず、以下の手順で行ってください。
1. `# docker exec -i -t exastro01 /bin/bash` <br>
1. `# vi ita_answers.txt`<br>
[注釈：ita_answers.txtの修正方法については、リンクのマニュアル（3.8 環境構築）を参照してください。](https://exastro-suite.github.io/it-automation-docs/asset/Learn_ja/ITA-online-install_ja.pdf)<br>
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
