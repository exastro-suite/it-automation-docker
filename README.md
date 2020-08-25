# Exastro ITAutomation-docker
This Dockerfile provides the Exastro ITAutomation installation environment (all-in-one).<br>
notes: Exastro ITAutomation is not installed just by building this dockerfile<br>
# How to Install Exastro ITAutomation in Container
1. Download the required version of Dockerfile<br>
`git clone it-automation-docker/XXXXX or wget XXXXXXXXXXXXXX`<br>
1. Build Docker Image<br>
`docker image build -t exastro/it-automatio .`<br>
1. run container <br>
`docker run --privileged -d -p 8080:80 -p 10443:443 --name exastro01 exastro/it-automation:latest`<br>
notes: Change the port number according to your environment.<br>
1. Install Exastro ITAutomation<br>
`docker exec -i -t exastro01  sh ita_builder_online.sh`<br>
# How to change installation settings<br>
If you want to change the installation settings, do not perform "4. Install Exastro IT Automation" and follow the procedure below.
1. `docker exec -i -t exastro01` 
1. `vi ita_answers.txt`
1. [See the link manual for how to modify the answer file](https://exastro-suite.github.io/it-automation-docs/asset/Learn/ITA-online-install_en.pdf)
