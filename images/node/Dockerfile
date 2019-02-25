FROM kindest/node:v1.13.2

#RUN echo "export http_proxy=http://172.17.0.1:8118/" >> /etc/default/docker
#RUN echo "export https_proxy=https://172.17.0.1:8118/" >> /etc/default/docker
# COPY ProxyRootCA.crt /usr/local/share/ca-certificates/ProxyRootCA.crt
# RUN update-ca-certificates

RUN mkdir -p /etc/systemd/system/docker.service.d
RUN echo "[Service]\nEnvironment=\"HTTP_PROXY=http://172.17.0.1:8118/\"" > /etc/systemd/system/docker.service.d/http-proxy.conf
#RUN echo "[Service]\nEnvironment=\"HTTPS_PROXY=https://172.17.0.1:8118/\"" > /etc/systemd/system/docker.service.d/https-proxy.conf
RUN echo "[Service]\nEnvironment=\"NO_PROXY=localhost,127.0.0.1,172.0.0.0/8,0.0.0.0/0\"" > /etc/systemd/system/docker.service.d/no-proxy.conf
