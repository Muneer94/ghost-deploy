# ghost

![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.2.0](https://img.shields.io/badge/AppVersion-0.2.0-informational?style=flat-square)

Helm Chart Deployment of Ghost with mysql DB replication

**Homepage:** <https://github.com/Muneer94/ghost-deploy>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Muneer Syed | <github@muneer.dev> |  |

## Source Code

* <https://github.com/Muneer94/ghost-deploy>

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| file://../mysql/ | mysql | ~9.x.x-0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Sets Ghost Pod affinity |
| autoscaling | object | `{"enabled":false,"maxReplicas":2,"minReplicas":1,"targetCPUUtilizationPercentage":80,"targetMemoryUtilizationPercentage":80}` | Ghost Auto Scaling based on cpu and memory metrics |
| command | object | `{}` | Ghost Overides docker entrypoint command |
| containerPort | int | `2368` |  |
| extraEnvs | list | `[]` | Sets Ghost Additional environment variables |
| extraInitContainers | list | `[]` | Sets Ghost Additional Init Containers |
| fullnameOverride | string | `""` |  |
| ghost | object | `{"database":"databasename","nodeEnv":"production","password":"writeyourpassword","url":"https://example.com","user":"username"}` | Sets Ghost config |
| ghost.database | string | `"databasename"` | Mysql database name |
| ghost.nodeEnv | string | `"production"` | contrary to the default mentioned in the linked documentation, this image defaults to NODE_ENV=production (so development mode needs to be explicitly specified if desired) |
| ghost.password | string | `"writeyourpassword"` | Mysql database password |
| ghost.url | string | `"https://example.com"` | this url value is just an example, and is likely wrong for your environment! |
| ghost.user | string | `"username"` | Mysql database username |
| global | object | `{"imagePullSecret":"regcred"}` | Ghost global values |
| global.imagePullSecret | string | `"regcred"` | Sets Ghost Kubernetes Docker registry Secret name |
| images | object | `{"ghost":{"registry":"docker.io","repository":"ghost","tag":"5.75.3-alpine"},"pullPolicy":"IfNotPresent"}` | Sets Ghost container image |
| images.ghost | object | `{"registry":"docker.io","repository":"ghost","tag":"5.75.3-alpine"}` | Sets Ghost main container image |
| labels | object | `{"app":"ghost"}` | Sets Ghost labels |
| lifecycle | object | `{}` | Attach handlers to container lifecycle events |
| minAvailable | int | `1` | Ghost Pod Disruption minimum pods available |
| mysql.architecture | string | `"standalone"` |  |
| mysql.auth.createDatabase | bool | `true` |  |
| mysql.auth.customPasswordFiles | object | `{}` |  |
| mysql.auth.database | string | `"databasename"` |  |
| mysql.auth.defaultAuthenticationPlugin | string | `""` |  |
| mysql.auth.existingSecret | string | `""` |  |
| mysql.auth.password | string | `"writeyourpassword"` |  |
| mysql.auth.replicationPassword | string | `""` |  |
| mysql.auth.replicationUser | string | `"replicator"` |  |
| mysql.auth.rootPassword | string | `"writeyourpassword"` |  |
| mysql.auth.usePasswordFiles | bool | `false` |  |
| mysql.auth.username | string | `"username"` |  |
| mysql.clusterDomain | string | `"cluster.local"` |  |
| mysql.commonAnnotations | object | `{}` |  |
| mysql.commonLabels | object | `{}` |  |
| mysql.diagnosticMode.args[0] | string | `"infinity"` |  |
| mysql.diagnosticMode.command[0] | string | `"sleep"` |  |
| mysql.diagnosticMode.enabled | bool | `false` |  |
| mysql.extraDeploy | list | `[]` |  |
| mysql.fullnameOverride | string | `""` |  |
| mysql.global.imagePullSecrets | list | `[]` |  |
| mysql.global.imageRegistry | string | `""` |  |
| mysql.global.storageClass | string | `"local-path"` |  |
| mysql.image.debug | bool | `false` |  |
| mysql.image.digest | string | `""` |  |
| mysql.image.pullPolicy | string | `"IfNotPresent"` |  |
| mysql.image.pullSecrets | list | `[]` |  |
| mysql.image.registry | string | `"docker.io"` |  |
| mysql.image.repository | string | `"bitnami/mysql"` |  |
| mysql.image.tag | string | `"8.0.35-debian-11-r0"` |  |
| mysql.initdbScripts | object | `{}` |  |
| mysql.initdbScriptsConfigMap | string | `""` |  |
| mysql.kubeVersion | string | `""` |  |
| mysql.metrics.containerSecurityContext.enabled | bool | `true` |  |
| mysql.metrics.containerSecurityContext.runAsNonRoot | bool | `true` |  |
| mysql.metrics.containerSecurityContext.runAsUser | int | `1001` |  |
| mysql.metrics.enabled | bool | `false` |  |
| mysql.metrics.extraArgs.primary | list | `[]` |  |
| mysql.metrics.extraArgs.secondary | list | `[]` |  |
| mysql.metrics.image.digest | string | `""` |  |
| mysql.metrics.image.pullPolicy | string | `"IfNotPresent"` |  |
| mysql.metrics.image.pullSecrets | list | `[]` |  |
| mysql.metrics.image.registry | string | `"docker.io"` |  |
| mysql.metrics.image.repository | string | `"bitnami/mysqld-exporter"` |  |
| mysql.metrics.image.tag | string | `"0.15.0-debian-11-r71"` |  |
| mysql.metrics.livenessProbe.enabled | bool | `true` |  |
| mysql.metrics.livenessProbe.failureThreshold | int | `3` |  |
| mysql.metrics.livenessProbe.initialDelaySeconds | int | `120` |  |
| mysql.metrics.livenessProbe.periodSeconds | int | `10` |  |
| mysql.metrics.livenessProbe.successThreshold | int | `1` |  |
| mysql.metrics.livenessProbe.timeoutSeconds | int | `1` |  |
| mysql.metrics.prometheusRule.additionalLabels | object | `{}` |  |
| mysql.metrics.prometheusRule.enabled | bool | `false` |  |
| mysql.metrics.prometheusRule.namespace | string | `""` |  |
| mysql.metrics.prometheusRule.rules | list | `[]` |  |
| mysql.metrics.readinessProbe.enabled | bool | `true` |  |
| mysql.metrics.readinessProbe.failureThreshold | int | `3` |  |
| mysql.metrics.readinessProbe.initialDelaySeconds | int | `30` |  |
| mysql.metrics.readinessProbe.periodSeconds | int | `10` |  |
| mysql.metrics.readinessProbe.successThreshold | int | `1` |  |
| mysql.metrics.readinessProbe.timeoutSeconds | int | `1` |  |
| mysql.metrics.resources.limits | object | `{}` |  |
| mysql.metrics.resources.requests | object | `{}` |  |
| mysql.metrics.service.annotations."prometheus.io/port" | string | `"{{ .Values.metrics.service.port }}"` |  |
| mysql.metrics.service.annotations."prometheus.io/scrape" | string | `"true"` |  |
| mysql.metrics.service.clusterIP | string | `""` |  |
| mysql.metrics.service.port | int | `9104` |  |
| mysql.metrics.service.type | string | `"ClusterIP"` |  |
| mysql.metrics.serviceMonitor.annotations | object | `{}` |  |
| mysql.metrics.serviceMonitor.enabled | bool | `false` |  |
| mysql.metrics.serviceMonitor.honorLabels | bool | `false` |  |
| mysql.metrics.serviceMonitor.interval | string | `"30s"` |  |
| mysql.metrics.serviceMonitor.jobLabel | string | `""` |  |
| mysql.metrics.serviceMonitor.labels | object | `{}` |  |
| mysql.metrics.serviceMonitor.metricRelabelings | list | `[]` |  |
| mysql.metrics.serviceMonitor.namespace | string | `""` |  |
| mysql.metrics.serviceMonitor.relabelings | list | `[]` |  |
| mysql.metrics.serviceMonitor.scrapeTimeout | string | `""` |  |
| mysql.metrics.serviceMonitor.selector | object | `{}` |  |
| mysql.nameOverride | string | `""` |  |
| mysql.namespaceOverride | string | `""` |  |
| mysql.networkPolicy.allowExternal | bool | `true` |  |
| mysql.networkPolicy.enabled | bool | `false` |  |
| mysql.networkPolicy.explicitNamespacesSelector | object | `{}` |  |
| mysql.primary.affinity | object | `{}` |  |
| mysql.primary.args | list | `[]` |  |
| mysql.primary.command | list | `[]` |  |
| mysql.primary.configuration | string | `"[mysqld]\ndefault_authentication_plugin={{- .Values.auth.defaultAuthenticationPlugin | default \"mysql_native_password\" }}\nskip-name-resolve\nexplicit_defaults_for_timestamp\nbasedir=/opt/bitnami/mysql\nplugin_dir=/opt/bitnami/mysql/lib/plugin\nport=3306\nsocket=/opt/bitnami/mysql/tmp/mysql.sock\ndatadir=/bitnami/mysql/data\ntmpdir=/opt/bitnami/mysql/tmp\nmax_allowed_packet=16M\nbind-address=*\npid-file=/opt/bitnami/mysql/tmp/mysqld.pid\nlog-error=/opt/bitnami/mysql/logs/mysqld.log\ncharacter-set-server=UTF8\nslow_query_log=0\nlong_query_time=10.0\n\n[client]\nport=3306\nsocket=/opt/bitnami/mysql/tmp/mysql.sock\ndefault-character-set=UTF8\nplugin_dir=/opt/bitnami/mysql/lib/plugin\n\n[manager]\nport=3306\nsocket=/opt/bitnami/mysql/tmp/mysql.sock\npid-file=/opt/bitnami/mysql/tmp/mysqld.pid"` |  |
| mysql.primary.containerSecurityContext.allowPrivilegeEscalation | bool | `false` |  |
| mysql.primary.containerSecurityContext.capabilities.drop[0] | string | `"ALL"` |  |
| mysql.primary.containerSecurityContext.enabled | bool | `true` |  |
| mysql.primary.containerSecurityContext.runAsNonRoot | bool | `true` |  |
| mysql.primary.containerSecurityContext.runAsUser | int | `1001` |  |
| mysql.primary.containerSecurityContext.seccompProfile.type | string | `"RuntimeDefault"` |  |
| mysql.primary.customLivenessProbe | object | `{}` |  |
| mysql.primary.customReadinessProbe | object | `{}` |  |
| mysql.primary.customStartupProbe | object | `{}` |  |
| mysql.primary.existingConfigmap | string | `""` |  |
| mysql.primary.extraEnvVars | list | `[]` |  |
| mysql.primary.extraEnvVarsCM | string | `""` |  |
| mysql.primary.extraEnvVarsSecret | string | `""` |  |
| mysql.primary.extraFlags | string | `""` |  |
| mysql.primary.extraPodSpec | object | `{}` |  |
| mysql.primary.extraPorts | list | `[]` |  |
| mysql.primary.extraVolumeMounts | list | `[]` |  |
| mysql.primary.extraVolumes | list | `[]` |  |
| mysql.primary.hostAliases | list | `[]` |  |
| mysql.primary.initContainers | list | `[]` |  |
| mysql.primary.lifecycleHooks | object | `{}` |  |
| mysql.primary.livenessProbe.enabled | bool | `true` |  |
| mysql.primary.livenessProbe.failureThreshold | int | `3` |  |
| mysql.primary.livenessProbe.initialDelaySeconds | int | `5` |  |
| mysql.primary.livenessProbe.periodSeconds | int | `10` |  |
| mysql.primary.livenessProbe.successThreshold | int | `1` |  |
| mysql.primary.livenessProbe.timeoutSeconds | int | `1` |  |
| mysql.primary.name | string | `"primary"` |  |
| mysql.primary.nodeAffinityPreset.key | string | `""` |  |
| mysql.primary.nodeAffinityPreset.type | string | `""` |  |
| mysql.primary.nodeAffinityPreset.values | list | `[]` |  |
| mysql.primary.nodeSelector | object | `{}` |  |
| mysql.primary.pdb.create | bool | `false` |  |
| mysql.primary.pdb.maxUnavailable | string | `""` |  |
| mysql.primary.pdb.minAvailable | int | `1` |  |
| mysql.primary.persistence.accessModes[0] | string | `"ReadWriteOnce"` |  |
| mysql.primary.persistence.annotations | object | `{}` |  |
| mysql.primary.persistence.enabled | bool | `true` |  |
| mysql.primary.persistence.existingClaim | string | `""` |  |
| mysql.primary.persistence.selector | object | `{}` |  |
| mysql.primary.persistence.size | string | `"8Gi"` |  |
| mysql.primary.persistence.storageClass | string | `""` |  |
| mysql.primary.persistence.subPath | string | `""` |  |
| mysql.primary.persistentVolumeClaimRetentionPolicy.enabled | bool | `false` |  |
| mysql.primary.persistentVolumeClaimRetentionPolicy.whenDeleted | string | `"Retain"` |  |
| mysql.primary.persistentVolumeClaimRetentionPolicy.whenScaled | string | `"Retain"` |  |
| mysql.primary.podAffinityPreset | string | `""` |  |
| mysql.primary.podAnnotations | object | `{}` |  |
| mysql.primary.podAntiAffinityPreset | string | `"soft"` |  |
| mysql.primary.podLabels | object | `{}` |  |
| mysql.primary.podManagementPolicy | string | `""` |  |
| mysql.primary.podSecurityContext.enabled | bool | `true` |  |
| mysql.primary.podSecurityContext.fsGroup | int | `1001` |  |
| mysql.primary.priorityClassName | string | `""` |  |
| mysql.primary.readinessProbe.enabled | bool | `true` |  |
| mysql.primary.readinessProbe.failureThreshold | int | `3` |  |
| mysql.primary.readinessProbe.initialDelaySeconds | int | `5` |  |
| mysql.primary.readinessProbe.periodSeconds | int | `10` |  |
| mysql.primary.readinessProbe.successThreshold | int | `1` |  |
| mysql.primary.readinessProbe.timeoutSeconds | int | `1` |  |
| mysql.primary.resources.limits | object | `{}` |  |
| mysql.primary.resources.requests | object | `{}` |  |
| mysql.primary.runtimeClassName | string | `""` |  |
| mysql.primary.schedulerName | string | `""` |  |
| mysql.primary.service.annotations | object | `{}` |  |
| mysql.primary.service.clusterIP | string | `""` |  |
| mysql.primary.service.externalTrafficPolicy | string | `"Cluster"` |  |
| mysql.primary.service.extraPorts | list | `[]` |  |
| mysql.primary.service.headless.annotations | object | `{}` |  |
| mysql.primary.service.loadBalancerIP | string | `""` |  |
| mysql.primary.service.loadBalancerSourceRanges | list | `[]` |  |
| mysql.primary.service.nodePorts.mysql | string | `""` |  |
| mysql.primary.service.ports.mysql | int | `3306` |  |
| mysql.primary.service.sessionAffinity | string | `"None"` |  |
| mysql.primary.service.sessionAffinityConfig | object | `{}` |  |
| mysql.primary.service.type | string | `"ClusterIP"` |  |
| mysql.primary.sidecars | list | `[]` |  |
| mysql.primary.startupProbe.enabled | bool | `true` |  |
| mysql.primary.startupProbe.failureThreshold | int | `10` |  |
| mysql.primary.startupProbe.initialDelaySeconds | int | `15` |  |
| mysql.primary.startupProbe.periodSeconds | int | `10` |  |
| mysql.primary.startupProbe.successThreshold | int | `1` |  |
| mysql.primary.startupProbe.timeoutSeconds | int | `1` |  |
| mysql.primary.terminationGracePeriodSeconds | string | `""` |  |
| mysql.primary.tolerations | list | `[]` |  |
| mysql.primary.topologySpreadConstraints | list | `[]` |  |
| mysql.primary.updateStrategy.type | string | `"RollingUpdate"` |  |
| mysql.rbac.create | bool | `false` |  |
| mysql.rbac.rules | list | `[]` |  |
| mysql.secondary.affinity | object | `{}` |  |
| mysql.secondary.args | list | `[]` |  |
| mysql.secondary.command | list | `[]` |  |
| mysql.secondary.configuration | string | `"[mysqld]\ndefault_authentication_plugin=mysql_native_password\nskip-name-resolve\nexplicit_defaults_for_timestamp\nbasedir=/opt/bitnami/mysql\nplugin_dir=/opt/bitnami/mysql/lib/plugin\nport=3306\nsocket=/opt/bitnami/mysql/tmp/mysql.sock\ndatadir=/bitnami/mysql/data\ntmpdir=/opt/bitnami/mysql/tmp\nmax_allowed_packet=16M\nbind-address=*\npid-file=/opt/bitnami/mysql/tmp/mysqld.pid\nlog-error=/opt/bitnami/mysql/logs/mysqld.log\ncharacter-set-server=UTF8\nslow_query_log=0\nlong_query_time=10.0\n\n[client]\nport=3306\nsocket=/opt/bitnami/mysql/tmp/mysql.sock\ndefault-character-set=UTF8\nplugin_dir=/opt/bitnami/mysql/lib/plugin\n\n[manager]\nport=3306\nsocket=/opt/bitnami/mysql/tmp/mysql.sock\npid-file=/opt/bitnami/mysql/tmp/mysqld.pid"` |  |
| mysql.secondary.containerSecurityContext.allowPrivilegeEscalation | bool | `false` |  |
| mysql.secondary.containerSecurityContext.capabilities.drop[0] | string | `"ALL"` |  |
| mysql.secondary.containerSecurityContext.enabled | bool | `true` |  |
| mysql.secondary.containerSecurityContext.runAsNonRoot | bool | `true` |  |
| mysql.secondary.containerSecurityContext.runAsUser | int | `1001` |  |
| mysql.secondary.containerSecurityContext.seccompProfile.type | string | `"RuntimeDefault"` |  |
| mysql.secondary.customLivenessProbe | object | `{}` |  |
| mysql.secondary.customReadinessProbe | object | `{}` |  |
| mysql.secondary.customStartupProbe | object | `{}` |  |
| mysql.secondary.existingConfigmap | string | `""` |  |
| mysql.secondary.extraEnvVars | list | `[]` |  |
| mysql.secondary.extraEnvVarsCM | string | `""` |  |
| mysql.secondary.extraEnvVarsSecret | string | `""` |  |
| mysql.secondary.extraFlags | string | `""` |  |
| mysql.secondary.extraPodSpec | object | `{}` |  |
| mysql.secondary.extraPorts | list | `[]` |  |
| mysql.secondary.extraVolumeMounts | list | `[]` |  |
| mysql.secondary.extraVolumes | list | `[]` |  |
| mysql.secondary.hostAliases | list | `[]` |  |
| mysql.secondary.initContainers | list | `[]` |  |
| mysql.secondary.lifecycleHooks | object | `{}` |  |
| mysql.secondary.livenessProbe.enabled | bool | `true` |  |
| mysql.secondary.livenessProbe.failureThreshold | int | `3` |  |
| mysql.secondary.livenessProbe.initialDelaySeconds | int | `5` |  |
| mysql.secondary.livenessProbe.periodSeconds | int | `10` |  |
| mysql.secondary.livenessProbe.successThreshold | int | `1` |  |
| mysql.secondary.livenessProbe.timeoutSeconds | int | `1` |  |
| mysql.secondary.name | string | `"secondary"` |  |
| mysql.secondary.nodeAffinityPreset.key | string | `""` |  |
| mysql.secondary.nodeAffinityPreset.type | string | `""` |  |
| mysql.secondary.nodeAffinityPreset.values | list | `[]` |  |
| mysql.secondary.nodeSelector | object | `{}` |  |
| mysql.secondary.pdb.create | bool | `false` |  |
| mysql.secondary.pdb.maxUnavailable | string | `""` |  |
| mysql.secondary.pdb.minAvailable | int | `1` |  |
| mysql.secondary.persistence.accessModes[0] | string | `"ReadWriteOnce"` |  |
| mysql.secondary.persistence.annotations | object | `{}` |  |
| mysql.secondary.persistence.enabled | bool | `true` |  |
| mysql.secondary.persistence.existingClaim | string | `""` |  |
| mysql.secondary.persistence.selector | object | `{}` |  |
| mysql.secondary.persistence.size | string | `"8Gi"` |  |
| mysql.secondary.persistence.storageClass | string | `""` |  |
| mysql.secondary.persistence.subPath | string | `""` |  |
| mysql.secondary.persistentVolumeClaimRetentionPolicy.enabled | bool | `false` |  |
| mysql.secondary.persistentVolumeClaimRetentionPolicy.whenDeleted | string | `"Retain"` |  |
| mysql.secondary.persistentVolumeClaimRetentionPolicy.whenScaled | string | `"Retain"` |  |
| mysql.secondary.podAffinityPreset | string | `""` |  |
| mysql.secondary.podAnnotations | object | `{}` |  |
| mysql.secondary.podAntiAffinityPreset | string | `"soft"` |  |
| mysql.secondary.podLabels | object | `{}` |  |
| mysql.secondary.podManagementPolicy | string | `""` |  |
| mysql.secondary.podSecurityContext.enabled | bool | `true` |  |
| mysql.secondary.podSecurityContext.fsGroup | int | `1001` |  |
| mysql.secondary.priorityClassName | string | `""` |  |
| mysql.secondary.readinessProbe.enabled | bool | `true` |  |
| mysql.secondary.readinessProbe.failureThreshold | int | `3` |  |
| mysql.secondary.readinessProbe.initialDelaySeconds | int | `5` |  |
| mysql.secondary.readinessProbe.periodSeconds | int | `10` |  |
| mysql.secondary.readinessProbe.successThreshold | int | `1` |  |
| mysql.secondary.readinessProbe.timeoutSeconds | int | `1` |  |
| mysql.secondary.replicaCount | int | `1` |  |
| mysql.secondary.resources.limits | object | `{}` |  |
| mysql.secondary.resources.requests | object | `{}` |  |
| mysql.secondary.runtimeClassName | string | `""` |  |
| mysql.secondary.schedulerName | string | `""` |  |
| mysql.secondary.service.annotations | object | `{}` |  |
| mysql.secondary.service.clusterIP | string | `""` |  |
| mysql.secondary.service.externalTrafficPolicy | string | `"Cluster"` |  |
| mysql.secondary.service.extraPorts | list | `[]` |  |
| mysql.secondary.service.headless.annotations | object | `{}` |  |
| mysql.secondary.service.loadBalancerIP | string | `""` |  |
| mysql.secondary.service.loadBalancerSourceRanges | list | `[]` |  |
| mysql.secondary.service.nodePorts.mysql | string | `""` |  |
| mysql.secondary.service.ports.mysql | int | `3306` |  |
| mysql.secondary.service.sessionAffinity | string | `"None"` |  |
| mysql.secondary.service.sessionAffinityConfig | object | `{}` |  |
| mysql.secondary.service.type | string | `"ClusterIP"` |  |
| mysql.secondary.sidecars | list | `[]` |  |
| mysql.secondary.startupProbe.enabled | bool | `true` |  |
| mysql.secondary.startupProbe.failureThreshold | int | `15` |  |
| mysql.secondary.startupProbe.initialDelaySeconds | int | `15` |  |
| mysql.secondary.startupProbe.periodSeconds | int | `10` |  |
| mysql.secondary.startupProbe.successThreshold | int | `1` |  |
| mysql.secondary.startupProbe.timeoutSeconds | int | `1` |  |
| mysql.secondary.terminationGracePeriodSeconds | string | `""` |  |
| mysql.secondary.tolerations | list | `[]` |  |
| mysql.secondary.topologySpreadConstraints | list | `[]` |  |
| mysql.secondary.updateStrategy.type | string | `"RollingUpdate"` |  |
| mysql.serviceAccount.annotations | object | `{}` |  |
| mysql.serviceAccount.automountServiceAccountToken | bool | `true` |  |
| mysql.serviceAccount.create | bool | `true` |  |
| mysql.serviceAccount.name | string | `""` |  |
| mysql.serviceBindings.enabled | bool | `false` |  |
| mysql.startdbScripts | object | `{}` |  |
| mysql.startdbScriptsConfigMap | string | `""` |  |
| mysql.volumePermissions.enabled | bool | `false` |  |
| mysql.volumePermissions.image.digest | string | `""` |  |
| mysql.volumePermissions.image.pullPolicy | string | `"IfNotPresent"` |  |
| mysql.volumePermissions.image.pullSecrets | list | `[]` |  |
| mysql.volumePermissions.image.registry | string | `"docker.io"` |  |
| mysql.volumePermissions.image.repository | string | `"bitnami/os-shell"` |  |
| mysql.volumePermissions.image.tag | string | `"11-debian-11-r91"` |  |
| mysql.volumePermissions.resources | object | `{}` |  |
| name | string | `"ghost"` | Sets Ghost name |
| nameOverride | string | `""` | Ghost Override name of helm release |
| nodeSelector | object | `{}` | Sets Ghost node selector |
| persistentVolumeClaim | object | `{"accessModes":"ReadWriteOnce","enabled":true,"storageClassName":"local-path","storageSize":"5Gi"}` | Claim desired amount of storage from respective storage class |
| podAnnotations | object | `{}` | Ghost Pod Annotations |
| podSecurityContext | object | `{}` | Sets Ghost Pod Security Context |
| podSecurityPolicy | object | `{"annotations":{"seccomp.security.alpha.kubernetes.io/allowedProfileNames":"*"},"enabled":false,"spec":{"allowPrivilegeEscalation":false,"fsGroup":{"rule":"RunAsAny"},"hostIPC":false,"hostNetwork":false,"hostPID":false,"privileged":false,"readOnlyRootFilesystem":true,"requiredDropCapabilities":["ALL"],"runAsGroup":{"rule":"RunAsAny"},"runAsUser":{"rule":"RunAsAny"},"seLinux":{"rule":"RunAsAny"},"supplementalGroups":{"rule":"RunAsAny"},"volumes":["configMap","emptyDir","projected","secret","downwardAPI","persistentVolumeClaim"]}}` | Sets Ghost Pod Security Policy |
| podSecurityPolicy.spec.allowPrivilegeEscalation | bool | `false` | Required to prevent escalations to root. |
| podSecurityPolicy.spec.requiredDropCapabilities | list | `["ALL"]` | This is redundant with non-root + disallow privilege escalation, but we can provide it for defense in depth. |
| podSecurityPolicy.spec.seLinux.rule | string | `"RunAsAny"` | This policy assumes the nodes are using AppArmor rather than SELinux. |
| podSecurityPolicy.spec.volumes | list | `["configMap","emptyDir","projected","secret","downwardAPI","persistentVolumeClaim"]` | Allow core volume types. |
| podSecurityPolicy.spec.volumes[5] | string | `"persistentVolumeClaim"` | Assume that persistentVolumes set up by the cluster admin are safe to use. |
| rbac | object | `{"create":true}` | Create rbac |
| replicas | int | `1` | Sets Ghost replicas |
| resources | object | `{"limits":{"cpu":"500m","memory":"500Mi"},"requests":{"cpu":"500m","memory":"500Mi"}}` | Sets Ghost CPU and Memory Limits |
| resources.limits | object | `{"cpu":"500m","memory":"500Mi"}` | Sets threshold maximum allocated resources |
| resources.requests | object | `{"cpu":"500m","memory":"500Mi"}` | Sets minimum allocated resources |
| securityContext | object | `{}` | Sets Ghost Security Context |
| service | object | `{"annotations":{},"enableHttp":true,"enableHttps":true,"enabled":true,"externalIPs":[],"externalTrafficPolicy":"","healthCheckNodePort":0,"labels":{},"loadBalancerIP":"","loadBalancerSourceRanges":[],"name":"ghost","nodePorts":{"grpc":"","http":"","https":"","tcp":{},"udp":{}},"omitClusterIP":false,"ports":{"http":80,"https":443},"sessionAffinity":"","targetPorts":{"http":"http","https":"http"},"type":"ClusterIP"}` | Sets Ghost Service config |
| service.externalIPs | list | `[]` | Ref: https://kubernetes.io/docs/user-guide/services/#external-ips |
| service.externalTrafficPolicy | string | `""` | Ref: https://kubernetes.io/docs/tutorials/services/source-ip/#source-ip-for-services-with-typeloadbalancer |
| service.nodePorts | object | `{"grpc":"","http":"","https":"","tcp":{},"udp":{}}` | Example for setting node port type: NodePort nodePorts:   http: 32080   https: 32443   grpc: 32143   tcp:     8080: 32808 |
| service.omitClusterIP | bool | `false` | Deprecated, instead simply do not provide a clusterIP value |
| service.sessionAffinity | string | `""` | Ref: https://kubernetes.io/docs/concepts/services-networking/service/#virtual-ips-and-service-proxies |
| serviceAccount | object | `{"annotations":{},"create":true,"name":null}` | Ghost service account creation |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |
| serviceAccount.name | string | `nil` | If not set and create is true, a name is generated using the fullname template |
| strategy | object | `{"type":"RollingUpdate"}` | Ghost Scaling strategy |
| targetPortName | string | `"http"` | Sets Ghost Container Port Details |
| tolerations | list | `[]` | Sets Ghost tolerations |
| volumeMounts | list | `[{"mountPath":"/var/lib/ghost/content","name":"ghost"}]` | Sets Ghost Additional volumeMounts |

