Storing npm cache between builds

The traditional way
```
docker build -f Dockerfile.1 -t ex:1 .
```

Using a mount for the npm cache, the second build is faster
```
docker build -f Dockerfile.2 -t ex:2 .
touch newfile
docker build -f Dockerfile.2 -t ex:2 .
docker build . -f Dockerfile.2 --no-cache
```

And it takes less space:

```
docker images ex
```

Because the `.npm` as it is mounted it is not present in the final image!
```
dk run --rm ex:1 du -s /root/.npm
dk run --rm ex:2 du -s /root/.npm
```