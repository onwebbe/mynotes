ignore https certificate
process.env['NODE_TLS_REJECT_UNAUTHORIZED'] = 0;




mac jenkinsci run Jenkinsfile docker failed with permission error
do as below

docker run \       
  --name jenkins_ci \
  -u root \
  -p 9999:8080 \
  -v /data/jenkinsdata/sciblueocean:/var/jenkins_home \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v "$HOME":/home \
  -v /usr/local/bin/docker:/usr/bin/docker \
  jenkinsci/blueocean


mongodb vscode client "Azure Cosmos DB"


nginx
docker run -p 5001:80 --name mynginx11 -v /data/docker-data/nginx/www:/www -v /data/docker-data/nginx/confg/conf.d:/etc/nginx/conf.d -v /data/docker-data/nginx/logs:/wwwlogs -d nginx
