# A Curated Collection of Kyverno Policies

This repository is a curated collection of Kyverno policies designed to enforce security best practices and improve the reliability of your Kubernetes environments. Policies are organized into three tiers: essential (must-have), recommended (nice-to-have), and optional, allowing for flexible adoption by any project.

## Table of Contents

  - [🔴 Must-Have Policies](#must-have)
      - [Pod Security Standards (Baseline & Restricted)](###Resource-Management)
      - [Resource Management](https://www.google.com/search?q=%23resource-management)
      - [Image Security](https://www.google.com/search?q=%23image-security)
      - [Access Control](https://www.google.com/search?q=%23access-control)
      - [Network Security](https://www.google.com/search?q=%23network-security)
  - [🟡 Nice-to-Have Policies](https://www.google.com/search?q=%23nice-to-have-policies)
  - [🟢 Optional Policies](https://www.google.com/search?q=%23optional-policies)
  - [🚀 How to Use](https://www.google.com/search?q=%23how-to-use)
  - [🤝 Contributing](https://www.google.com/search?q=%23contributing)
  - [📄 License](https://www.google.com/search?q=%23license)

-----
<a name="must-have"></a>
## Must-Have Policies

These policies are considered essential for establishing a baseline security and reliability posture in any Kubernetes cluster.

### Pod Security Standards (Baseline & Restricted)

These policies enforce a secure context for running pods, aligning with the official Kubernetes Pod Security Standards.

| Policy | Kyverno Documentation | YAML File |
| :--- | :--- | :--- |
| **Disallow Host Namespaces** | [Official Link](https://kyverno.io/policies/pod-security/baseline/disallow-host-namespaces/disallow-host-namespaces/) | [`Link`](https://www.google.com/search?q=./must-have/pod-security/disallow-host-namespaces.yaml) |
| **Disallow Host Ports** | [Official Link](https://kyverno.io/policies/pod-security/baseline/disallow-host-ports/disallow-host-ports/) | [`Link`](https://www.google.com/search?q=./must-have/pod-security/disallow-host-ports.yaml) |
| **Disallow hostPath Volumes** | [Official Link](https://kyverno.io/policies/pod-security/baseline/disallow-host-path/disallow-host-path/) | [`Link`](https://www.google.com/search?q=./must-have/pod-security/disallow-host-path.yaml) |
| **Disallow Privileged Containers** | [Official Link](https://kyverno.io/policies/pod-security/baseline/disallow-privileged-containers/disallow-privileged-containers/) | [`Link`](https://www.google.com/search?q=./must-have/pod-security/disallow-privileged-containers.yaml) |
| **Require runAsNonRoot** | [Official Link](https://kyverno.io/policies/pod-security/restricted/require-run-as-nonroot/require-run-as-nonroot/) | [`Link`](https://www.google.com/search?q=./must-have/pod-security/require-run-as-nonroot.yaml) |
| **Drop All Capabilities** | [Official Link](https://kyverno.io/policies/best-practices/require-drop-all/require-drop-all/) | [`Link`](https://www.google.com/search?q=./must-have/pod-security/drop-all-capabilities.yaml) |
| **Drop CAP\_NET\_RAW** | [Official Link](https://kyverno.io/policies/best-practices/require-drop-cap-net-raw/require-drop-cap-net-raw/) | [`Link`](https://www.google.com/search?q=./must-have/pod-security/drop-cap-net-raw.yaml) |
| **Disallow Capabilities (Strict)** | [Official Link](https://kyverno.io/policies/pod-security/restricted/disallow-capabilities-strict/disallow-capabilities-strict/) | [`Link`](https://www.google.com/search?q=./must-have/pod-security/disallow-capabilities-strict.yaml) |
| **Restrict Volume Types** | [Official Link](https://kyverno.io/policies/pod-security/restricted/restrict-volume-types/restrict-volume-types/) | [`Link`](https://www.google.com/search?q=./must-have/pod-security/restrict-volume-types.yaml) |
| **Restrict Seccomp** | [Official Link](https://kyverno.io/policies/pod-security/baseline/restrict-seccomp/restrict-seccomp/) | [`Link`](https://www.google.com/search?q=./must-have/pod-security/restrict-seccomp.yaml) |

### Resource Management

Ensure that all workloads are good cluster citizens by defining resource requests and limits.

| Policy | Kyverno Documentation | YAML File |
| :--- | :--- | :--- |
| **Require Pod Requests and Limits** | [Official Link](https://kyverno.io/policies/best-practices/require-pod-requests-limits/require-pod-requests-limits/) | [`Link`](https://www.google.com/search?q=./must-have/resource-management/require-pod-requests-limits.yaml) |
| **Add Default Resources** | [Official Link](https://kyverno.io/policies/other/add-default-resources/add-default-resources/) | [`Link`](https://www.google.com/search?q=./must-have/resource-management/add-default-resources.yaml) |
| **Enforce Resources as Ratio** | [Official Link](https://kyverno.io/policies/other/enforce-resources-as-ratio/enforce-resources-as-ratio/) | [`Link`](https://www.google.com/search?q=./must-have/resource-management/enforce-resources-as-ratio.yaml) |
| **Add emptyDir sizeLimit** | [Official Link](https://kyverno.io/policies/other/add-emptydir-sizelimit/add-emptydir-sizelimit/) | [`Link`](https://www.google.com/search?q=./must-have/resource-management/add-emptydir-sizelimit.yaml) |

### Image Security

Control the container images running in your cluster to prevent known vulnerabilities and ensure they originate from trusted sources.

| Policy | Kyverno Documentation | YAML File |
| :--- | :--- | :--- |
| **Disallow Latest Tag** | [Official Link](https://kyverno.io/policies/best-practices/disallow-latest-tag/disallow-latest-tag/) | [`Link`](https://www.google.com/search?q=./must-have/image-security/disallow-latest-tag.yaml) |
| **Restrict Image Registries** | [Official Link](https://kyverno.io/policies/best-practices/restrict-image-registries/restrict-image-registries/) | [`Link`](https://www.google.com/search?q=./must-have/image-security/restrict-image-registries.yaml) |
| **Check Image Base** | [Official Link](https://kyverno.io/policies/other/require-base-image/require-base-image/) | [`Link`](https://www.google.com/search?q=./must-have/image-security/check-image-base.yaml) |
| **Block Stale Images** | [Official Link](https://kyverno.io/policies/other/block-stale-images/block-stale-images/) | [`Link`](https://www.google.com/search?q=./must-have/image-security/block-stale-images.yaml) |
| **Block Large Images** | [Official Link](https://kyverno.io/policies/other/block-large-images/block-large-images/) | [`Link`](https://www.google.com/search?q=./must-have/image-security/block-large-images.yaml) |

### Access Control

Enforce the principle of least privilege for service accounts and avoid using insecure defaults.

| Policy | Kyverno Documentation | YAML File |
| :--- | :--- | :--- |
| **Disallow Default Namespace** | [Official Link](https://kyverno.io/policies/best-practices/disallow-default-namespace/disallow-default-namespace/) | [`Link`](https://www.google.com/search?q=./must-have/access-control/disallow-default-namespace.yaml) |
| **Check ServiceAccount** | [Official Link](https://kyverno.io/policies/other/check-serviceaccount/check-serviceaccount/) | [`Link`](https://www.google.com/search?q=./must-have/access-control/check-serviceaccount.yaml) |
| **Check Long-Lived Secrets in ServiceAccounts** | [Official Link](https://kyverno.io/policies/other/check-serviceaccount-secrets/check-serviceaccount-secrets/) | [`Link`](https://www.google.com/search?q=./must-have/access-control/check-serviceaccount-secrets.yaml) |
| **Disallow automountServiceAccountToken** | [Official Link](https://kyverno.io/policies/other/disable-automountserviceaccounttoken/disable-automountserviceaccounttoken/) | [`Link`](https://www.google.com/search?q=./must-have/access-control/disallow-automountserviceaccounttoken.yaml) |

### Network Security

Implement baseline network controls to isolate workloads and reduce the attack surface.

| Policy | Kyverno Documentation | YAML File |
| :--- | :--- | :--- |
| **Add Network Policy (Default-Deny)** | [Official Link](https://kyverno.io/policies/best-practices/add-network-policy/add-network-policy/) | [`Link`](https://www.google.com/search?q=./must-have/network-security/add-network-policy-default-deny.yaml) |
| **Add Network Policy for DNS** | [Official Link](https://kyverno.io/policies/best-practices/add-networkpolicy-dns/add-networkpolicy-dns/) | [`Link`](https://www.google.com/search?q=./must-have/network-security/add-network-policy-dns.yaml) |
| **Disallow NodePort** | [Official Link](https://kyverno.io/policies/best-practices/restrict-node-port/restrict-node-port/) | [`Link`](https://www.google.com/search?q=./must-have/network-security/disallow-nodeport.yaml) |
| **Disallow Localhost ExternalName Services** | [Official Link](https://kyverno.io/policies/other/disallow-localhost-services/disallow-localhost-services/) | [`Link`](https://www.google.com/search?q=./must-have/network-security/disallow-localhost-externalname.yaml) |

-----

## Nice-to-Have Policies

> 📝 *Content for this section is coming soon.*

## Optional Policies

> 📝 *Content for this section is coming soon.*

-----

## How to Use

### Prerequisites

1.  A running Kubernetes cluster.
2.  `kubectl` installed and configured.
3.  [Kyverno installed](https://kyverno.io/docs/installation/) in the cluster.

### Applying Policies

1.  **Clone the repository:**

    ```sh
    git clone https://github.com/your-username/your-repo-name.git
    cd your-repo-name
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

## Contributing

Contributions are welcome\! If you have a policy you'd like to add or an improvement to suggest, please feel free to open an issue or submit a pull request.

1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/your-new-policy`).
3.  Commit your changes (`git commit -m 'Add new policy: ...'`).
4.  Push to the branch (`git push origin feature/your-new-policy`).
5.  Open a pull request.

## License

This project is licensed under the [MIT License](https://www.google.com/search?q=./LICENSE).
