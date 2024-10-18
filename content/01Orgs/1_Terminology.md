---
title: "Terminology"
linkTitle: "Terminology"
weight: 1
---

## Terminology - Start with a solid foundation! 

- Organizations/"OU”/{{% badge color="orange" %}}Units{{% /badge %}} – these are hierarchical identifiers indicating directories or folders within the FCLD Organizations concept 
  - The Org has a root OU ID and can have child OU ID’s 
- IAM - {{% badge color="green" %}}Accounts{{% /badge %}} – numbered FortiCloud Account ID’s. 
  - The Org has a single Root Account (belonging to MSSP)
  - MSSP can create child/member Accounts in an OU via FCLD Web GUI 
- IAM - {{% badge color="red" %}}Users{{% /badge %}} – 3 types as described in docs 
  - IAM “users"- user entity managed in FCLD 
    - Can be local or Org with same “permission scope” and “permission profile” as below 
    - Password must be set with “Reset URL”, which can only be triggered by admin (not user)
    - 2FA enabled by default and cannot be disabled 
      - Delivered to User’s email, so must be valid (FortiToken is the only other option presently)
  - External Idp Roles/{{% badge color="cyan" %}}Roles{{% /badge %}} – which is really just a mapping of a SAML Assertion containing “Role” = “XYZ” to the following 
    - Local role – access to the “Account” in which the Role is created 
      - {{% badge color="violet" %}}Permission scope{{% /badge %}} (asset folder)
      - {{% badge color="blue" %}}Permission profile{{% /badge %}} (local specific) – specifies which FCLD Portal features are available 
    - Org role – access to an OU or Account within the Org 
      - {{% badge color="violet" %}}Permission scope{{% /badge %}} (Org OU or Account within OU)
      - {{% badge color="blue" %}}Permission profile{{% /badge %}} (Org specific) - specifies which FCLD Portal features are available 
    - 2FA handled by IdP 
    - IDP enablement is via special request to PM 
  - API User – required for calling any of the available API’s
