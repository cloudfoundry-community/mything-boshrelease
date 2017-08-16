# BOSH release for mything

This BOSH release and deployment manifest deploy a cluster of mything.

## Install

```
export BOSH_ENVIRONMENT=<bosh-alias>
export BOSH_DEPLOYMENT=mything
bosh2 deploy manifests/mything.yml --vars-store tmp/creds.yml
```

If your BOSH has Credhub, then you can omit `--vars-store` flag. It is used to generate any passwords/credentials/certificates required by `manifests/mything.yml`.


## Development

As a developer of this release, create new releases, upload and deploy them:

```
bosh2 create-release --force && \
  bosh2 -n upload-release && \
  bosh2 deploy manifests/mything.yml --vars-store tmp/creds.yml
```

If your BOSH has Credhub, then you can omit `--vars-store` flag. It is used to generate any passwords/credentials/certificates required by `manifests/mything.yml`.
