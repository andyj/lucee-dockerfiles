# Change timezone of container

On Ubuntu based Dockers this will change the time zone of the container to UTC

You can change "Etc/UTC" to any supported timezone e.g. "Europe/London", "America/Antigua" etc


```
RUN echo "Etc/UTC" > /etc/timezone && \
dpkg-reconfigure -f noninteractive tzdata
```