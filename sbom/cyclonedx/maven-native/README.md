# SBOM for Java applications using Maven and CycloneDX

## Generating a SBOM from an artifact using Syft

```shell
./mvnw package
syft target/demo-sbom-cdx-maven-0.0.1-SNAPSHOT.jar -o cyclonedx-json --file bom-syft.cdx.json
```

## Generating a SBOM from the source code using cdxgen

```shell
FETCH_LICENSE=true cdxgen -o bom-cdxgen.cdx.json --spec-version 1.4
```

## Generating a SBOM at build time using CycloneDX

```shell
./mvnw package
```

## Scanning a SBOM for security vulnerabilities with Trivy

```shell
trivy sbom target/bom.json
```

## Verifying the quality of a SBOM with sbomqs

```shell
sbomqs score target/bom.json
```

## Generating a SBOM for a GraalVM native executable

```shell
./mvnw -Pnative native:compile
```

## Scanning a GraalVM SBOM for vulnerabilities with Trivy

```shell
trivy sbom target/demo-sbom-cdx-maven.sbom.json
```
