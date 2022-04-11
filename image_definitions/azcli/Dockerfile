# This image builds on the base image and installs AzureCLI - specifically for function deployments

FROM amidostacks/runner-pwsh

# Install the AzCLI prerequisites
RUN apt-get update
RUN apt-get install -y ca-certificates curl apt-transport-https lsb-release gnupg
RUN curl -sL https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor | tee /etc/apt/trusted.gpg.d/microsoft.gpg > /dev/null

# Install the AzCLI
RUN AZ_REPO=$(lsb_release -cs) && echo "deb [arch=amd64] https://packages.microsoft.com/repos/azure-cli/ $AZ_REPO main" | tee /etc/apt/sources.list.d/azure-cli.list
RUN apt-get update
RUN apt-get install -y azure-cli

# Clean up
RUN apt-get -y remove curl && \
    apt-get -y autoremove
