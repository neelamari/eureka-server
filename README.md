

# Kaiser Eureka Server

* Eureka Server Instance

### Building and Testing locally
```
PACKAGING   mvn package
```
```
RUNNING (local)    From root folder, java -jar target/kaiser-eureka-0.0.1-SNAPSHOT.jar 
```
```
VERIFY    Check http://localhost:8761 to verify if it runs correctly
```

### Deploying to Bluemix

## Deployment

### Steps to Deploy 

* set endpoint and login

```
bluemix api https://api.ng.bluemix.net
```

* login

```
  bluemix login -u "your userid"
```

* set orgs and spaces

```
  cf target -o "your organization"

  cf target -s "your space"
```

* deploying application.

  Modify the manifest.yml with the name you used for MongoDB Service

```
  cf push
```

```
Find URL:    Once deployed successfully, identify URL of applictaion 
```
```
VERIFY    Verify URL if Eureka Server is running correctly
```
###  Create User Defined Service 

```
CREATE User Defined Service    cf cups kaiser-service-registry -p '{"uri":"https://kaiser-eureka-untheological-tenorrhaphy.mybluemix.net"}'

Replace with appropriate URL
```


###  Verifying logs 

* Bluemix console may not show all logs during application startup. 

* Use the cf logs command from command line to verify logs 

```
  cf logs "app name" 
```
