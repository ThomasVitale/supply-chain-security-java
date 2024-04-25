# SBOM for Java Native applications using Maven and CycloneDX

## Generating a SBOM for a GraalVM native executable

```shell
./mvnw -Pnative native:compile
```

## Scanning a GraalVM SBOM for vulnerabilities with Trivy

```shell
trivy sbom target/demo-sbom-cdx-maven-native.sbom.json
```
