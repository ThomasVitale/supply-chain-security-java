# Containerizing Java applications with Cloud Native Buildpacks

## Building a container image with Spring Boot

```shell
./gradlew bootBuildImage
```

## Extracting the SBOMs from each layer of the image with pack

```shell
pack sbom download demo-buildpacks:1.0 --output-dir image-sboms
```

## Scanning the SBOMs for security vulnerabilities with Trivy

```shell
trivy sbom image-sboms/layers/sbom/launch/paketo-buildpacks_executable-jar/sbom.cdx.json
```
