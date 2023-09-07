```
docker run <image>:<tag>
docker save <image>:<tag> | gzip > <output-name>.tar.gz
docker load <image>.tar.gz
```