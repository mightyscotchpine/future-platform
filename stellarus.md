# The New Company: Stellarus

Stellarus is a small, early stage startup that provides Software-as-a-Service to healthcare insurance companies. It is in the process of being spun off of another company, "Blue Shield of California", also known as "BSC".


## The Stellarus Platform Engineering team (SPE)

The Platform Engineering (SPE) team within Stellarus builds and operates all Kubernetes and cloud infrastructure, manages GitHub, and manages all CI/CD tooling.

## The Stellarus Developer team (SDEV)

Currently a small team of remote developers.

## Stellarus Code Repos

GitHub is used for all code repos.

## Stellarus AI Tool Access

All teams at the company have access to Azure OpenAI Services for Inference and for building agents.

## Stellarus Infrastructure as Code

All cloud infrastructure is defined in Terraform and reconciled via manual terraform commands run by SPE.
SPE plans to implement Crossplane in the near future.

## Stellarus foundational cloud infrastructure

Stellarus foundational cloud infrastructure is very simple right now. It is all in Azure, and includes the following:
- One Azure account
- A few Azure subscriptions containing a few VNets and a handful of subnets.
- A couple of Azure VPNs
- Application infrastructure also includes basic things like Azure Key Vaults and Storage Accounts.
- All that is defined with Terraform.


## Stellarus Kubernetes Infrastructure

Our Kubernetes infrastructure in Azure is also very simple right now. There are three AKS clusters:
- One "hub-cluster" for management applications like ArgoCD.
  - It is bootstrapped via direct Terraform commands.
- One "lower cluster for the DEV, QA AND STAGE application environments
  - It is defined in Terraform and reconciled via ArgoCD.
- One "upper" cluster for the PROD application environments
  - It is defined in Terraform and reconciled via ArgoCD.


## Stellarus CI/CD

The application deployments are very simple right now.
- All applications are containerized.
- Container images are stored in Azure Container Registry (ACR)
- SDEV create their own docker config and build their container image
- SDEV do local testing
- SDEV add a "DEV" tag to the container image and push it to ACR
- ArgoCD sees the new image and deploys it to the DEV environment in AKS.
- There are no CI pipelines yet.
- SDEV run their tests against the DEV environment.
- If all testing in DEV passes, SDEV tags the container image with a "QA" tag. This tag-driven promotion process continues up to PROD.


## Stellarus Application Databases
Databases are run by a dedicated team, and are currently out of scope for the IDP.
We do not run Backstage or any other dedicated developer portal layer.

## Stellarus Observability
- Currently working with an LGTM stack (Loki, Graphana, Tempo, Mimir), plus Pyroscope (continuous application profiling)
- Also considering Datadog

# The Old Company: Blue Shield of California (BSC)

More details about BSC will be added here.
