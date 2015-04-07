Docker image for Breakerbox

I've added env to the breakerbox.urls.

https://github.com/arthurtsang/breakerbox

so you can set the config.properties like this

```
#!/bin/bash

docker kill breakerbox >/dev/null 2>&1
docker rm breakerbox >/dev/null 2>&1
docker run -d --name=breakerbox \
        -p 8080:8080 \
        -p 8081:8081 \
        -e BREAKERBOX_URLS=file:config/config.properties,http://localhost:8080/archaius/breakerbox \
        -v /home/arthur/breakerbox-config:/home/breakerbox/config \
        arthurtsang/breakerbox
```
