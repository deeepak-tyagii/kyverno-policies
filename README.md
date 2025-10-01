# A Curated Collection of Kyverno Policies

This repository is a curated collection of Kyverno policies designed to enforce security best practices and improve the reliability of your Kubernetes environments. Policies are organized into three tiers: essential (must-have), recommended (nice-to-have), and optional, allowing for flexible adoption by any project.

## Table of Contents

  - [🔴 Must-Have Policies](#must-have)
      - [Pod Security Standards (Baseline & Restricted)](#psp)
      - [Resource Management](#resource-management)
      - [Image Security](#image-security)
      - [Access Control](#access-control)
      - [Network Security](#network-security)
  - [🟡 Nice-to-Have Policies](#nice-to-have)
  - [🟢 Optional Policies](#optional)
  - [🚀 How to Use](#how-to-use)
  - [🤝 Contributing](#contributing)

-----
<a name="must-have"></a>
## Must-Have Policies

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
| **Disallow Capabilities (Strict)** | [Official Link](https://kyverno.io/policies/pod-security/restricted/disallow-capabilities-strict/disallow-capabilities-strict/) | [`Link`](https://www.google.com/search?q=./must-have/pod-security/disallow-capabilities-strict.yaml) |
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
## Nice-to-Have Policies

> 📝 *Content for this section is coming soon.*
<a name="optional"></a>
## Optional Policies

> 📝 *Content for this section is coming soon.*

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
