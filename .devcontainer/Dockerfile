ARG VARIANT="20"
FROM mcr.microsoft.com/vscode/devcontainers/javascript-node:0-${VARIANT}

# install some useful tools
RUN apt-get update && apt-get -y install --no-install-recommends curl git sqlite3 

# Install SAP CAP SDK globally by using user node. 
# User `node` is created for 20 variant of miscosoft development docker
USER node
RUN npm install -g @sap/cds-dk
RUN npm install -g hana-cli
WORKDIR /home/node

# install public key and package for client to repository for Cloud Foundry
RUN wget -q -O - https://packages.cloudfoundry.org/debian/cli.cloudfoundry.org.key | sudo apt-key add -
RUN echo "deb https://packages.cloudfoundry.org/debian stable main" | sudo tee /etc/apt/sources.list.d/cloudfoundry-cli.list
RUN sudo apt-get update
RUN sudo apt-get install cf8-cli

RUN npm install -g @ui5/cli 
RUN npm -g yo 
RUN npm -g @sapui5/generator-sapui5-templates
RUN npm -g @sap/generator-base-mta-module 
RUN npm -g @sap/generator-cap-project 
RUN npm -g @sap/generator-fiori
RUN npm -g @sap/generator-hdb-project 
RUN npm -g mbt 
RUN npm -g mta 
RUN npm -g typescript
