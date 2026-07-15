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

For the full installation guide, see the
[Inspektor Gadget documentation](https://inspektor-gadget.io/docs/latest/reference/install-kubernetes#installation-with-the-helm-chart).

## Chart Values

The list of configurable values, their defaults, and descriptions are published
alongside the chart itself:

* [Chart page on Artifact Hub](https://artifacthub.io/packages/helm/gadget/gadget)
* Chart source (template and `values.yaml`) in the [inspektor-gadget/inspektor-gadget repository](https://github.com/inspektor-gadget/inspektor-gadget/tree/main/charts/gadget)

## Maintainers

| Name |  Url |
| ---- |  --- |
| Inspektor Gadget Team | <https://www.inspektor-gadget.io> |

## Source Code

* <https://github.com/inspektor-gadget/inspektor-gadget>

## Getting Help

In case you encounter any problems while using Inspektor Gadget, feel free to
open an issue in the [Inspektor Gadget GitHub repository](https://github.com/inspektor-gadget/inspektor-gadget) or reach out to us at
[Inspektor Gadget Slack channel](https://kubernetes.slack.com/messages/inspektor-gadget/).
