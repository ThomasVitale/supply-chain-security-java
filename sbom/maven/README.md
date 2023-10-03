# SBOM for Java applications using Maven

## Generating a SBOM from an artifact using Syft

```shell
./mvnw package
syft target/demo-0.0.1-SNAPSHOT.jar -o cyclonedx-json --file bom-syft-cyclonedx.json
```

## Generating a SBOM from the source code using cdxgen

```shell
FETCH_LICENSE=true cdxgen -o bom-cdxgen-cyclonedx.json --spec-version 1.4
```

## Generating a SBOM at build time using CycloneDX

```shell
./mvnw package
```

## Scanning a SBOM for security vulnerabilities with Trivy

```shell
trivy sbom target/bom.json
```
