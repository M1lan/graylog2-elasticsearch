```
docker run \
  --name=my-container \
  --restart=always \
  --log-driver=gelf \
  --log-opt gelf-address=udp://192.168.99.100:12201 \
  -d namespace/image
```
