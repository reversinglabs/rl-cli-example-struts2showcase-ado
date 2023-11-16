# ReversingLabs rl-secure Azure DevOps (ADO) Examples

This repository contains working examples of Azure DevOps (ADO) pipeline scripts to illustrate scanning with the
[ReversingLabs secure.software CLI](https://docs.secure.software/cli/).

ReversingLabs secure.software CLI is capable of scanning
[nearly any type](https://docs.secure.software/concepts/language-coverage)
of software artifact or package that results from a build.

In these examples, we're using the source code and Maven build instructions for the Struts2 showcase web app,
which came with [Apache Struts v2.5.28](https://archive.apache.org/dist/struts/2.5.28/).

The following examples are provided in this repository:

- **azure-pipelines.yml**
- **azure-pipelines-cli.yml**

Both examples require that you define the `RLSECURE_ENCODED_LICENSE` and the `RLSECURE_SITE_KEY` secret environment variables
to store your ReversingLabs
[license and site key](https://docs.secure.software/cli/deployment/rl-deploy-quick-start#prepare-the-license-and-site-key).


## azure-pipelines.yml
This pipeline script builds the WAR file and scans it using the
[ReversingLabs rl-scanner Docker image](https://hub.docker.com/r/reversinglabs/rl-scanner).

After the file is scanned, analysis reports in HTML, JSON, CycloneDX, and SPDX formats are saved as pipeline artifacts.


## azure-pipelines-cli.yml

This pipeline script builds the WAR file.

It installs the [rl-deploy](https://pypi.org/project/rl-deploy/) Python package,
which is subsequently used to install and license the `rl-secure` CLI.

After the file is scanned, analysis reports in HTML, JSON, CycloneDX, and SPDX formats are saved as pipeline artifacts.
