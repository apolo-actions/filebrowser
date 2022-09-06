# Filebrowser action for neuro-flow

This is a [`neuro-flow`](https://github.com/neuro-inc/neuro-flow) action launching the [Filebrowser](https://hub.docker.com/r/filebrowser/filebrowser) app for working with platform storage.

All it needs is a reference to a storage folder that becomes the root folder for the Filebrowser instance.

### Quick example

```
jobs:
  filebrowser:
    action: gh:neuro-actions/filebrowser@v1.0.1
    args:
      volumes_project_remote: $[[ volumes.project.remote ]]
```

## Arguments

### `volumes_project_remote`

Reference to the project's remote volume.

### Example

```
args:
	volumes_project_remote: $[[ volumes.project.remote ]]
```

### `http_port`

HTTP port to use for Filebrowser. `"80"` by default.

### Example

```
args:
	http_port: "8888"
```

### `http_auth`

Whetther to use HTTP authentication for Filebrowser or not. `"True"` by default.

### Example

```
args:
	http_auth: "False"
```

### `job_name`

The name of the Filebrowser server. Use it to generate a predictable job hostname. `"filebrowser"` by default.

### Example

```
args:
	job_name: "browser-job"
```

### `preset`

Resource preset, used to run the server. The first one in the `neuro config show` list by default.

### Example

```
args:
	preset: cpu-small
```

### `life_span`

Amount of time to keep the Filebrowser job running.
Format: "1d2h3m4s" (some parts may be missing).
Default: 1 day.

### Example

```
args:
	life_span: 30d20h
```
