# Kielipankki-demo

This repository contains the Language Bank Demo server scripts (under `cgi-bin/`, `files/` and `scripts/`) and configuration settings (under `ansible/`).

## Configuration

There are three roles in `ansible/` that are responsible for the server's actual content.

### `demo-setup`

Setting up the instance, installing a large number of Ubuntu and Python packages, configuring `lighttpd`, ensuring directories and permissions.

### `cgi-bin`

Fetching repositories and binary blobs, building compiled objects, installing everything in the appropriate places.

### `html`

Writing `index.html` using a template which loops through content variables in `ansible/roles/html/vars/index_vars.yaml`. Commenting out something here results in the front page no longer displaying that tool.

## Dependencies within CSC

The server also depends on a number of archives that are kept in Allas. They are:

```
s3://demo_server_blobs/compiled_pmatch.tar.gz
s3://demo_server_blobs/fiwn.tar.gz
s3://demo_server_blobs/hfst-tagger.tar.gz
s3://demo_server_blobs/histner.tar.gz
s3://demo_server_blobs/omor.tar.gz
s3://demo_server_blobs/predict.tar.gz
s3://demo_server_blobs/termipankki.tar.gz
s3://demo_server_blobs/vecs.tar.gz
s3://demo_server_blobs/ylilauta.tar.bz2
```
