docker login
docker tag node-api:v1  hocptit/node-1:v1
docker tag local-image:tagname new-repo:tagname
docker push new-repo:tagname
docker push hocptit/node-1:v1
docker pull hocptit/node-1:v1