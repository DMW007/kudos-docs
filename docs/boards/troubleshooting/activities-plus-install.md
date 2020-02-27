# Activities Plus Install FAQ

If you are following the HCL install documentation, these notes need to be applied during the relevant sections. We recommend using our [install documentation](https://docs.kudosapps.com/boards/cp/) instead.

## Installing Activities Plus services

- There is an [HCL Technote](https://support.hcltechsw.com/csm?id=kb_article&sysparm_article=KB0074334) (KB0074334) that needs to be followed

- The helm upgrade command needs to be run from the directory containing boards-cp.yaml and the correct command is:

        helm upgrade kudos-boards-cp path_to_helm_charts/kudos-boards-cp-1.0.0-20191120-214007.tgz -i -f ./boards-cp.yaml --namespace connections --recreate-pods

    e.g.

        helm upgrade kudos-boards-cp /root/microservices_connections/hybridcloud/helmbuilds/kudos-boards-cp-1.0.0-20191120-214007.tgz -i -f ./boards-cp.yaml --namespace connections --recreate-pods

## Configuring IBM HTTP Server as reverse proxy

- If you do not have them enabled, you will need to enable the following modules by uncommenting them (remove the '#'):

        LoadModule proxy_module modules/mod_proxy.so
        LoadModule proxy_connect_module modules/mod_proxy_connect.so
        LoadModule proxy_ftp_module modules/mod_proxy_ftp.so
        LoadModule proxy_http_module modules/mod_proxy_http.so

        LoadModule rewrite_module modules/mod_rewrite.so

- If you have not specified earlier (such as during other component-pack app installs), please set `ProxyPreserveHost On` before the Kudos Boards section in the VirtualHost

## Updating the Activities Plus configuration file

- Please use this [boards-cp.yaml](/assets/boards/cp/boards-cp.yaml) NOT the one supplied with the component pack.

## Migrating Activities data

- The helm upgrade command needs to be run from the directory containing boards-cp.yaml and the correct command is:

        helm upgrade kudos-boards-cp-activity-migration path_to_helm_charts/kudos-boards-cp-activity-migration-1.0.0-20191120-214007.tgz -i -f ./boards-cp.yaml --namespace connections --recreate-pods

    e.g.

        helm upgrade kudos-boards-cp-activity-migration /root/microservices_connections/hybridcloud/helmbuilds/kudos-boards-cp-activity-migration-1.0.0-20191120-214007.tgz -i -f ./boards-cp.yaml --namespace connections --recreate-pods