# playground-container

## How To Use

1. Edit `.env`

    - Set `LOCAL_HOST_PATH`

        - e.g. `/home/ec2-user/playground-container`

    - Set `USERNAME`

        - e.g. `ec2-user`

1. Edit `devcontainer.json`

    - Set `remoteUser`

        - e.g. `ec2-user`

    - Set `service`

        - Service name in `docker-compose.yml`

        - e.g. `node16`
