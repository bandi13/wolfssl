This is a small container that has wolfCLU installed for quick access. To build your own run the following:
```
docker build --pull --build-arg DUMMY=$(date +%s) -t wolfclu . 
```

To run the container, you can use:
```
docker run -it --rm -v $(pwd):/ws -w /ws wolfclu version
```
This command will allow you to use the certs/keys in your local directory.

If you would like to have a container that builds for multiple architectures, you can use:
```
docker buildx build --pull --build-arg DUMMY=$(date +%s) -t wolfclu --platform=linux/amd64,linux/arm64,linux/arm/v7,linux/riscv64 .
```

