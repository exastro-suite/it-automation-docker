# it-automation-docker
## QuickStart with Exastro and Docker
Here how to get an all-in-one server running in a Docker container: <br>

Step - 1 : Run Exastro Server docker container<br>
Command example:<br>
`docker run --privileged -d -p 8080:80 -p 10443:443 --name exastro01 exastro/it-automation:1.5.0-en `<br>
Attention : Change the port number according to your environment.<br>
<br>
step - 2 : Web Console to start Exastro IT Automation<br>
Next,visit http://#Docker_Host_IP#:8080 or https://#Docker-Host-IP#:10443 <br>
<br>
step - 3: Exastro  IT Automation login<br>
When the IT Automation login screen appears, enter the given login ID and initial password and then click the Login button.<br>
- Login ID: administrator<br>
- Initial password: password<br>

If you have logged in for the first time after the installation, you will be prompted to change the password.<br>
Change the initial password.<br>

step - 4: Exastro IT Automation Quick start<br>
[Get Started with Exastro IT Automation with Quick Start](https://exastro-suite.github.io/it-automation-docs/learn.html)<br>

## What's in this image?
IT Automation All-in-one server installed.<br>
Since this container is a beta version, some functions may not be available<br>

Installation settings<br>
- Base Image :CentOS8<br>
- language:<br>
  English (image name : X.X.X-en)<br>
   Japanese (imagename : X.X.X-ja)<br>
- DB settings
  db_name : ita_db<br>
  db_root_password : ita_root_password<br>
  db_username : ita_db_user<br>
  db_password : ita_db_password<br>
