This project uses Postgresql to store keyclock data. We will interact with keyclock using admin portal.

Keyclock version used -  24.4.9

helm install my-keycloak bitnami/keycloak --version 24.4.9 -n keycloak --create-namespace -f helm/values.yaml
kubectl get pods -n keycloak
kubectl get svc -n keycloak -- to retrive the ports

Use username=admin and password=admin to login into keycloak

Create a new realme - test-realm -- for test authentication flow
Create a client and also include valid redirect urls for redirecting after authenication -- http://localhost:30080/
After creating a user assign it a role
Go to credentials and give that user a password -- test-password

Make the post request using the file in postman/. 
provide the username and password and credential to get access token
Go to 3rd (GET request) paste the access token to get user details

helm uninstall my-keycloak -n keycloak
