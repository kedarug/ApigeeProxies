# ApigeeProxies

**Demo 1 - kg-xpo-api proxy.**

Using XPO Auth for Authorization & Authentication. 

* Step 1 - 
Created a MVC Client which generates the access token using Auth XPO. 
Authority - https://login-sandbox.authxpo.com
custom scope added is xpo-tran-google-api. 
Show the JWT Decoded values ( jwt.io)

* Step 2 - 
Set up VerifyJWTToken policy. Here it only does authentication.  
VerifyJWTToken generated outside Apigee using the public key store. 
We use the auth xpo public key. 

* Step 3 - 
Based on the endpoint, check the scope using regular expression and allow access to the resource.
If not matching, then show unauthorised error. 

Note that this supports only application level scope.These scopes are maintained in the apigee layer. 
User level authorization is not covered with this. 

**Demo 2 - proxies - kg-oauth & kg-oauth-product.**
oauth with scopes. 

We will be using the default apigee generated oauth. This is implmented in kg-oauth. 
then assign some scopes to the product at the apigee level.
![image](https://user-images.githubusercontent.com/96166550/155371230-7bd8b4f2-4e3d-48a9-a39a-fd565d13dd87.png)


scope check in the oauth validation policy. 
Then verify if scope is correct, if not it will error with invalid scope.  

Next steps 

1) Dell boomi apis - brokerage / otm. 
2) explore ci/cd options.
3) keep the existing keys from boomi to apigee.
4) microservices - refrence architecture. 
5) bff pattern. integration services layer. 
6) communication of services through gRPC. 
7) Integration with git for better traceability 

postman collection : 

