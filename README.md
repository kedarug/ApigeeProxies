# ApigeeProxies

Demo 1 - kg-xpo-api proxy.

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

