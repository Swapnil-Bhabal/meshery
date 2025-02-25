---
layout: default
title: Meshery Adapter for Cilium Service Mesh
name: Meshery Adapter for Cilium Service Mesh
mesh_name: Ciluim
earliest_version: v1.10.6
port: 10012/tcp
project_status: beta
adapter_version: v0.1.0
lab: cilium-meshery-adapter
github_link: https://github.com/meshery/meshery-cilium
image: /assets/img/service-meshes/cilium.svg
permalink: service-meshes/adapters/cilium
---

{% include adapter-status.html %}

### Features

1. {{page.mesh_name}} Lifecycle Management
1. Workload Lifecycle Management
   1. Using Service Mesh Standards
      1. Service Mesh Performance (SMP)
         1. Prometheus and Grafana connections
      1. Service Mesh Interface (SMI)
1. Configuration Analysis, Patterns, and Best Practices
   1. Custom Service Mesh Configuration

## Lifecycle management

The {{page.name}} can install **{{page.version}}** of {{page.mesh_name}}. A number of sample applications can be installed using the {{page.name}}.

The {{ page.name }} is currently under construction ({{ page.project_status }} state), which means that the adapter is not functional and cannot be interacted with through the <a href="{{ site.baseurl }}/installation#6-you-will-now-be-directed-to-the-meshery-ui"> Meshery UI </a>at the moment. Check back here to see updates.

Want to contribute? Check our [progress]({{page.github_link}}).

### Install {{ page.mesh_name }}

##### Choose the Meshery Adapter for {{ page.mesh_name }}

<a href="{{ site.baseurl }}/assets/img/adapters/linkerd/linkerd-adapter.png">
  <img style="width:500px;" src="{{ site.baseurl }}/assets/img/adapters/linkerd/linkerd-adapter.png" />
</a>

##### Click on (+) and choose the {{page.version}} of the {{page.mesh_name}} service mesh.

<a href="{{ site.baseurl }}/assets/img/adapters/linkerd/linkerd-install.png">
  <img style="width:500px;" src="{{ site.baseurl }}/assets/img/adapters/linkerd/linkerd-install.png" />
</a>