# open folder with docker-compose.yml
cd kafka

docker-compose up -d
#check that containers up and running 
docker ps
#check the logs
docker logs kafka_zookeeper_1 --tail 99 --follow
^C
docker logs kafka_kafka_1 --tail 99 --follow
^C
# end of story