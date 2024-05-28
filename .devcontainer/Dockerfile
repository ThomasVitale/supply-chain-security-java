FROM mcr.microsoft.com/devcontainers/java:1-21-bullseye

RUN apt-get update && export DEBIAN_FRONTEND=noninteractive && \
    apt-get -y install httpie && \
    rm -Rf /var/lib/apt/lists/*  && \
    rm -Rf /usr/share/doc && rm -Rf /usr/share/man  && \
    apt-get clean

RUN curl -sLS https://get.arkade.dev | sudo sh && \
    arkade system install go && \
    echo "export PATH=\$PATH:/usr/local/go/bin/" | tee -a /etc/profile && \
    echo "export GOPATH=\$HOME/go" | tee -a /etc/profile

RUN arkade get cosign crane dive grype pack syft trivy && \
    chmod +x $HOME/.arkade/bin/* && \
    mv $HOME/.arkade/bin/* /usr/local/bin/

RUN /usr/local/go/bin/go install github.com/sigstore/gitsign@latest && \
    chmod +x $HOME/go/bin/* && \
    mv $HOME/go/bin/* /usr/local/bin/ && \
    rm -Rf $HOME/go
