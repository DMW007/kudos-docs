# Deploy MongoDB & S3 Storage

Kudos Boards requires an S3 object store, and a Mongo database. This documentation will deploy a Minio S3 storage container & MongoDB replicaSet into the Swarm setup.

If you already have externally hosted mongo database and/or S3 storage please contact us for assistance in utilising them. [support@kudosboards.com](mailto:support@kudosboards.com)

### Pre-Requisites

1. Docker swarm with Portainer up and running [Guide here](/swarm/)
1. [Storage Config File](/assets/config/swarm/storage.yml) downloaded

---

### Update config file

| Key            | Description                                                                                                                                   |
| -------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| x-minio-access | Provide an access key to use (min 3 chars, alpha numeric and "-"), you will need to provide this to any services that require access to minio |
| x-minio-secret | Provide a secret key to use (min 8 chars, alpha numeric and "-"), you will need to provide this to any services that require access to minio  |

_Optional:_ if you only want to deploy one of these services you can remove the other, ie under `services:`, delete either the `mongo:` or `minio:` sections.

---

### Deploy

1. Open Portainer and login
1. Select your primary endpoint
1. Choose Stacks from the side menu
1. Click Add Stack
1. Name your stack `Storage`
1. Browse to your customised config file
1. Click "Deploy the stack"
