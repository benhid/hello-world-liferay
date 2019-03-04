# Liferay Portlet Deployment

This is an example of how to deploy a portlet on Liferay 7.1 with [Docker](https://hub.docker.com/r/liferay/portal/).

## Build instructions

Run 

```bash
$ ./gradlew build
```

([see more](https://docs.gradle.org/current/userguide/gradle_wrapper.html)) or, alternatively, 

```bash
$ gradle build
```

to generate the _war_ file in `~/apps/jsp-war-portlet/build/libs/`.

## Deploy to Docker

Run

```
$ docker run -it -p 8080:8080 -v $(pwd)/build/libs:/opt/liferay/deploy liferay/portal:7.1.0-ga1-201809012030
```

to generate an instance of Liferay and copy the _war_ file to `/opt/liferay/deploy` inside the container. Modules within this folder will be deployed on Liferay Portal at runtime.