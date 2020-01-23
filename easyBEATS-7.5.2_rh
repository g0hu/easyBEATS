#!/bin/bash

echo "$(tput setaf 6) ---- Setting Timezone to America/Chicago ----$(tput sgr0)"
timedatectl set-timezone America/Chicago
echo $(date)

echo "$(tput setaf 6) ---- Installing Filebeat ----$(tput sgr0)"
curl -L -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-7.5.2-x86_64.rpm
rpm -vi filebeat-7.5.2-x86_64.rpm
filebeat modules enable system
echo "$(tput setaf 6) ---- Starting Filebeat ----$(tput sgr0)"
systemctl enable filebeat


echo "$(tput setaf 6) ---- Installing Metricbeat ----$(tput sgr0)"
curl -L -O https://artifacts.elastic.co/downloads/beats/metricbeat/metricbeat-7.5.2-x86_64.rpm
rpm -i metricbeat-7.5.2-x86_64.rpm
metricbeat modules enable system
echo "$(tput setaf 6) ---- Starting Metricbeat ----$(tput sgr0)"
systemctl enable metricbeat


echo "$(tput setaf 6) ---- Installing Packetbeat ----$(tput sgr0)"
apt-get install libpcap0.8
curl -L -O https://artifacts.elastic.co/downloads/beats/packetbeat/packetbeat-7.5.2-x86_64.rpm
rpm -i packetbeat-7.5.2-x86_64.rpm
echo "$(tput setaf 6) ---- Starting Packetbeat ----$(tput sgr0)"
systemctl enable packetbeat


echo "$(tput setaf 6) ---- Installing Auditbeat ----$(tput sgr0)"
curl -L -O https://artifacts.elastic.co/downloads/beats/auditbeat/auditbeat-7.5.2-x86_64.rpm
rpm -i auditbeat-7.5.2-x86_64.rpm
echo "$(tput setaf 6) ---- Starting Auditbeat ----$(tput sgr0)"
systemctl enable auditbeat
 
/bin/systemctl daemon-reload

rm filebeat*
rm metricbeat*
rm packetbeat*
