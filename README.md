## docker-registry
Private Docker registry with basic authentication and frontend UI

Update passwords file with your own credentials

## Updating the password.
  `.htpasswd -c passwords [username]`, command for updating password. 
  
  Alternately password can be generated online: http://www.htaccesstools.com/htpasswd-generator
  
## Starting the registry
 `docker-compose up -d --build` 
 
## Using the registry
  When using registry without ssl, configure `insecure-registries` options in docker daemon. Edit `/etc/docker/daemon.json` file and update following configurations. Restart the docker daemon
  ```
  {
    "insecure-registries" : ["myregistry.in:5000"]
  }
  ```
  
  Docker login: `docker login -u docker -p password myregistry.in:5000`
  
  Run these commands to pull a `busybox` image and upload it to your registry:
  ```
  docker pull busybox
  docker tag busybox myregistry.in:5000/busybox/busybox
  docker push myregistry.in:5000/busybox/busybox
  ```
 
 
## Registry UI options
  https://github.com/kwk/docker-registry-frontend/

