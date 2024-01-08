# Application platform monitoring-influxdb-release Guide

### Create Application Platform monitoring-influxdb-release
  - Download the latest Applicatio Platform Monitoring InfluxDB Release
    ```   
    $ git clone https://github.com/K-PaaS/monitoring-influxdb-release.git
    $ cd monitoring-influxdb-release   
    ```   
  - Download & Copy "source files" into the src directory    
    ```   
    ## download source files    
    $ wget -O src.zip https://nextcloud.k-paas.org/index.php/s/MNbSc6KceE9wwPT/download
    
    ## unzip download source files    
    $ unzip src.zip 

    ## final src directory
    src
      ├── bootstrapper
      │   └── src
      │        └── bootstrapper
      ├── chronograf
      │   └── chronograf-1.9.4_linux_amd64.tar.gz
      ├── golang
      │   └── go1.17.13.linux-amd64.tar.gz
      ├── influxdb
      │   └── influxdb-1.8.10_linux_amd64.tar.gz
      └── pidutils.sh

    
    ```  
  - Create Application Platform monitoring-influxdb-release
    ```   
    ## <VERSION> :: release version (e.g. 5.8.1)   
    ## <RELEASE_TARBALL_PATH> :: release file path (e.g. /home/ubuntu/workspace/monitoring-influxdb-release-<VERSION>.tgz)    
    $ bosh -e <bosh_name> create-release --name=influxdb --sha2 --version=<VERSION> --tarball=<RELEASE_TARBALL_PATH> --force   
    ```    
### Deployment
- https://github.com/K-PaaS/service-deployment
