Related Repositories
=======================
<table>
  <tr>
    <td colspan=2 align=center>
      플랫폼
    </td>
    <td colspan=2 align=center>
      <a href="https://github.com/PaaS-TA/portal-deployment/commits?author=okpc579">어플리케이션 플랫폼</a>
    </td>
    <td colspan=2 align=center>
      <a href="https://github.com/PaaS-TA/portal-deployment/commits?author=okpc579">컨테이너 플랫폼</a>
    </td>
  </tr>
  <tr>
    <td colspan=2 align=center>
      포털
    </td>
    <td colspan=2 align=center>
      <a href="https://github.com/PaaS-TA/portal-deployment/commits?author=okpc579">AP 포털</a>
    </td>
    <td colspan=2 align=center>
      <a href="https://github.com/PaaS-TA/portal-deployment/commits?author=okpc579">CP 포털</a>
    </td>
  </tr>
  <tr align=center>
    <td rowspan=4>모니터링</td>
    <td rowspan=2>릴리즈<br>/빌드팩</td>
    <td><a href="https://github.com/PaaS-TA/PaaS-TA-Monitoring-Release">Monitoring Release</a></td>
    <td><a href="https://github.com/PaaS-TA/paas-ta-monitoring-logsearch-release">Logsearch Release</a></td>
    <td>🚩<a href="https://github.com/PaaS-TA/paas-ta-monitoring-influxdb-release">InfluxDB Release</a></td>
    <td><a href="https://github.com/PaaS-TA/paas-ta-monitoring-redis-release">Redis Release</a></td>
  </tr>
  <tr align=center>
    <td><a href="https://github.com/PaaS-TA/PAAS-TA-PINPOINT-MONITORING-RELEASE">Pinpoint Release</td>
    <td><a href="https://github.com/PaaS-TA/PAAS-TA-PINPOINT-MONITORING-BUILDPACK">Pinpoint Buildpack</td>
    <td></td>
    <td></td>
  </tr>
  <tr align=center>
    <td>배포</td>
    <td colspan=4><a href="https://github.com/PaaS-TA/monitoring-deployment">Monitoring Deployment</td>
  </tr>
  <tr align=center>
    <td>가이드<br>/소스 코드</td>
    <td colspan=4><a href="https://github.com/PaaS-TA/PaaS-TA-Monitoring">PaaS-TA-Monitoring</a></td>
  </tr>
  </tr>
  <tr align=center>
    <td rowspan=4 colspan=2>
      서비스
    </td>
    <td>
      <a href="https://github.com/PaaS-TA/portal-deployment/commits?author=okpc579">Cubrid</a>
    </td>
    <td>
      <a href="https://github.com/PaaS-TA/portal-deployment/commits?author=okpc579">Gateway</a>
    </td>
    <td>
      <a href="https://github.com/PaaS-TA/portal-deployment/commits?author=okpc579">GlusterFS</a>
    </td>
    <td>
      <a href="https://github.com/PaaS-TA/portal-deployment/commits?author=okpc579">Lifecycle</a>
    </td>
  </tr>
  <tr align=center>
    <td>
      <a href="https://github.com/PaaS-TA/portal-deployment/commits?author=okpc579">Logging</a>
    </td>
    <td>
      <a href="https://github.com/PaaS-TA/portal-deployment/commits?author=okpc579">MongoDB</a>
    </td>
    <td>
      <a href="https://github.com/PaaS-TA/portal-deployment/commits?author=okpc579">MySQL</a>
    </td>
    <td>
      <a href="https://github.com/PaaS-TA/portal-deployment/commits?author=okpc579">Pinpoint APM</a>
    </td>
  </tr>
  <tr align=center>
    <td>
      <a href="https://github.com/PaaS-TA/portal-deployment/commits?author=okpc579">Pipeline</a>
    </td>
    <td align=center>
      <a href="https://github.com/PaaS-TA/portal-deployment/commits?author=okpc579">RabbitMQ</a>
    </td>
    <td>
      <a href="https://github.com/PaaS-TA/portal-deployment/commits?author=okpc579">Redis</a>
    </td>
    <td>
      <a href="https://github.com/PaaS-TA/portal-deployment/commits?author=okpc579">형상관리</a>
    </td>
  </tr>
  <tr align=center>
    <td>
      <a href="https://github.com/PaaS-TA/portal-deployment/commits?author=okpc579">WEB-IDE</a>
    </td>
    <td>
    </td>
    <td>
    </td>
    <td>
    </td>
  </tr>
</table>
<i>*🚩─ You are here.</i>

## paas-ta-monitoring-influxdb-release

### Create PaaS-TA Monitoring InfluxDB Release   
  - Download the latest PaaS-TA Monitoring InfluxDB Release    
    ```   
    $ git clone --recursive https://github.com/PaaS-TA/paas-ta-monitoring-influxdb-release.git    
    $ cd paas-ta-monitoring-influxdb-release   
    ```   
  - Download & Copy "source files" into the src directory    
    ```   
    ## download source files    
    $ wget -O src.zip https://nextcloud.paas-ta.org/index.php/s/H8PZ6QSSfqEQT7Y/download
    
    ## unzip download source files    
    $ unzip src.zip  (chronograf, golang, influxdb)  

    ## final src directory
    src
      ├── bootstrapper
      │   └── src
      │       ├── bootstrapper
      │       └── github.com (influxdata/influxdb@bc8ec43 - 1.8.4)
      ├── chronograf
      │   └── chronograf-1.8.9.1_linux_amd64.tar.gz
      ├── golang
      │   └── go1.9.2.linux-amd64.tar.gz
      ├── influxdb
      │   └── influxdb-1.8.4_linux_amd64.tar.gz
      └── pidutils.sh

    
    ```  
  - Create PaaS-TA Monitoring Inflxudb Release   
    ```   
    ## <VERSION> :: release version (e.g. 1.8.4)   
    ## <RELEASE_TARBALL_PATH> :: release file path (e.g. /home/ubuntu/workspace/monitoring-influxdb-release-<VERSION>.tgz)    
    $ bosh -e <bosh_name> create-release --name=influxdb --sha2 --version=<VERSION> --tarball=<RELEASE_TARBALL_PATH> --force   
    ```    
### Deployment
- https://github.com/PaaS-TA/monitoring-deployment   

