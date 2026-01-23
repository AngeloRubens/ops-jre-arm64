# The Cloud Evolves and Meets Unikernels: Java, Semeru Runtime, and Quarkus on ARM64 AWS Graviton with Nanos Unikernel

![Hero Image – Cloud, Java, and Unikernels](hero-image.png)

## Java and Jakarta EE Truly Meet Unikernels

The key message of this article is simple and strong:

**any Java or Jakarta EE application is already ready** to benefit from the advantages of unikernels.

Java and Jakarta EE, including modern frameworks such as Quarkus, can immediately take advantage of the unikernel model **without waiting for new languages, new runtimes, or radical rewrites**.

With **Nanos Unikernel**, Java applications run unchanged: the JVM is not modified, the application is not rewritten, and the well-known Java promise of *write once, run anywhere* remains fully valid — even in a unikernel environment.

This represents a major shift: unikernels are no longer a research topic or a niche experiment, but a **first-class deployment target** for enterprise Java workloads.

---

## From Virtual Machines and Containers to Unikernels

Cloud-native Java applications have traditionally been deployed on virtual machines and, more recently, inside containers orchestrated by Kubernetes. While containers brought improvements in portability and density, they also introduced additional layers of software complexity.

Unikernels remove these layers by compiling the application and its required runtime components into a **single-purpose, minimal image** that runs directly on a hypervisor.

With Nanos Unikernel, this model becomes practical for Java and Jakarta EE workloads.

---

## Proof of Concept Overview

This article builds on the original Foojay article, where the application image was executed on **Oracle Cloud Infrastructure (OCI)**. The goal of this Proof of Concept is to demonstrate that **the same Nanos Unikernel image can be deployed on a different cloud provider and hypervisor** without modification.

### PoC Environment

- **Cloud provider**: AWS
- **Instance type**: t4g.small (ARM64)
- **CPU**: AWS Graviton2
- **Hypervisor**: AWS Nitro
- **Unikernel**: Nanos (ARM64)
- **Runtime JAVA**: IBM Semeru Runtime 25 for Arm64 
- **Framework**: Quarkus

This demonstrates that Nanos unikernels are **hypervisor-agnostic** and cloud-independent.

---

## Architectural Diagram of the PoC

![PoC Architecture Diagram](poc-diagram.png)

The application runs as a single unikernel image directly on top of the AWS Nitro hypervisor, without a guest operating system, container runtime, or Kubernetes node.

---

## Containers vs Unikernels: A Stack Comparison

![Container vs Unikernel Stack](container-vs-unikernel.png)

### Container Stack

- Hardware
- Hypervisor
- Guest Operating System
- Container Runtime
- Container Image
- Java Runtime
- Application

### Unikernel Stack

- Hardware
- Hypervisor
- Unikernel (Application + Runtime)

By removing unnecessary layers, unikernels reduce boot time, memory footprint, and attack surface.

---

## Quarkus, Semeru, and Nanos on AWS Nitro Graviton

![Quarkus + Semeru + Nanos on AWS](quarkus-semeru-nanos.png)

Quarkus is particularly well suited for this model thanks to its fast startup and low memory usage, while IBM Semeru provides a production-grade OpenJDK runtime. Combined with Nanos, the result is a highly efficient Java unikernel.

---

## AWS Nitro: Cloud-Native Capabilities Without Kubernetes

AWS Nitro, like all modern hypervisors, already provides many of the foundational capabilities often associated with Kubernetes:

- Strong isolation and security boundaries
- Elastic scaling at the VM level
- High-performance networking and storage
- Hardware offloading for I/O and virtualization
- Integrated observability and telemetry
- Native IAM integration

Because these features are built directly into the cloud infrastructure, **there is no technical requirement to add additional orchestration layers** for many workloads.

Running Java applications as unikernels allows teams to:

- Exploit hardware more efficiently
- Reduce operational complexity
- Lower infrastructure and operational costs

---

## Hypervisor Independence

In the original article, the application image runs on the Oracle OCI hypervisor. In this Proof of Concept, the same image runs on AWS Nitro.

This confirms that Nanos unikernels are **not tied to a specific cloud provider or hypervisor**. The same Java application can be deployed consistently across environments.

---

## Why This Matters for Java and Jakarta EE

Java and Jakarta EE can benefit **today** from unikernel advantages:

- Faster boot times
- Smaller memory footprint
- Reduced attack surface
- Simpler deployment model

Most importantly, this comes **without changing existing applications or the JVM**.

Unikernels with Nanos represent an evolutionary step, not a disruptive rewrite, for the Java ecosystem.

---

## Conclusion

The cloud is evolving, and unikernels are becoming a practical deployment option for real-world workloads.

With Nanos Unikernel, Java, Jakarta EE, Quarkus, and IBM Semeru Runtime can fully exploit modern ARM64 cloud platforms such as AWS Graviton2 and the Nitro hypervisor — **today, without compromise**.
