# Description
this is collected maven artifacts that required to build jasper reports server community edition 8.1.1 [jrs-ce8.1.1]
the source for jasper reports server can be found in the following repo https://github.com/aryabisma/jasperreports-server-ce-8.1.1

# Requirements
- java jdk / openjdk 8
- maven (can use latest version)

# Build step 
(currently in Windows as of my local setup)
1. create a bat file that sets the JAVA_HOME, MAVENT_HOME, and MAVEN_OPTS
   example:
```@echo off
set JAVA_HOME=C:\sonata.os\home\Research\jasperreports-server-ce-8-master\openlogic-openjdk-8u442-b06-windows-x64
set MAVEN_HOME=C:\sonata.os\opt\apache-maven-3.9.10
set MAVEN_OPTS=-Djavax.net.ssl.trustStore=%JAVA_HOME%\jre\lib\security\cacerts -Djavax.net.ssl.trustStorePassword=changeit -Djavax.net.ssl.trustStoreType=JKS

set PATH=%MAVEN_HOME%\bin;%JAVA_HOME%\bin;%MAVEN_OPTS%;%PATH%

echo JAVA_HOME=%JAVA_HOME%
echo MAVEN_HOME=%MAVEN_HOME%
echo MAVEN_OPTS=%MAVEN_OPTS%
ECHO FULL_PATH=%PATH%

REM Open PowerShell with execution policy bypass in the process scope
start powershell -NoExit -Command "& Set-ExecutionPolicy Bypass -Scope Process;"
```

3. add the following config in your maven setting.xml to use local maven repository instead of pulling from internet
   ><localRepository>C:\sonata.os\opt\maven_local_repo</localRepository>
4. compile with maven
   >mvn install -X


I am open for any improvement or updates for this repository or build command
