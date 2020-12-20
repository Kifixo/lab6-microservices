## Microservices handling report

### Microservice `account (2222)` and `web` are running and registered

Here we can see accounts service running on port 2222
![Account logs](screenshots/1_account_service.png)

... and Web service running on port 3333
![Web logs](screenshots/1_web_service.png)


### Registration service with two microservices registered

Here we can see Eureka server (registration) running correctly on port 1111

![Registration logs](screenshots/2_register_service.png)

When this service is running, we can access the dashboard by using our preferred Web Browser: `localhost:1111`

![Registration dashboard](screenshots/2_dashboard.png)


### Second account microservice running on port 4444

Here we can see a new account microservice running on port 4444 and correctly registered
![Second account service](screenshots/3_account_service.png)

... and we can see here the new service on dashboard
![Dashboard](screenshots/3_dashboard.png)


### What happens when the microservice running on port 2222 is killed? Can the web service provide information about the accounts and why?

When we kill the `account 2222` microservice, we will get an error if we try to access this service via web.

![500 Error](screenshots/4_500_dashboard.png)

Nevertheless, Eureka will take notice of the new service, and will re-register that microservice running on port 4444, so the service is reestablished successfully.

![500 Error](screenshots/4_dashboard.png)