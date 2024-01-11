# reveal-js inside kubernetes!
This Helm Chart deploys Reveal.js presentations and server using Nginx within a Kubernetes cluster, offering flexibility to host multiple presentations and allowing customization through ConfigMaps.

It allows the installation of revealjs as a server into a Kubernetes cluster and enables for example direct editing of one or more HTML or Markdown files as a ConfigMap, adding them as a Kubernetes resource.

The container is based on the nginx container, with the revealjs tarball simply unpacked into the nginx container. The ConfigMap is unpacked into /usr/share/nginx/html/slides. The Helm chart also supports specifying existing or custom ConfigMaps with configurable mount points.

For example, it is possible to call Markdowns from a git directly as remote Markdown and much more.

## Deploy on kubernetes cluster (documentation wip)
You can create your own values file with the html files included. The helm chart creates in this example the config mount by itself:
```
1. Installing with default values inside reveal namespace:
helm install reveal . --create-namespace -n reveal

2. Installing with your own values inside reveal namespace:
helm install reveal . --create-namespace -n reveal -f ../../youvalues.yaml

3. You can also uninstalling it, after your presentation:
helm uninstall reveal -n reveal
```

## Used tools
This is a list of used software

| Tool | Version |
| ------ | ----------- |
| Revealjs   | 5.0.4 |
| Nginx (offical image) | nginx:alpine3.18 |


## Local testing with image
The Contaienr image are located at ghcr.
With this example command, you can pull the image to you local env:
```
nerdctl run ghcr.io/syntax3rror404/revealjs-helm/revealjs:latest
```
<div align="center">
  MIT licence | Copyright © 2024 Marcel Zapf
</div>
