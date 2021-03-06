<!-- TOC -->

- [Container Expert Source](#container-expert-source)
- [Detalles](#detalles)
- [Swarm](#swarm)
- [VS Code](#vs-code)
- [ECS](#ecs)

<!-- /TOC -->

# Container Expert Source
![1](./docs/images/DockerBootcampv2.0-expert.png)

n nuestro **"Container Bootcamp v2.0 - Expert"**


# Detalles

Nuestra app no sera nada llamativo ni nada complejo, por que el objetivo de este bootcamp no es ni lenguajes de programación, ni tener un app tan compleja que no nos permita avanzar; a lo largo de este bootcamp haremos refactoring a nuestra app para que aprendamos algunos detalles necesarios para hacerla mas facil la migracion a Cloud Native app.

> No es tan necesario saber programar PERO definitivamente si podría ayudar.
> Pido disculpas a aquellos developer experimentados, mi background no es desarrollo.

Tendremos 3 elecciones de lenguajes:

- [python](./src/python/app.py) [Recomendado]
- [go](./src/go/main.go)
- [nodejs](./src/nodejs/app.js)

Con estos lenguajes trabajaremos y transformaremos a manera que podamos entender los requerimientos o sugerencias que deberiamos de hacer en nuestras apps (vida real)


Cada app viene acompanado de exactamente lo mismo y se comportaran de la misma manera, a excepcion de python quien es nuestro frontend. Rutas:

- `"/"`: ruta root, mostrara un sencillo "HTML" con un mensaje importante, cada app tiene la responsabilidad de mostrar un **mensaje único.**
- `"/health"`: indica que nuestra app este saludable, nos servira en docker-compose, swarm & kubernetes.
- `"/api"`: devuelve un json con el **mensaje único.**
    ```json
    {
    "msg": "Bootcamp Experts 🤓!",
    "host": "456a45a47433"
    }
    ```


# Swarm

---
# VS Code

mi VS Code tiene los siguientes add-onds (plugins):

- better comments - Aaron Bond
- Docker - microsoft
- Kubernetes - microsoft
- editorconfig
- [THEME]: Andromeda Italic Border
- [File Icons Themes]: VSCode Icons


# ECS

```bash
ecs-cli configure --cluster kontinu-ecs --default-launch-type EC2 --config-name kontinu-ecs --region us-east-2

ecs-cli configure profile --access-key $aws_access_key_id --secret-key $aws_secret_access_key --profile-name kontinu-ecs-profile


ecs-cli up --keypair gitlab-devops-bootcamp --capability-iam --size 1 --instance-type t2.small --cluster-config kontinu-ecs --ecs-profile kontinu-ecs-profile


ecs-cli compose up --create-log-groups --cluster-config kontinu-ecs --ecs-profile kontinu-ecs-profile


ecs-cli compose down --cluster-config kontinu-ecs --ecs-profile kontinu-ecs-profile



ecs-cli compose service up --cluster-config kontinu-ecs --ecs-profile kontinu-ecs-profile


ecs-cli compose service rm --cluster-config kontinu-ecs --ecs-profile kontinu-ecs-profile

ecs-cli down --force --cluster-config kontinu-ecs --ecs-profile kontinu-ecs-profile



```
