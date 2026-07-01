The following are the needs to be filled by the features of the Stellarus Internal Developer Platform (IDP).

# General needs

Assume that the IDP must meet all the typical needs of software developers, and meets them in a way that is typical for the software development industry in 2026.
Anything more specific below overides this for that particular aspect or functionality of the platform.


# Specific Developer Needs

- Must ensure that a specific application version must be deployed with specific versions of its dependencies.
- Developers must be able to request network connectivity for their application deployments via the platform.
  - Inter-application connectivity only needs to be approved by the owners of the the source and destination applications. Those approvals are done via pull requests to make them completely auditable.
  - The platform will not permit connectivity that violates security or compliance policy. Those policies are defined in code by the central security and compliance engineering teams.

# Specific Platform Engineering needs
