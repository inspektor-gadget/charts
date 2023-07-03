# Helm Repository for Inspektor Gadget

Inspektor Gadget is a collection of tools (or gadgets) to debug and inspect
Kubernetes resources and applications. It manages the packaging, deployment and
execution of [eBPF](https://ebpf.io/) programs in a Kubernetes cluster,
including many based on [BCC](https://github.com/iovisor/bcc) tools, as well as
some developed specifically for use in Inspektor Gadget. It automatically maps
low-level kernel primitives to high-level Kubernetes resources, making it easier
and quicker to find the relevant information.

## The Gadgets

Inspektor Gadget tools are known as gadgets. You can deploy one, two or many gadgets.

![different tools offered by Inspektor Gadget](https://raw.githubusercontent.com/inspektor-gadget/inspektor-gadget/main/docs/images/architecture/inspektor_gadget_tools.svg)

## Getting Started

```
$ helm repo add gadget https://inspektor-gadget.github.io/charts
$ helm install gadget gadget/gadget --namespace=gadget --create-namespace
```

## Maintainers

| Name |  Url |
| ---- |  --- |
| Inspektor Gadget Team | <https://www.inspektor-gadget.io> |

## Source Code

* <https://github.com/inspektor-gadget/inspektor-gadget>

## Getting Help

In case you encounter any problems while using Inspektor Gadget, feel free to
open an issue in the [Inspektor Gadget GitHub repository](https://github.com/inspektor-gadget/inspektor-gadget) or reach out to use at
[Inspektor Gadget Slack channel](https://kubernetes.slack.com/messages/inspektor-gadget/).

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| config.hookMode | string | `"auto"` | How to get containers start/stop notifications (auto, crio, podinformer, nri, fanotify, fanotify+ebpf") |
| config.fallbackPodInformer | bool | `true` | Whether to use the fallback pod informer |
| config.containerdSocketPath | string | `"/run/containerd/containerd.sock"` | Containerd CRI Unix socket path |
| config.crioSocketPath | string | `"/run/crio/crio.sock"` | CRI-O CRI Unix socket path |
| config.dockerSocketPath | string | `"/run/docker.sock"` | Docker Engine API Unix socket path |
| config.experimental | bool | `false` | Enable experimental features |
| image.repository | string | `"ghcr.io/inspektor-gadget/inspektor-gadget"` | Container repository for the container image |
| image.pullPolicy | string | `"Always"` | Pull policy for the container image |
| image.tag | string | `""` | Tag for the container image |
| nodeSelector | object | `{"kubernetes.io/os":"linux"}` | Node selector used by `gadget` container |
| affinity | object | `{}` | Affinity used by `gadget` container |
| tolerations | list | `[{"effect":"NoSchedule","operator":"Exists"},{"effect":"NoExecute","operator":"Exists"}]` | Tolerations used by `gadget` container |
