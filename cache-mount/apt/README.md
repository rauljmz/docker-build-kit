Storing cache between builds

```
docker build .
```

```
touch newfile
docker build .
```

```
docker build . --no-cache
```