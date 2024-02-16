# Workflows

This repository contains N8N – an extendable workflow automation tool.

## Requirements

Make sure that the [Base](https://gitlab.com/hueske-digital/services/base) and the [nginx reverse proxy](https://gitlab.com/hueske-digital/services/proxy) are already set up and started.

## Setup instructions

Clone the code to your server:<br>
```
git clone git@gitlab.com:hueske-digital/services/workflows.git ~/services/workflows
```

Create environment file and fill up with your values:<br>
```
cd ~/services/workflows && cp .env.example .env && vim .env
```

Pull images and start the compose file:<br>
```
docker compose up -d
```

While waiting you can create a host in your nginx proxy manager which points to `workflows-app-1` with port `443` and websockets enabled.

## Other information

Update all container images and recreate them if new images are available:<br>
```
docker compose pull && docker compose up -d
```

Restart a single container:<br>
```
docker compose restart app
```

Shutdown all container of this compose file:<br>
```
docker compose down
```

Show and follow logs:<br>
```
docker compose logs -ft
```

Additional configuration:<br>
You can include any other docker config by using an additional [compose file](https://docs.docker.com/compose/extends/).
