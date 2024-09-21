# SBOM for Java applications using Gradle and SPDX

## Generating a SBOM from an artifact using Syft

```shell
./gradlew clean bootJar
syft build/libs/demo-sbom-spdx-gradle-1.0.jar -o spdx-json --file bom-syft.spdx.json
```

## Generating a SBOM from a container image using Syft

```shell
./gradlew bootBuildImage
syft demo-sbom-spdx-gradle:1.0 -o spdx-json --file bom-oci-syft.spdx.json
```

## Generating a SBOM from the source code using Trivy

```shell
trivy fs --format spdx-json -o bom-trivy.spdx.json .
```

## Generating a SBOM at build time using SPDX

```shell
./gradlew clean build
```

## Scanning a SBOM for security vulnerabilities with Trivy

```shell
trivy sbom build/application.spdx.json
```

## Verifying the quality of a SBOM with sbomqs

```shell
sbomqs score build/application.spdx.json
```
