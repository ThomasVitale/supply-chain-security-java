# SBOM for Java applications using Gradle and CycloneDX

## Generating a SBOM from an artifact using Syft

```shell
./gradlew bootJar
syft build/libs/demo-sbom-cdx-gradle-1.0.jar -o cyclonedx-json --file bom-syft.cdx.json
```

## Generating a SBOM from the source code using cdxgen

```shell
FETCH_LICENSE=true cdxgen -o bom-cdxgen.cdx.json --spec-version 1.5
```

## Generating a SBOM at build time using CycloneDX

```shell
./gradlew build
```

## Scanning a SBOM for security vulnerabilities with Trivy

```shell
trivy sbom build/reports/bom.json
```

## Verifying the quality of a SBOM with sbomqs

```shell
sbomqs score build/reports/bom.json
```

## Generating a SBOM for a GraalVM native executable

```shell
./gradlew nativeCompile
```

## Scanning a GraalVM SBOM for vulnerabilities with Trivy

```shell
trivy sbom build/native/nativeCompile/demo-sbom-cdx-gradle.sbom.json
```
