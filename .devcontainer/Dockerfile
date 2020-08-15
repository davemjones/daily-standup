#-------------------------------------------------------------------------------------------------------------
# Copyright (c) Microsoft Corporation. All rights reserved.
# Licensed under the MIT License. See https://go.microsoft.com/fwlink/?linkid=2090316 for license information.
#-------------------------------------------------------------------------------------------------------------

# To fully customize the contents of this image, use the following Dockerfile instead:
# https://github.com/microsoft/vscode-dev-containers/tree/v0.128.0/containers/javascript-node-14/.devcontainer/Dockerfile
FROM mcr.microsoft.com/vscode/devcontainers/javascript-node:0-14

# Setup git bash prompt
COPY ./git-profile.txt /tmp
RUN cat /tmp/git-profile.txt >> /root/.bashrc
RUN curl -o /tmp/.git-prompt.sh \
    https://raw.githubusercontent.com/git/git/master/contrib/completion/git-prompt.sh
RUN echo 'source /tmp/.git-prompt.sh' >> /root/.bashrc

# Install npm packages globally
RUN npm install -g http-server 
RUN npm install -g ngrok --unsafe-perm=true --allow-root
COPY ./ngrok-authtoken.txt /tmp 
RUN ngrok authtoken | cat /tmp/ngrok-authtoken.txt

# ** [Optional] Uncomment this section to install additional packages. **
#
# RUN apt-get update \
#     && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>

