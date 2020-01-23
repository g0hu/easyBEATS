# easyBEATS

easyBEATS is a project started to make the installation of Beats packages faster and easier for Linux

## How To Use

### Debian (Ubuntu)

easyBEATS-7.5.2_deb will install Filebeat, Metricbeat, Packetbeat, and Auditbeat.  It *Does Not* use apt-get and the script puts each of the beats packages on apt-get hold to prevent accidental upgrading.  If you want to upgrade you must remove the hold.  I do this to avoid accidentally upgrading my beats clients to a newer version that my ELK stack.

1. Download easyBEATS-7.5.2_deb 
2. Copy to your debian system
3. Make it executable and run it

```
sudo chmod +x easyBEATS-7.5.2_deb
./easyBEATS-7.5.2_deb
```

4. After the sccript is finished, configure each of the Beats shippers
    - /etc/filebeat/filebeat.yml
    - /etc/metricbeat/metricbeat.yml
    - /etc/packetbeat/packetbeat.yml
    - /etc/auditbeat/auditbeat.yml
5. The script has already prepared the system to launch the service at boot / re-boot.  You just need to start the service after you configure

```
sudo systemctl start filebeat metricbeat packetbeat auditbeat
```

7. Run the setup command for each to finalize

```
filebeat setup -e
```

Repeat the command and change the name of filebeat to each of the other beats

### Red Hat Linux (CentOS/Fedora)

easyBEATS-7.5.2_rh will install Filebeat, Metricbeat, Packetbeat, and Auditbeat.  It uses yum to get the packages and install.

1. Download easyBEATS-7.5.2_rh 
2. Copy to your debian system
3. Make it executable and run it

```
sudo chmod +x easyBEATS-7.5.2_rh
./easyBEATS-7.5.2_rh
```

4. After the sccript is finished, configure each of the Beats shippers
    - /etc/filebeat/filebeat.yml
    - /etc/metricbeat/metricbeat.yml
    - /etc/packetbeat/packetbeat.yml
    - /etc/auditbeat/auditbeat.yml
5. The script has already prepared the system to launch the service at boot / re-boot.  You just need to start the service after you configure

```
sudo systemctl start filebeat metricbeat packetbeat auditbeat
```

7. Run the setup command for each to finalize

```
filebeat setup -e
```

Repeat the command and change the name of filebeat to each of the other beats
