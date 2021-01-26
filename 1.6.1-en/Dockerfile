FROM centos:8
WORKDIR /etc
RUN dnf -y upgrade
RUN dnf -y install sudo crontabs wget openssh-server openssh-clients yum-utils diffutils
RUN sed -i -e 's/LANG="en_US.UTF-8"/LANG="C.utf-8"/g' locale.conf
WORKDIR /etc/yum.repos.d
RUN sed -i -e "s/enabled=0/enabled=1/g" CentOS-Linux-PowerTools.repo
WORKDIR /root
RUN wget -P /root https://github.com/exastro-suite/it-automation/archive/v1.6.1.tar.gz
RUN tar zxf /root/v1.6.1.tar.gz
WORKDIR /root/it-automation-1.6.1/ita_install_package/install_scripts/
RUN sed -i -e "s/linux_os:/linux_os:CentOS8/g" ita_answers.txt \
&& sed -i -e "s/ita_directory:/ita_directory:\/exastro/g" ita_answers.txt \
&& sed -i -e "s/ita_os:RHEL7/ita_os:RHEL8/g" ita_answers.txt \
&& sed -i -e "s/db_root_password:/db_root_password:ita_root_password/g" ita_answers.txt \
&& sed -i -e "s/db_name:/db_name:ita_db/g" ita_answers.txt \
&& sed -i -e "s/db_username:/db_username:ita_db_user/g" ita_answers.txt \
&& sed -i -e "s/db_password:/db_password:ita_db_password/g" ita_answers.txt
CMD [ "/sbin/init" ]
