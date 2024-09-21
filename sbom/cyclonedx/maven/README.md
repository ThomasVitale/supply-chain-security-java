# SBOM for Java applications using Maven and CycloneDX

## Generating a SBOM from an artifact using Syft

```shell
./mvnw package
syft target/demo-sbom-cdx-maven-1.0.jar -o cyclonedx-json --file bom-syft.cdx.json
```

## Generating a SBOM from a container image using Syft

```shell
./mvnw spring-boot:build-image
syft demo-sbom-cdx-maven:1.0 -o cyclonedx-json --file bom-oci-syft.cdx.json
```

## Generating a SBOM from the source code using cdxgen

```shell
FETCH_LICENSE=true cdxgen -o bom-cdxgen.cdx.json --spec-version 1.6
```

## Generating a SBOM at build time using CycloneDX

```shell
./mvnw package
```

## Scanning a SBOM for security vulnerabilities with Trivy

```shell
trivy sbom target/classes/META-INF/sbom/application.cdx.json
```

## Verifying the quality of a SBOM with sbomqs

```shell
sbomqs score target/classes/META-INF/sbom/application.cdx.json
```
