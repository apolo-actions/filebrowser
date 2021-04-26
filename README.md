# Filebrowser action for neuro-flow

This is a [`neuro-flow`](https://github.com/neuro-inc/neuro-flow) action launching the [Filebrowser](https://hub.docker.com/r/filebrowser/filebrowser) app for working with platform storage.

All it needs is a reference to a storage folder that becomes the root folder for the Filebrowser instance.

### Quick example

```
jobs:
  filebrowser:
    action: gh:neuro-actions/filebrowser@master
    args:
      volumes_project_remote: $[[ volumes.project.remote ]]
```

## Arguments

### `http_port`

HTTP port to use for Jupyter. `"80"` by default.

### Example

```
args:
	http_port: "8888"
```

### `http_auth`

Whetther to use HTTP authentication for Jupyter or not. `"True"` by default.

### Example

```
args:
	http_auth: "False"
```

### `volumes_project_remote`

Reference to the project's remote volume.

### Example

```
args:
	volumes_project_remote: $[[ volumes.project.remote ]]
```

### `job_name`

The name of the Jupyter server. Use it to generate a predictable job hostname. `"filebrowser"` by default.

### Example

```
args:
	job_name: "browser-job"
```