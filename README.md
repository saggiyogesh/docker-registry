## docker-registry
Private Docker registry with basic authentication and frontend UI

Update passwords file with your own credentials

## Updating the password.
  `.htpasswd -c passwords [username]`, command for updating password. 
  
  Alternately password can be generated online: http://www.htaccesstools.com/htpasswd-generator
  
## Starting the registry
 `docker-compose up -d --build` 

