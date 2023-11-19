# Supply Chain Security Java

Samples showing how to secure the supply chain for Java applications, including:

* SBOMs with CycloneDX and SPDX
* Dependency Management with Gradle and Maven
* Cryptographic signatures, policies, and SLSA

## Pre-requisites

* Java 21

## Devoxx Belgium 2023

[![Watch the video](https://img.youtube.com/vi/ftPFxK8JPNM/hqdefault.jpg)](https://www.youtube.com/embed/ftPFxK8JPNM)

Software supply chain security has never been more critical, and protecting our systems from bad actors and vulnerabilities is a constant challenge.

Do you know whether your Git commits are being manipulated without your knowledge? Are you confident that you have complete visibility of all the libraries and dependencies in your application JARs and container images? Can you trust the results of your vulnerability scanner? And how can you verify the integrity of your applications in production?

This presentation will show you how to secure the supply chain for your Java applications. We'll cover a range of techniques, patterns, and technologies for secure dependency management, source code integrity, safe builds, vulnerability scanning of Java source code and images, signing and verifying production artifacts, and patching strategies. We'll also explore options for handling supply chain security in a Kubernetes-native way.

But this isn't just a theoretical discussion. You'll see a live demonstration of the practices and technologies we'll discuss based on the cutting-edge SLSA framework and the CNCF WG Security research. We'll use open-source tools like Gradle, Sigstore, Cloud Native Buildpacks, Trivy, Syft, and Kyverno.
