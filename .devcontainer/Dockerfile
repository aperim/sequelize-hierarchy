# [Choice] Node.js version: 14, 12, 10
ARG VARIANT="14-buster"
FROM mcr.microsoft.com/vscode/devcontainers/javascript-node:0-${VARIANT}

# [Optional] Uncomment this section to install additional OS packages.
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends apt-transport-https ca-certificates gnupg curl

RUN ln -s /usr/bin/gpg /usr/local/bin/gpg && \
    sudo -u node mkdir -p /home/node/.gnupg \
      /home/node/.ssh \
      /home/node/.vscode-server/extensions \
      /home/node/.vscode-server-insiders/extensions

# Disabling kite to see if it is a resource hog
# RUN su - node -c "echo -e \"\\n\\n\" | bash -c \"\$(wget -q -O - https://linux.kite.com/dls/linux/current)\""

# [Optional] Uncomment if you want to install an additional version of node using nvm
# ARG EXTRA_NODE_VERSION=10
# RUN su node -c "source /usr/local/share/nvm/nvm.sh && nvm install ${EXTRA_NODE_VERSION}"

# [Optional] Uncomment if you want to install more global node modules
# RUN sudo -u node npm install -g <your-package-list-here>
RUN sudo -u node yarn global add prettier eslint prettier-eslint eslint-config-airbnb eslint-config-prettier eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-prettier eslint-plugin-react eslint-plugin-react-hooks