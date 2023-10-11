## Related Repositories

<table>
  <tr>
    <td colspan=2 align=center>플랫폼</td>
    <td colspan=2 align=center><a href="https://github.com/K-PaaS/paasta-deployment">어플리케이션 플랫폼</a></td>
    <td colspan=2 align=center><a href="https://github.com/K-PaaS/container-platform">컨테이너 플랫폼</a></td>
  </tr>
  <tr>
    <td colspan=2 rowspan=2 align=center>포털</td>
    <td colspan=2 align=center><a href="https://github.com/K-PaaS/portal-deployment">AP 포털</a></td>
    <td colspan=2 align=center><a href="https://github.com/K-PaaS/cp-portal-release">CP 포털</a></td>
  </tr>
  <tr align=center>
    <td colspan=4><a href="https://github.com/K-PaaS/PaaS-TA-Monitoring">모니터링 대시보드</a></td>
  </tr>
  <tr align=center>
    <td rowspan=2 colspan=2><a href="https://github.com/K-PaaS/monitoring-deployment">모니터링</a></td>
    <td><a href="https://github.com/K-PaaS/PaaS-TA-Monitoring-Release">Monitoring</a></td>
    <td><a href="https://github.com/K-PaaS/paas-ta-monitoring-logsearch-release">Logsearch</a></td>
    <td><a href="https://github.com/K-PaaS/monitoring-influxdb-release">🚩 InfluxDB</a></td>
    <td><a href="https://github.com/K-PaaS/paas-ta-monitoring-redis-release">Redis</a></td>
  </tr>
  <tr align=center>
    <td><a href="https://github.com/K-PaaS/PAAS-TA-PINPOINT-MONITORING-RELEASE">Pinpoint</td>
    <td><a href="https://github.com/K-PaaS/PAAS-TA-PINPOINT-MONITORING-BUILDPACK">Pinpoint Buildpack</td>
    <td></td>
    <td></td>
  </tr>
  </tr>
  <tr align=center>
    <td rowspan=4 colspan=2><a href="https://github.com/K-PaaS/service-deployment">AP 서비스</a></td>
    <td><a href="https://github.com/K-PaaS/PAAS-TA-CUBRID-RELEASE">Cubrid</a></td>
    <td><a href="https://github.com/K-PaaS/ap-api-gateway-release">Gateway</a></td>
    <td><a href="https://github.com/K-PaaS/ap-glusterfs-release">GlusterFS</a></td>
    <td><a href="https://github.com/K-PaaS/ap-app-lifecycle-release">Lifecycle</a></td>
  </tr>
  <tr align=center>
    <td><a href="https://github.com/K-PaaS/PAAS-TA-LOGGING-SERVICE-RELEASE">Logging</a></td>
    <td><a href="https://github.com/K-PaaS/ap-mongodb-shard-release">MongoDB</a></td>
    <td><a href="https://github.com/K-PaaS/ap-mysql-release">MySQL</a></td>
    <td><a href="https://github.com/K-PaaS/ap-pinpoint-release">Pinpoint APM</a></td>
  </tr>
  <tr align=center>
    <td><a href="https://github.com/K-PaaS/ap-pipeline-release">Pipeline</a></td>
    <td align=center><a href="https://github.com/K-PaaS/ap-rabbitmq-release">RabbitMQ</a></td>
    <td><a href="https://github.com/K-PaaS/ap-on-demand-redis-release">Redis</a></td>
    <td><a href="https://github.com/K-PaaS/ap-source-control-release">Source Control</a></td>
  </tr>
  <tr align=center>
    <td><a href="https://github.com/K-PaaS/ap-web-ide-release">WEB-IDE</a></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr align=center>
    <td rowspan=1 colspan=2><a href="https://github.com/K-PaaS/cp-deployment">CP 서비스</a></td>
    <td><a href="https://github.com/K-PaaS/container-platform-pipeline-release">Pipeline</a></td>
    <td><a href="https://github.com/K-PaaS/container-platform-source-control-release">Source Control</a></td>
    <td></td>
    <td></td>
  </tr>
</table>
<i>🚩 You are here.</i>

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
