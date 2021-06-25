A bind mount allows adding files from the context (or a different stage), so they are available in the build process but are not committed to the resulting image.

```
docker build -t test:1 -f Dockerfile.1 .
docker run --rm test:1

docker build -t test:2 -f Dockerfile.2 .
docker run --rm test:2
```

