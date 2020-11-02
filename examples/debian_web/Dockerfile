FROM armbuild/debian:latest
RUN apt-get update && apt-get -y install curl php5 && apt-get clean
RUN mkdir -p /shop/randomsilo/web
WORKDIR /shop/randomsilo/web
RUN echo "<h1>Test</h1>" >> /shop/randomsilo/web/index.php
EXPOSE 80
CMD ["php","-S","0.0.0.0:8080"]