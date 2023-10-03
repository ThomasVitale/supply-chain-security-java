# Verifying policies for signatures and provenance

## Verifying the signature on an OCI image

```shell
cosign verify \
   --certificate-identity-regexp https://github.com/ThomasVitale \
   --certificate-oidc-issuer https://token.actions.githubusercontent.com \
   ghcr.io/thomasvitale/demo | jq
```

## Verifying the SLSA provenance for an OCI image

```shell
IMAGE=ghcr.io/thomasvitale/demo
IMAGE="${IMAGE}@"$(crane digest "${IMAGE}")
slsa-verifier verify-image "$IMAGE" \
  --source-uri github.com/ThomasVitale/supply-chain-security-java
```
