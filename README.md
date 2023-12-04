[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Docker Pulls](https://img.shields.io/docker/pulls/zenika/terraform-aws-cli.svg)](https://hub.docker.com/r/zenika/terraform-aws-cli/)

# Terraform and AWS CLI Docker image

## 🔧 What's inside ?

Tools included:

* [Terraform CLI](https://www.terraform.io/docs/commands/index.html)
* [AWS CLI](https://aws.amazon.com/fr/cli/)
* [Git](https://git-scm.com/) for Terraform remote module usage
* [jq](https://stedolan.github.io/jq/) to process JSON returned by AWS
* [OpenSSH Client](https://www.openssh.com/) to handle Terraform module clone over SSH
* This image uses a non-root user with a UID and GID of 1001 to conform with docker security best practices.

## 🚀 Usage

### 🐚 Launch the CLI

Set your AWS credentials (optional) and use the CLI as you would on any other platform, for instance using the latest image:

```bash
echo AWS_ACCESS_KEY_ID=YOUR_ACCESS_KEY
echo AWS_SECRET_ACCESS_KEY=YOUR_SECRET_KEY
echo AWS_DEFAULT_REGION=YOUR_DEFAULT_REGION

docker container run -it --rm -e "AWS_ACCESS_KEY_ID=${AWS_ACCESS_KEY_ID}" -e "AWS_SECRET_ACCESS_KEY=${AWS_SECRET_ACCESS_KEY}" -e "AWS_DEFAULT_REGION=${AWS_DEFAULT_REGION}" -v ${PWD}:/workspace zenika/terraform-aws-cli:latest
```

> The `--rm` flag will completely destroy the container and its data on exit.

### ⚙️ Build the image

The image can be built locally directly from the Dockerfiles, using the build script.

It will :

* Lint the Dockerfile with [Hadolint](https://github.com/hadolint/hadolint);
* Build and tag the image `zenika/terraform-aws-cli:dev`;
* Execute [container structure tests](https://github.com/GoogleContainerTools/container-structure-test) on the image.

```bash
# launch build script
./dev.sh
```

Optionally, it is possible to choose the tools desired versions :

```bash
# Set tools desired versions
AWS_CLI_VERSION=2.12.6
TERRAFORM_VERSION=1.5.2

# launch the build script with parameters
./dev.sh $AWS_CLI_VERSION $TERRAFORM_VERSION
```

## 🙏 Contributions
Do not hesitate to contribute by [filling an issue](https://github.com/Zenika/terraform-aws-cli/issues) or [a PR](https://github.com/Zenika/terraform-aws-cli/pulls) !

## 📚 Documentations

* [Dependencies upgrades checklist](https://github.com/zenika-open-source/terraform-aws-cli/tree/master/docs/dependencies-upgrades.md)
* [Binaries verifications](https://github.com/zenika-open-source/terraform-aws-cli/tree/master/docs/binaries-verifications.md)

## 🚩 Similar repositories

* For Azure: [zenika-open-source/terraform-azure-cli](https://github.com/zenika-open-source/terraform-azure-cli)

## 📖 License
This project is under the [Apache License 2.0](https://raw.githubusercontent.com/Zenika/terraform-aws-cli/master/LICENSE)

[![with love by zenika](https://img.shields.io/badge/With%20%E2%9D%A4%EF%B8%8F%20by-Zenika-b51432.svg)](https://oss.zenika.com)
# tools-docker-image
# tools-docker-image
