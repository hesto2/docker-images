FROM node:20-alpine

RUN apk add --no-cache --virtual .build-deps \
python3 \
py3-pip \
ca-certificates \
openssl \
bash \
curl \
git \
zip && \
pip3 install --no-cache-dir --break-system-packages awscli

ENV TERRAFORM_VERSION 1.7.3

RUN wget -O terraform.zip https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
  unzip terraform.zip -d /usr/local/bin && \
  rm -f terraform.zip
RUN mkdir -p /home/node/project
RUN chmod -R 777 /home/node
USER node

ENTRYPOINT ["/bin/bash", "-c"]

