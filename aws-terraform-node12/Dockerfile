FROM node:12-alpine

RUN apk add --no-cache \
python \
py-pip \
py-setuptools \
ca-certificates \
openssl \
bash \
curl \
git \
zip && \
pip install --no-cache-dir --upgrade pip awscli

ENV TERRAFORM_VERSION 0.12.24

RUN wget -O terraform.zip https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
  unzip terraform.zip -d /usr/local/bin && \
  rm -f terraform.zip

RUN mkdir -p /home/node/app && chown -R node:node /home/node/app
WORKDIR /home/node/app
USER node
COPY --chown=node:node . .

ENTRYPOINT ["/bin/bash", "-c"]

