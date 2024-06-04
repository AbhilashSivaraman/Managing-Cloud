# Managing Cloud and Containerisation Dependencies

## Text editor to be utilised to create web pages within EC2 instance

```
nano index.html
```

## Server to be utilised for website hosting

- ubuntu
  
```
apache2
```
- Amazon Linux 2

```
httpd
```

## Providing ec2-user sudo permissions to run docker

```
sudo usermod -aG docker ec2-user
```

## Docker-Compose

- Installing Docker Compose
  
```
sudo curl -L "https://github.com/docker/compose/releases/download/v2.24.7/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

- Providing executable permission

```
sudo chmod +x /usr/local/bin/docker-compose
```

## Test Driven Development

- Junit
```
https://repo1.maven.org/maven2/junit/junit/4.13.2/junit-4.13.2.jar
```
- Hamcrest
  
```
https://repo1.maven.org/maven2/org/hamcrest/hamcrest-core/1.3/hamcrest-core-1.3.jar
```

- Compile

```
javac -cp .:junit-4.13.2.jar:hamcrest-core-1.3.jar src/filename.java test/filename.java
```

- Run
```
java -cp .:src:test:junit-4.13.2.jar:hamcrest-core-1.3.jar org.junit.runner.JUnitCore executablename
```