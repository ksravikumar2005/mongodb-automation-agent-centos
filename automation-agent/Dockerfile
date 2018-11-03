FROM centos:latest
RUN yum -y update
RUN rpm -ivh https://cloud.mongodb.com/download/agent/automation/mongodb-mms-automation-agent-manager-latest.x86_64.rhel7.rpm
RUN yum clean all
RUN groupadd mongodb
RUN useradd -d /home/mongodb -ms /bin/bash -g mongodb -G mongodb -p mongodb mongodb
VOLUME /var/lib/mongodb-mms-automation
VOLUME /data
RUN chown -R mongodb:mongodb /data
EXPOSE 27000
USER mongodb
ENTRYPOINT ["/opt/mongodb-mms-automation/bin/mongodb-mms-automation-agent"]
