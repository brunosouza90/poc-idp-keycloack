# poc-idp-keycloack
API protection Example, with a KeyCloack Realm and OpenID 

Step 1 - Up the Keycloack application with docker 

docker run --name keycloak -p 8080:8080 -e KEYCLOAK_USER=admin -e KEYCLOAK_PASSWORD=admin quay.io/keycloak/keycloak:14.0.0

KEYCLOAK_USER=admin e KEYCLOAK_PASSWORD=admin
Use -> http://localhost:8080 

------

Step 2 - For this example, in the Keay cloack landing page, create a Realm "poc-iam" and after create the client "poc-api-protection"

Client config - Access type -> Confidential
                Services Accounts Enable -> ON
                Authorization Enable -> ON
                Valid Redirect URLs -> localhost:8090

------
                
Step 3 - Up the SpringBoot service in this repository

------
Step 4 - Get the acces token, (use Postman for that) in -> http://localhost:8080/auth/realms/poc-iam/protocol/openid-connect/token

------

Step 5 - Add the Authorization header with a token on the step 4, call the API -> http://localhost:8090/security


