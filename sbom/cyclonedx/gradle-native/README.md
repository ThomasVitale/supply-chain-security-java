# SBOM for Java Native applications using Gradle and CycloneDX

## Generating a SBOM for a GraalVM native executable

```shell
./gradlew nativeCompile
```

## Scanning a GraalVM SBOM for vulnerabilities with Trivy

```shell
trivy sbom build/native/nativeCompile/demo-sbom-cdx-gradle-native.sbom.json
```
