---
name: AWS Directory Service
x-slug: aws-directory-service
description: AWS Directory Service for Microsoft Active Directory (Enterprise Edition),
  also known as AWS Microsoft AD, enables your directory-aware workloads and AWS resources
  to use managed Active Directory in the AWS Cloud. The Microsoft AD service is built
  on actual Microsoft Active Directory and does not require you to synchronize or
  replicate data from your existing Active Directory to the cloud. You can use standard
  Active Directory administration tools and take advantage of built-in Active Directory
  features such as Group Policy, trusts, and single sign-on. With Microsoft AD, you
  can easily joinAmazon EC2andAmazon RDS for SQL Serverinstances to a domain, and
  useAWS Enterprise IT applicationssuch asAmazon WorkSpaceswith Active Directory users
  and groups.
image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Security-Identity_AWSDirectoryService.png
x-kinRank: "10"
x-alexaRank: "0"
tags: Routes
created: "2018-06-25"
modified: "2018-06-25"
url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/aws-directory-service/apis.md
specificationVersion: "0.14"
apis:
- name: AWS Directory Service API Add Ip Routes
  x-api-slug: aws-directory-service-api
  description: If the DNS server for your on-premises domain uses a publicly addressable
    IP address, you must add a CIDR address block to correctly route traffic to and
    from your Microsoft AD on Amazon Web Services.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Security-Identity_AWSDirectoryService.png
  humanURL: https://aws.amazon.com/directoryservice/
  baseURL: ://///?Action=AddIpRoutes
  tags: IP Address Routes
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/aws-directory-service/actionaddiproutes-get-openapi.md
- name: AWS Directory Service API List Ip Routes
  x-api-slug: aws-directory-service-api
  description: Lists the address blocks that you have added to a directory.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Security-Identity_AWSDirectoryService.png
  humanURL: https://aws.amazon.com/directoryservice/
  baseURL: ://///?Action=ListIpRoutes
  tags: IP Address Routes
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/aws-directory-service/actionlistiproutes-get-openapi.md
- name: AWS Directory Service API Remove Ip Routes
  x-api-slug: aws-directory-service-api
  description: Removes IP address blocks from a directory.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Security-Identity_AWSDirectoryService.png
  humanURL: https://aws.amazon.com/directoryservice/
  baseURL: ://///?Action=RemoveIpRoutes
  tags: IP Address Routes
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/aws-directory-service/actionremoveiproutes-get-openapi.md
- name: AWS Directory Service API
  x-api-slug: aws-directory-service-api
  description: AWS Directory Service for Microsoft Active Directory (Enterprise Edition),
    also known as AWS Microsoft AD, enables your directory-aware workloads and AWS
    resources to use managed Active Directory in the AWS Cloud. The Microsoft AD service
    is built on actual Microsoft Active Directory and does not require you to synchronize
    or replicate data from your existing Active Directory to the cloud. You can use
    standard Active Directory administration tools and take advantage of built-in
    Active Directory features such as Group Policy, trusts, and single sign-on. With
    Microsoft AD, you can easily joinAmazon EC2andAmazon RDS for SQL Serverinstances
    to a domain, and useAWS Enterprise IT applicationssuch asAmazon WorkSpaceswith
    Active Directory users and groups.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Security-Identity_AWSDirectoryService.png
  humanURL: https://aws.amazon.com/directoryservice/
  baseURL: :///
  tags: Routes
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/aws-directory-service/openapi.md
x-common:
- type: x-command-line-interface
  url: http://docs.aws.amazon.com/cli/latest/reference/ds/index.html
- type: x-documentation
  url: http://docs.aws.amazon.com/directoryservice/latest/devguide/api-ref.html
- type: x-faq
  url: https://aws.amazon.com/directoryservice/faqs/
- type: x-getting-started
  url: https://aws.amazon.com/directoryservice/getting-started/
- type: x-pricing
  url: https://aws.amazon.com/directoryservice/pricing/
- type: x-website
  url: https://aws.amazon.com/directoryservice/
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---