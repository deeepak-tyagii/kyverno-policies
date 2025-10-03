# A Curated Collection of Kyverno Policies

This repository is a curated collection of Kyverno policies designed to enforce security best practices and improve the reliability of your Kubernetes environments. Policies are organized into three tiers: essential (**must-have**), recommended (**nice-to-have**), and **optional**, allowing for flexible adoption by any project.

## Table of Contents

  - [🔴 Must Have Policies](#must-have)
      - [Pod Security Standards (Baseline & Restricted)](#psp)
      - [Resource Management](#resource-management)
      - [Image Security](#image-security)
      - [Access Control](#access-control)
      - [Network Security](#network-security)
  - [🟡 Nice to Have Policies](#nice-to-have)
       - [Security Context](#security-context)
      - [Image Verification](#image-verification)
      - [Workload Security](#workload-security)
      - [Multi-Tenancy](#multi-tenancy)
  - [🟢 Optional Policies](#optional)
      - [Cloud Integrations - EKS Best Practices](#cloud-integrations)
      - [Service Mesh](#service-mesh)
      - [Compliance](#compliance)
      - [Development](#development)
      - [Advanced Security](#advanced-security)
      - [Workload Optimization](#workload-optimization)
      - [Certificate Management](#certificate-management)
      - [Networking](#networking)
  - [🚀 How to Use](#how-to-use)
  - [🤝 Contributing](#contributing)

-----
<a name="must-have"></a>
## 🔴 Must-Have Policies

These policies are considered essential for establishing a baseline security and reliability posture in any Kubernetes cluster.
<a name="psp"></a>
### Pod Security Standards (Baseline & Restricted)

These policies enforce a secure context for running pods, aligning with the official Kubernetes Pod Security Standards.

| Policy | Kyverno Documentation | YAML File |
| :--- | :--- | :--- |
| **Disallow Host Namespaces** | [Official Link](https://kyverno.io/policies/pod-security/baseline/disallow-host-namespaces/disallow-host-namespaces/) | [`Link`](must-have/pod-security-standards/disallow-host-namespaces.yaml) |
| **Disallow Host Ports** | [Official Link](https://kyverno.io/policies/pod-security/baseline/disallow-host-ports/disallow-host-ports/) | [`Link`](must-have/pod-security-standards/disallow-hostPorts.yaml) |
| **Disallow hostPath Volumes** | [Official Link](https://kyverno.io/policies/pod-security/baseline/disallow-host-path/disallow-host-path/) | [`Link`](must-have/pod-security-standards/disallow-hostPath.yaml) |
| **Disallow Privileged Containers** | [Official Link](https://kyverno.io/policies/pod-security/baseline/disallow-privileged-containers/disallow-privileged-containers/) | [`Link`](must-have/pod-security-standards/disallow-privileged-containers.yaml) |
| **Require runAsNonRoot** | [Official Link](https://kyverno.io/policies/pod-security/restricted/require-run-as-nonroot/require-run-as-nonroot/) | [`Link`](must-have/pod-security-standards/require-runAsNonRoot.yaml) |
| **Drop All Capabilities** | [Official Link](https://kyverno.io/policies/best-practices/require-drop-all/require-drop-all/) | [`Link`](must-have/pod-security-standards/drop-all-capabilities.yaml) |
| **Drop CAP\_NET\_RAW** | [Official Link](https://kyverno.io/policies/best-practices/require-drop-cap-net-raw/require-drop-cap-net-raw/) | [`Link`](must-have/pod-security-standards/drop-CAP_NET_RAW.yaml) |
| **Disallow Capabilities (Strict)** | [Official Link](https://kyverno.io/policies/pod-security/restricted/disallow-capabilities-strict/disallow-capabilities-strict/) | [`Link`](must-have/pod-security-standards/disallow-capabilities-strict.yaml) |
| **Restrict Volume Types** | [Official Link](https://kyverno.io/policies/pod-security/restricted/restrict-volume-types/restrict-volume-types/) | [`Link`](must-have/pod-security-standards/restrict-volume-types.yaml) |
| **Restrict Seccomp** | [Official Link](https://kyverno.io/policies/pod-security/baseline/restrict-seccomp/restrict-seccomp/) | [`Link`](must-have/pod-security-standards/restrict-seccomp.yaml) |
<a name="resource-management"></a>
### Resource Management

Ensure that all workloads are good cluster citizens by defining resource requests and limits.

| Policy | Kyverno Documentation | YAML File |
| :--- | :--- | :--- |
| **Require Pod Requests and Limits** | [Official Link](https://kyverno.io/policies/best-practices/require-pod-requests-limits/require-pod-requests-limits/) | [`Link`](must-have/resource-management/require-pod-requests-and-limits.yaml) |
| **Add Default Resources** | [Official Link](https://kyverno.io/policies/other/add-default-resources/add-default-resources/) | [`Link`](must-have/resource-management/add-default-resources.yaml) |
| **Enforce Resources as Ratio** | [Official Link](https://kyverno.io/policies/other/enforce-resources-as-ratio/enforce-resources-as-ratio/) | [`Link`](must-have/resource-management/enforce-resources-as-ratio.yaml) |
| **Add emptyDir sizeLimit** | [Official Link](https://kyverno.io/policies/other/add-emptydir-sizelimit/add-emptydir-sizelimit/) | [`Link`](must-have/resource-management/add-emptyDir-sizeLimit.yaml) |
<a name="image-security"></a>
### Image Security

Control the container images running in your cluster to prevent known vulnerabilities and ensure they originate from trusted sources.

| Policy | Kyverno Documentation | YAML File |
| :--- | :--- | :--- |
| **Disallow Latest Tag** | [Official Link](https://kyverno.io/policies/best-practices/disallow-latest-tag/disallow-latest-tag/) | [`Link`](must-have/image-security/disallow-latest-tag.yaml) |
| **Restrict Image Registries** | [Official Link](https://kyverno.io/policies/best-practices/restrict-image-registries/restrict-image-registries/) | [`Link`](must-have/image-security/restrict-image-registries.yaml) |
| **Check Image Base** | [Official Link](https://kyverno.io/policies/other/require-base-image/require-base-image/) | [`Link`](must-have/image-security/check-image-base.yaml) |
| **Block Stale Images** | [Official Link](https://kyverno.io/policies/other/block-stale-images/block-stale-images/) | [`Link`](must-have/image-security/block-stale-images.yaml) |
| **Block Large Images** | [Official Link](https://kyverno.io/policies/other/block-large-images/block-large-images/) | [`Link`](must-have/image-security/block-large-images.yaml) |
<a name="access-control"></a>
### Access Control

Enforce the principle of least privilege for service accounts and avoid using insecure defaults.

| Policy | Kyverno Documentation | YAML File |
| :--- | :--- | :--- |
| **Disallow Default Namespace** | [Official Link](https://kyverno.io/policies/best-practices/disallow-default-namespace/disallow-default-namespace/) | [`Link`](must-have/access-control/disallow-default-namespace.yaml) |
| **Check ServiceAccount** | [Official Link](https://kyverno.io/policies/other/check-serviceaccount/check-serviceaccount/) | [`Link`](must-have/access-control/check-serviceAccount.yaml) |
| **Check Long-Lived Secrets in ServiceAccounts** | [Official Link](https://kyverno.io/policies/other/check-serviceaccount-secrets/check-serviceaccount-secrets/) | [`Link`](must-have/access-control/check-long-lived-secrets-in-serviceAccounts.yaml) |
| **Disallow automountServiceAccountToken** | [Official Link](https://kyverno.io/policies/other/disable-automountserviceaccounttoken/disable-automountserviceaccounttoken/) | [`Link`](must-have/access-control/disallow-automountServiceAccountToken.yaml) |
<a name="network-security"></a>
### Network Security

Implement baseline network controls to isolate workloads and reduce the attack surface.

| Policy | Kyverno Documentation | YAML File |
| :--- | :--- | :--- |
| **Add Network Policy (Default-Deny)** | [Official Link](https://kyverno.io/policies/best-practices/add-network-policy/add-network-policy/) | [`Link`](must-have/network-security/add-network-policy-(Default-Deny).yaml) |
| **Add Network Policy for DNS** | [Official Link](https://kyverno.io/policies/best-practices/add-networkpolicy-dns/add-networkpolicy-dns/) | [`Link`](must-have/network-security/add-network-policy-for-DNS.yaml) |
| **Disallow NodePort** | [Official Link](https://kyverno.io/policies/best-practices/restrict-node-port/restrict-node-port/) | [`Link`](must-have/network-security/disallow-nodePort.yaml) |
| **Disallow Localhost ExternalName Services** | [Official Link](https://kyverno.io/policies/other/disallow-localhost-services/disallow-localhost-services/) | [`Link`](must-have/network-security/disallow-localhost-ExternalName-services.yaml) |

-----
<a name="nice-to-have"></a>
## 🟡 Nice-to-Have Policies

These policies are recommended to further harden your environment and adopt more advanced best practices.

<a name="security-context"></a>

### Security Context

Apply additional security constraints to workloads.

| Policy | Kyverno Documentation | YAML File |
| :--- | :--- | :--- |
| **Add Default securityContext** | [Official Link](https://kyverno.io/policies/other/add-default-securitycontext/add-default-securitycontext/) | [`Link`](nice-to-have/security-context/add-default-securityContext.yaml) |
| **Check supplementalGroups** | [Official Link](https://kyverno.io/policies/psp-migration/check-supplemental-groups/check-supplemental-groups/) | [`Link`](nice-to-have/security-context/check-supplementalGroups.yaml) |
| **Disallow CRI socket mounts** | [Official Link](https://kyverno.io/policies/best-practices/disallow-cri-sock-mount/disallow-cri-sock-mount/) | [`Link`](nice-to-have/security-context/disallow-CRI-socket-mounts.yaml) |

<a name="image-verification"></a>

### Image Verification

Ensure container images are signed and free from critical vulnerabilities.

| Policy | Kyverno Documentation | YAML File |
| :--- | :--- | :--- |
| **Verify Image** | [Official Link](https://kyverno.io/policies/other/verify-image/verify-image/) | [`Link`](nice-to-have/image-verification/verify-image.yaml) |
| **Check Image for CVEs** | [Official Link](https://kyverno.io/policies/other/verify-image-cve-2022-42889/verify-image-cve-2022-42889/) | [`Link`](nice-to-have/image-verification/verify-image-check-CVE-2022-42889.yaml) |
| **Allowed Base Images** | [Official Link](https://kyverno.io/policies/other/allowed-base-images/allowed-base-images/) | [`Link`](nice-to-have/image-verification/allowed-base-images.yaml) |
| **Annotate Base Images** | [Official Link](https://kyverno.io/policies/other/annotate-base-images/annotate-base-images/) | [`Link`](nice-to-have/image-verification/annotate-base-images.yaml) |

<a name="workload-security"></a>

### Workload Security

Enforce best practices for workload configurations and runtime behavior.

| Policy | Kyverno Documentation | YAML File |
| :--- | :--- | :--- |
| **Always Pull Images** | [Official Link](https://kyverno.io/policies/other/always-pull-images/always-pull-images/) | [`Link`](nice-to-have/workload-security/always-pull-images.yaml) |
| **Add Safe To Evict** | [Official Link](https://kyverno.io/policies/best-practices/add-safe-to-evict/add-safe-to-evict/) | [`Link`](nice-to-have/workload-security/add-safe-to-evict.yaml) |
| **Block Ephemeral Containers** | [Official Link](https://kyverno.io/policies/other/block-ephemeral-containers/block-ephemeral-containers/) | [`Link`](nice-to-have/workload-security/block-ephemeral-containers.yaml) |
| **Add runtimeClassName** | [Official Link](https://kyverno.io/policies/psp-migration/add-runtimeclassname/add-runtimeclassname/) | [`Link`](nice-to-have/workload-security/add-runtimeClassname.yaml) |

<a name="multi-tenancy"></a>

### Multi-Tenancy

Policies that help manage resources and permissions in a shared cluster environment.

| Policy | Kyverno Documentation | YAML File |
| :--- | :--- | :--- |
| **Add Quota** | [Official Link](https://kyverno.io/policies/best-practices/add-ns-quota/add-ns-quota/) | [`Link`](nice-to-have/multi-tenancy/add-quota.yaml) |
| **Add RoleBinding** | [Official Link](https://kyverno.io/policies/best-practices/add-rolebinding/add-rolebinding/) | [`Link`](nice-to-have/multi-tenancy/add-roleBinding.yaml) |
| **Add PSA Labels** | [Official Link](https://kyverno.io/policies/psa/add-psa-labels/add-psa-labels/) | [`Link`](nice-to-have/multi-tenancy/add-PSA-labels.yaml) |
| **Copy Namespace Labels** | [Official Link](https://kyverno.io/policies/other/copy-namespace-labels/copy-namespace-labels/) | [`Link`](nice-to-have/multi-tenancy/copy-namespace-labels.yaml) |

-----

<a name="optional"></a>
## 🟢 Optional Policies

These are situational policies that can be applied based on specific use cases, tools, or compliance requirements.

<a name="cloud-integrations"></a>
### Cloud Integrations

**EKS Best Practices**
| Policy | Kyverno Documentation | YAML File |
| :--- | :--- | :--- |
| **Require Pod priorityClassName** | [Official Link](https://kyverno.io/policies/other/require-pod-priorityclassname/require-pod-priorityclassname/) | [`Link`](optional/cloud-integrations/eks-best-practices/require-pod-priorityClassName.yaml) |
| **Karpenter Do Not Evict** | [Official Link](https://kyverno.io/policies/karpenter/add-karpenter-donot-evict/add-karpenter-donot-evict/) | [`Link`](optional/cloud-integrations/eks-best-practices/add-karpenter-do-not-evict.yaml) |
| **Karpenter nodeSelector** | [Official Link](https://kyverno.io/policies/karpenter/add-karpenter-nodeselector/add-karpenter-nodeselector/) | [`Link`](optional/cloud-integrations/eks-best-practices/add-karpenter-nodeSelector.yaml) |

<a name="service-mesh"></a>

### Service Mesh

| Policy | Kyverno Documentation | YAML File |
| :--- | :--- | :--- |
| **Add Istio Sidecar Injection** | [Official Link](https://kyverno.io/policies/istio/add-sidecar-injection-namespace/add-sidecar-injection-namespace/) | [`Link`](optional/istio-service-mesh/add-istio-sidecar-injection.yaml) |
| **Enforce Istio Strict mTLS** | [Official Link](https://kyverno.io/policies/istio/enforce-strict-mtls/enforce-strict-mtls/) | [`Link`](optional/istio-service-mesh/enforce-istio-strict-mTLS.yaml) |
| **Add Istio Ambient Mode** | [Official Link](https://kyverno.io/policies/istio/add-ambient-mode-namespace/add-ambient-mode-namespace/) | [`Link`](optional/istio-service-mesh/add-istio-ambient-mode.yaml) |
| **Create Deny AuthorizationPolicy** | [Official Link](https://kyverno.io/policies/istio/create-authorizationpolicy/create-authorizationpolicy/) | [`Link`](optional/istio-service-mesh/create-deny-authorizationPolicy.yaml) |

<a name="compliance"></a>

### Compliance

| Policy | Kyverno Documentation | YAML File |
| :--- | :--- | :--- |
| **Add PSA Namespace Reporting** | [Official Link](https://kyverno.io/policies/psa/add-psa-namespace-reporting/add-psa-namespace-reporting/) | [`Link`](optional/compliance/add-PSA-namespace-reporting.yaml) |
| **Check deprecated APIs** | [Official Link](https://kyverno.io/policies/best-practices/check-deprecated-apis/check-deprecated-apis/) | [`Link`](optional/compliance/check-deprecated-APIs.yaml) |
| **Audit Event on Delete** | [Official Link](https://kyverno.io/policies/other/audit-event-on-delete/audit-event-on-delete/) | [`Link`](optional/compliance/audit-event-on-delete.yaml) |

<a name="development"></a>

### Development

| Policy | Kyverno Documentation | YAML File |
| :--- | :--- | :--- | 
| **Add Environment Variables from ConfigMap** | [Official Link](https://kyverno.io/policies/other/add-env-vars-from-cm/add-env-vars-from-cm/) | [`Link`](optional/developement/add-environment-variables-from-configMap.yaml) |
| **Add TTL to Jobs** | [Official Link](https://kyverno.io/policies/other/add-ttl-jobs/add-ttl-jobs/) | [`Link`](optional/developement/add-ttl-to-jobs.yaml) |
| **Cleanup Bare Pods** | [Official Link](https://kyverno.io/policies/cleanup/cleanup-bare-pods/cleanup-bare-pods/) | [`Link`](optional/developement/cleanup-bare-pods.yaml) |
| **Cleanup Empty ReplicaSets** | [Official Link](https://kyverno.io/policies/cleanup/cleanup-empty-replicasets/cleanup-empty-replicasets/) | [`Link`](optional/developement/cleanup-empty-replicaSets.yaml) |

<a name="advanced-security"></a>

### Advanced Security

| Policy | Kyverno Documentation | YAML File |
| :--- | :--- | :--- |
| **Block Pod Exec by Namespace Label** | [Official Link](https://kyverno.io/policies/other/block-pod-exec-by-namespace-label/block-pod-exec-by-namespace-label/) | [`Link`](optional/advanced-security/block-pod-exec-by-namespace-label.yaml) |
| **Disallow All Secrets** | [Official Link](https://kyverno.io/policies/other/disallow-all-secrets/disallow-all-secrets/) | [`Link`](optional/advanced-security/disallow-all-secrets.yaml) |
| **Docker Socket Requires Label** | [Official Link](https://kyverno.io/policies/other/docker-socket-requires-label/docker-socket-requires-label/) | [`Link`](optional/advanced-security/docker-socket-requires-label.yaml) |

<a name="workload-optimization"></a>

### Workload Optimization

| Policy | Kyverno Documentation | YAML File |
| :--- | :--- | :--- |
| **Add Pod Anti-Affinity** | [Official Link](https://kyverno.io/policies/other/create-pod-antiaffinity/create-pod-antiaffinity/) | [`Link`](optional/workload-optimization/add-pod-anti-affinity.yaml) |
| **Add Pod Disruption Budget** | [Official Link](https://kyverno.io/policies/other/create-default-pdb/create-default-pdb/) | [`Link`](optional/workload-optimization/add-pod-disruption-budget.yaml) |
| **Add Tolerations** | [Official Link](https://kyverno.io/policies/other/add-tolerations/add-tolerations/) | [`Link`](optional/workload-optimization/add-tolerations.yaml) |
| **Check PDB minAvailable** | [Official Link](https://kyverno.io/policies/other/pdb-minavailable/pdb-minavailable/) | [`Link`](optional/workload-optimization/check-PDB-minavailable.yaml) |

<a name="certificate-management"></a>

### Certificate Management

| Policy | Kyverno Documentation | YAML File |
| :--- | :--- | :--- |
| **Certificate max duration 100 days** | [Official Link](https://kyverno.io/policies/cert-manager/limit-duration/limit-duration/) | [`Link`](optional/certificate-management/certificate-max-duration-100-days.yaml) |
| **Add Certificates as Volume** | [Official Link](https://kyverno.io/policies/other/add-certificates-volume/add-certificates-volume/) | [`Link`](optional/certificate-management/add-certificates-as-volume.yaml) |

<a name="networking"></a>

### Networking

| Policy | Kyverno Documentation | YAML File |
| :--- | :--- | :--- |
| **Add ndots Option** | [Official Link](https://kyverno.io/policies/other/add-ndots/add-ndots/) | [`Link`](optional/networking/add-ndots.yaml) |
| **Change DNS Config and Policy** | [Official Link](https://kyverno.io/policies/other/dns-policy-and-dns-config/dns-policy-and-dns-config/) | [`Link`](optional/networking/change-DNS-config-and-policy.yaml) |
| **Disable Service Discovery** | [Official Link](https://kyverno.io/policies/other/disable-service-discovery/disable-service-discovery/) | [`Link`](optional/networking/disable-service-discovery.yaml) |


-----
<a name="how-to-use"></a>
## How to Use

### Prerequisites

1.  A running Kubernetes cluster.
2.  `kubectl` installed and configured.
3.  [Kyverno installed](https://kyverno.io/docs/installation/) in the cluster.

### Applying Policies

1.  **Clone the repository:**

    ```sh
    git clone https://github.com/deeepak-tyagii/kyverno-policies.git
    cd kyverno-policies
    ```

2.  **Apply a single policy:**

    ```sh
    # Example: Apply the 'disallow-latest-tag' policy
    kubectl apply -f must-have/image-security/disallow-latest-tag.yaml
    ```

3.  **Apply all policies in a category:**

    ```sh
    # Example: Apply all 'must-have' pod security policies
    kubectl apply -f must-have/pod-security/
    ```

-----
<a name="contributing"></a>
## Contributing

Contributions are welcome\! If you have a policy you'd like to add or an improvement to suggest, please feel free to open an issue or submit a pull request.

1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/your-new-policy`).
3.  Commit your changes (`git commit -m 'Add new policy: ...'`).
4.  Push to the branch (`git push origin feature/your-new-policy`).
5.  Open a pull request.

## License

This project is licensed under the [MIT License](https://www.google.com/search?q=./LICENSE).
