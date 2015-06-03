#Mac下安装配置eclipse

##eclipse javaEE最新版

##jdk7u79

##下载tomcat core zip BinaryDistributions
执行startup.sh安装

##安装tomcat插件
参考：[http://www.cnblogs.com/bukudekong/archive/2013/10/03/3350418.html](http://www.cnblogs.com/bukudekong/archive/2013/10/03/3350418.html)

##maven

###下载安装
地址：[http://maven.apache.org/download.cgi](http://maven.apache.org/download.cgi)

###复制以下配置内容到`/maven/conf/settings.xml`

    <settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
              xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
              xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0
                  http://maven.apache.org/xsd/settings-1.0.0.xsd">
    
    <localRepository>/Users/harx/Applications/maven_repository</localRepository>
    
    <!--非官方插件命令行运行配置-->
    <pluginGroups>
        <pluginGroup>org.mortbay.jetty</pluginGroup>      
    </pluginGroups>
    <servers>
        <server>
          <id>releases</id>
          <username>admin</username>
          <password>admin123</password>
        </server>
        <server>
          <id>snapshots</id>
          <username>admin</username>
          <password>admin123</password>
        </server>
        <server>
          <id>nexus</id>
          <username>admin</username>
          <password>admin123</password>
        </server>	
    </servers>
    
    <mirrors>
        <!--配置仓库镜像-->
        <mirror>
          <id>nexus</id>
          <mirrorOf>*</mirrorOf>
          <name>Human Readable Name for this Mirror.</name>
          <url>http://nexus.lagou.com/content/groups/public/</url>
        </mirror>
        
    </mirrors>
      
    <profiles>
        <!--配置仓库和插件仓库-->
        <profile>
          <id>nexus</id>
          <repositories>
                    <repository>
                        <id>central</id>
                        <name>central</name>
                        <url>http://central</url>
                        <releases>
                            <enabled>true</enabled>
                        </releases>
                        <snapshots>
                            <enabled>true</enabled>
                        </snapshots>
                    </repository>
                </repositories>
                
                <pluginRepositories>
                    <pluginRepository>
                        <id>central</id>
                        <name>central</name>
                        <url>http://central</url>
                        <releases>
                            <enabled>true</enabled>
                        </releases>
                        <snapshots>
                            <enabled>true</enabled>
                        </snapshots>
                    </pluginRepository>
                </pluginRepositories>
        </profile>
        <profile>  
            <id>jdk-1.6</id>  
            <activation>  
                <activeByDefault>true</activeByDefault>  
                <jdk>1.6</jdk>  
            </activation>  
            <properties>  
                <maven.compiler.source>1.6</maven.compiler.source>  
                <maven.compiler.target>1.6</maven.compiler.target>  
                <maven.compiler.compilerVersion>1.6</maven.compiler.compilerVersion>  
            </properties>  
        </profile> 
      </profiles> 
    
      <!--激活profile-->
      <activeProfiles>
        <activeProfile>nexus</activeProfile>
      </activeProfiles>
      
    </settings>

##安装maven插件 m2e（mavenToEclipse）
eclipse商店安装即可

##配置host 
10.7.0.182 nexus.lagou.com

##tomcat sever.xml文件配置
修改端口为8080。

修改文件`/tomcat/conf/server.xml`,添加需启动的主机配置。

    <!--      <Host name="hr.lagou.com" appBase="_" unpackWARs="true" xmlValidation="false" xmlNamespaceAware="false">-->
    <!--          <Alias>hr.lagou.com</Alias>-->
    <!--          <Context path="/" docBase="D:\SVN\lagou_resume_manager\branches\lagou_plus\src\main\webapp" debug="0" reloadable="true"/>-->
    <!--      </Host>-->
    
    <Host name="www.lagou.com" appBase="_" unpackWARs="true" xmlValidation="false" xmlNamespaceAware="false">
      <Alias>www.lagou.com</Alias>
      <Context path="/" docBase="/Users/harx/SVN/lagou/branches/lagou-new-search/src/main/webapp" debug="0" reloadable="true"/>
    </Host>

##端口映射
参考：[http://openwares.net/linux/mac_tomcat_port_80.html](http://openwares.net/linux/mac_tomcat_port_80.html)


添加`rdr on lo0 inet proto tcp from any to 127.0.0.1 port 80 -> 127.0.0.1 port 8080` 到文件`/etc/pf.conf`，最终如下：

    scrub-anchor "com.apple/*"
    nat-anchor "com.apple/*"
    rdr-anchor "com.apple/*"
    rdr on lo0 inet proto tcp from any to 127.0.0.1 port 80 -> 127.0.0.1 port 8080
    dummynet-anchor "com.apple/*"
    anchor "com.apple/*"
    load anchor "com.apple" from "/etc/pf.anchors/com.apple"

pf默认非自启动，所以需手动启动，执行命令`pfctl -ef /etc/pf.conf`。可能需要管理员权限。
