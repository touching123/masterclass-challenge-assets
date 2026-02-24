# Masterclass Challenge Assets

This repository contains the assets used for a [Killercoda](https://killercoda.com/touching/course/scenarios) challenge, specifically focusing on Kubernetes policy enforcement using [Kyverno](https://kyverno.io/).

## Contents

### Kyverno Policies (`kyverno-policies/`)

This directory houses `masterclass-policies.yaml`, which contains a set of Kyverno `ClusterPolicy` definitions designed to enforce best practices and security standards in a Kubernetes cluster. 

The following policies are included and enforced:

* **`require-resources`**: Ensures that all Pod containers have CPU and memory `requests` and `limits` defined.
* **`require-probes`**: Requires all Pod containers to configure both `livenessProbe` and `readinessProbe`.
* **`require-labels`**: Mandates the presence of standard Kubernetes labels (`app.kubernetes.io/name` and `app.kubernetes.io/instance`) on Pods, Deployments, and Services.
* **`require-non-root`**: Enforces that containers must run as a non-root user by requiring `securityContext.runAsNonRoot: true`.
* **`require-drop-all`**: Requires containers to drop all Linux capabilities (`securityContext.capabilities.drop: ["ALL"]`) for enhanced security.
* **`require-non-default-sa`**: Prevents the use of the `default` ServiceAccount, requiring Pods to specify a dedicated `serviceAccountName`.

## Usage

These assets are intended to be deployed as part of a Killercoda interactive environment to provide a hands-on learning experience for Kubernetes security and policy management.
