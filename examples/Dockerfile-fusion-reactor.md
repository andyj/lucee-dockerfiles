Dockerfile

You need to move the [downloaded and move the fusionreactor.jar](http://www.fusion-reactor.com/download/) to the base folder of your Docker build folder i.e. lucee-nginx/4.5/

```
RUN mkdir -p /opt/fusionreactor/instance/Tomcat8/
COPY fusionreactor.jar /opt/fusionreactor/instance/Tomcat8/

RUN echo 'FR_OPTS="-javaagent:/opt/fusionreactor/instance/Tomcat8/fusionreactor.jar=address=10000"' >> /usr/local/tomcat/bin/setenv.sh && \
    echo 'export JAVA_OPTS="$JAVA_OPTS $FR_OPTS"' >> /usr/local/tomcat/bin/setenv.sh
```

If you have a licence then you'll need to copy that file to the base folder of your Docker container and add the following couple of lines

```
RUN mkir /opt/fusionreactor/license
COPY fusionreactor.licence /opt/fusionreactor/license
```