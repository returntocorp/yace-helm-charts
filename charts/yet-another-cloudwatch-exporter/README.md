# yet-another-cloudwatch-exporter

![Version: 0.20.0](https://img.shields.io/badge/Version-0.20.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: v0.51.0](https://img.shields.io/badge/AppVersion-v0.51.0-informational?style=flat-square)

Yace - Yet Another CloudWatch Exporter

**Homepage:** <https://github.com/nerdswords/helm-charts>

## Installation

```sh
helm repo add nerdswords https://nerdswords.github.io/helm-charts
helm install nerdswords/yet-another-cloudwatch-exporter
```

## Source Code

* <https://github.com/nerdswords/yet-another-cloudwatch-exporter>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| aws.aws_access_key_id | string | `nil` |  |
| aws.aws_secret_access_key | string | `nil` |  |
| aws.role | string | `nil` |  |
| aws.secret.includesSessionToken | bool | `false` |  |
| aws.secret.name | string | `nil` |  |
| config | string | `"apiVersion: v1alpha1\nsts-region: eu-west-1\ndiscovery:\n  exportedTagsOnMetrics:\n    ec2:\n      - Name\n    ebs:\n      - VolumeId\n  jobs:\n  - type: es\n    regions:\n      - eu-west-1\n    searchTags:\n      - key: type\n        value: ^(easteregg|k8s)$\n    metrics:\n      - name: FreeStorageSpace\n        statistics:\n        - Sum\n        period: 60\n        length: 600\n      - name: ClusterStatus.green\n        statistics:\n        - Minimum\n        period: 60\n        length: 600\n      - name: ClusterStatus.yellow\n        statistics:\n        - Maximum\n        period: 60\n        length: 600\n      - name: ClusterStatus.red\n        statistics:\n        - Maximum\n        period: 60\n        length: 600"` |  |
| extraArgs | list | `[]` |  |
| extraEnv | list | `[]` |  |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"ghcr.io/nerdswords/yet-another-cloudwatch-exporter"` |  |
| image.tag | string | `""` |  |
| imagePullSecrets | list | `[]` |  |
| ingress.annotations | object | `{}` |  |
| ingress.className | string | `""` |  |
| ingress.enabled | bool | `false` |  |
| ingress.hosts[0].host | string | `"chart-example.local"` |  |
| ingress.hosts[0].paths[0].path | string | `"/"` |  |
| ingress.hosts[0].paths[0].pathType | string | `"ImplementationSpecific"` |  |
| ingress.tls | list | `[]` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` |  |
| podLabels | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| portName | string | `"http"` |  |
| priorityClassName | string | `nil` |  |
| prometheusRule.enabled | bool | `false` |  |
| replicaCount | int | `1` |  |
| resources | object | `{}` |  |
| securityContext | object | `{}` |  |
| service.port | int | `80` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |
| serviceAccount.name | string | `""` | The name of the service account to use. If not set and create is true, a name is generated using the fullname template |
| serviceMonitor.enabled | bool | `false` |  |
| testConnection | bool | `true` |  |
| tolerations | list | `[]` |  |
