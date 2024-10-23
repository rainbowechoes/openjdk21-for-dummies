build a image to compile the jdk base on the jdk source code and bootstrap jdk

prerequirement:
1. install sdkman first

```sh
docker build -t rainbow-openjdk-environment:openjdk21 .
mkdir ../../jdk-dist
docker run --rm -it -v /home/rainbow/git_repo/jdk-source:/source -v /home/rainbow/git_repo/jdk-dist:/dist -v /home/rainbow/.sdkman/candidates/java/current:/bootstrap rainbow-openjdk-environment:openjdk21
```

build a custom jdk docker image

```sh
docker build -t rainbow-jdk-bundle -f Dockerfile.jdk ../../
```

docker no space left:
```sh
docker system prune -a --volumes
```