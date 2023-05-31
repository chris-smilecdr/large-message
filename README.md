there is admin-node/createImage.sh and fhir-node/createImage.sh scripts to 
build docker images. This will set the properties need to replicate the issue

Create following Networks:

```
docker network create -d bridge databases
docker network create -d bridge jms
```

start Postgres
```
docker compose -f docker-compose-postgres.yml up -d
```

When starting up Postgres, create the following databases:
* clustermgr
* fhir_repo


start kafka
```
docker compose -f docker-compose-kafka.yml up -d
```

start smilecdr (admin and fhir nodes)
```
docker compose -f admin-node/docker-compose.yml up -d
docker compose -f fhir-node/docker-compose.yml up -d
```

