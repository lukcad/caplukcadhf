# caplukcadhf

## Overview

This is template of basic container for development using SAP CAP approach. This can be donwloaded from git Hub into your workspace and enriched by your CDS projects whihc follows to recomendations from [SAP CAP](https://cap.cloud.sap/docs/about/).

Initial container includes:

* container with node.js;
* install of components: curl, git, sqlite3;
* non-root user: node
* workdir: home/node
* main extensions for CAP to use VS:
  * SAPSE.vscode-cds
  * dbaeumer.vscode-eslint
  * humao.rest-client
  * qwtel.sqlite-viewer
  * mechatroner.rainbow-csv
* additional extensions for Fiori, UI5, typescript to use VS:

        "sapse.sap-ux-fiori-tools-extension-pack",
        "sapos.yeoman-ui",
        "hookyqr.beautify",
        "coenraads.bracket-pair-colorizer-2",
        "eamodio.gitlens",
        "yzhang.markdown-all-in-one",
        "fivepointseven.node-version",
        "bengreenier.vscode-node-readme",
        "christian-kohler.path-intellisense",
        "saposs.sap-hana-driver-for-sqltools",
        "sapse.vsc-extension-sa",
        "mtxr.sqltools",
        "pflannery.vscode-versionlens",
        "visualstudioexptteam.vscodeintellicode",
        "vscode-icons-team.vscode-icons",
        "saposs.xml-toolkit",
        "dotjoshjohnson.xml",
        "SAPSE.hana-database-explorer" 

* installing globally during initializaiton container these libraries for SAP CAP, CF and HANA:
  * cds
  * hana-cli
  * cf8-cli

* installing additional for Fiori generators, UI5, typescript

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


You should clone this by command to provide your own name of docker container project:

    git clone https://github.com/lukcad/caplukcadhf.git <your_name_container_project>

after clonning, you should change name of your container by opening file devcontainer.json and changing parameter "name" there.

You should open it by `VS code` as `contianer` and add into it as many as you wish CDS projects.

Using container:

* create CAP project

  Use this command to add new project in container:

      cds init <your_name_project>

  Use this command to add mock data into your new created project:

      cds add tiny-sample

  or

      cds add data

* create connectivity to SAP HANA cloud:

  * activate access to your Cloud Foundry in SAP BTP by preinstalled in container cf-cli using command:

        cf login

  * find name of your hana cloud from list of CF services:

        cf services

  * use preinstalled in container hana-client to accesss to your database:

        hana-cli hc

Enjoy, you have container which you can use for development your Full-Stack CAP applicaitons:

  * with access to SAP Hana Cloud based on SAP BTP CF
  * with access to xsuaa services based on SAP BTP
  * with Fiori UI based on SAP UI5 with Typescript 

Thank you,
LUKCAD.
