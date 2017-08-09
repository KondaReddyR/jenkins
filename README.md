```
echo "admin" | docker secret create jenkins-pass -
echo "admin" | docker secret create jenkins-user -

docker network create --driver overlay proxy

docker stack deploy -c proxy.yml proxy
docker stack deploy -c jenkins.yml jenkins

sleep 5
docker service ps jenkins_jenkins-master
docker service ps proxy_visualizer proxy_proxy proxy_swarm-listener```

