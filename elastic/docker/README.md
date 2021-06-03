docker run -d \
--name=filebeat \
--restart unless-stopped \
--user=root \
--network="host" \
--volume="$(pwd)/elastic/docker/filebeat.docker.yml:/usr/share/filebeat/filebeat.yml:ro" \
--volume="/var/log/splunk/:/var/log/splunk/:ro" \
docker.elastic.co/beats/filebeat:7.12.0 filebeat -e -strict.perms=false
