# jenkins-sonarqube-sonar scanner
install sonarQube And jenkins on server

```
docker-compose up -d
```

If you want to install sonar-scanner on server or client, you can install it in this way

First, type these commands

```
apt-get update
apt-get install unzip wget nodejs
cd /opt/
wget https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-4.7.0.2747-linux.zip
unzip sonar-scanner-cli-4.7.0.2747-linux.zip
mv sonar-scanner-cli-4.7.0.2747-linux/ sonar-scanner
```
Then activate these commands in this address
```
nano /opt/sonar-scanner/conf/sonar-scanner.properties
```
and active these command

```
sonar.host.url=http://localhost:9000
sonar.sourceEncoding=UTF-8
```

and add these command to this adress
```
nano /etc/profile.d/sonar-scanner.sh

#/bin/bash
export PATH="$PATH:/opt/sonar-scanner/bin"
```

and run these command
```
source /etc/profile.d/sonar-scanner.sh
env | grep PATH
```

and the end 
```
sonar-scanner -v
```

# References
* [SonarScanner](https://docs.sonarqube.org/latest/analysis/scan/sonarscanner)
* [SonarQube](https://hub.docker.com/_/sonarqube)
* [jenkins](https://hub.docker.com/r/jenkins/jenkins)

