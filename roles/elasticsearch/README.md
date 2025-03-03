# elasticsearch

Play configures ELK stack using docker & is available without HTTPS. Configure container variables in `tasks/SERVICE.yml` files, environment variables for the services & Java can also be configured here.

The following are manual steps required during setup.

## elastic

After creating elasticsearch container SSH into the running host and generate a new password for user `elastic` using command:

```bash
docker exec -it elasticsearch /usr/share/elasticsearch/bin/elasticsearch-reset-password -u elastic
```

## kibana

Create a password for `kibana_system` user:

```bash
export ELASTIC_PASSWORD=
export KIBANA_PASSWORD=
curl -s -X POST -u "elastic:${ELASTIC_PASSWORD}" -H "Content-Type: application/json" http://elasticsearch:9200/_security/user/kibana_system/_password -d "{\"password\":\"${KIBANA_PASSWORD}\"}" | grep -q "^{}";
```
