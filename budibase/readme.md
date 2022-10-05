# Budibase (Low Code Platform)

**Low code platform** | https://budibase.com/

## Setup

### .env File
Create `.env` file using the following template. Fill in / update the required values.
```
DOCKER_MY_NETWORK=proxy_net

# Use the main port in the builder for your self hosting URL, e.g. localhost:10000
MAIN_PORT=10000

# This section contains all secrets pertaining to the system
# These should be updated
JWT_SECRET=testsecret
MINIO_ACCESS_KEY=budibase
MINIO_SECRET_KEY=budibase
COUCH_DB_PASSWORD=budibase
COUCH_DB_USER=budibase
REDIS_PASSWORD=budibase
INTERNAL_API_KEY=budibase

# This section contains variables that do not need to be altered under normal circumstances
APP_PORT=4002
WORKER_PORT=4003
MINIO_PORT=4004
COUCH_DB_PORT=4005
REDIS_PORT=6379
WATCHTOWER_PORT=6161
BUDIBASE_ENVIRONMENT=PRODUCTION

# An admin user can be automatically created initially if these are set
BB_ADMIN_USER_EMAIL=email@domain.tld
BB_ADMIN_USER_PASSWORD=budibase

# A path that is watched for plugin bundles. Any bundles found are imported automatically/
PLUGINS_DIR=
```

### Start Containers

```shell
docker compose up -d
```

### Verify Caddy Config
If using the default [Caddy](../caddy/readme.md) config, the [Caddyfile](../caddy/Caddyfile) will default to subdomain `budibase.$MY_DOMAIN` for this app. Ensure the relevant block is uncommented in the Caddyfile, and update it as needed.

## Resources

- https://budibase.com
- https://docs.budibase.com/docs/docker-compose