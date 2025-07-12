|                     |                                                                                   |     |
| ------------------- | --------------------------------------------------------------------------------- | --- |
| **Assessment Type** | Multiple choice                                                                   |     |
| **Format**          | Online proctored                                                                  |     |
| **Duration**        | 1 hour                                                                            |     |
| **Price**           | $70.50 USD, plus locally applicable taxes and fees. Free retake **not included**. |     |
| **Language**        | English                                                                           |     |
| **Expiration**      | 2 years                                                                           |     |

## Inhaltsverzeichnis

- [1 Understand Infrastructure as Code (IaC) concepts](#1-understand-infrastructure-as-code-iac-concepts)
  - [1a Explain what IaC is](#1a-explain-what-iac-is)
  - [1b Describe advantages of IaC patterns](#1b-describe-advantages-of-iac-patterns)
- [2 Understand the purpose of Terraform (vs other IaC)](#2-understand-the-purpose-of-terraform-vs-other-iac)
  - [2a Explain multi-cloud and provider-agnostic benefits](#2a-explain-multi-cloud-and-provider-agnostic-benefits)
  - [2b Explain the benefits of state](#2b-explain-the-benefits-of-state)
- [3 Understand Terraform basics](#3-understand-terraform-basics)
  - [3a Install and version Terraform providers](#3a-install-and-version-terraform-providers)
  - [3c Write Terraform configuration using multiple providers](#3c-write-terraform-configuration-using-multiple-providers)
  - [3d Describe how Terraform finds and fetches providers](#3d-describe-how-terraform-finds-and-fetches-providers)
- [4 Use Terraform outside the core workflow](#4-use-terraform-outside-the-core-workflow)
  - [4a Describe when to use terraform import to import existing infrastructure into your Terraform state](#4a-describe-when-to-use-terraform-import-to-import-existing-infrastructure-into-your-terraform-state)
  - [4b Use terraform state to view Terraform state](#4b-use-terraform-state-to-view-terraform-state)
  - [4c Describe when to enable verbose logging and what the outcomevalue is](#4c-describe-when-to-enable-verbose-logging-and-what-the-outcomevalue-is)
- [5 Interact with Terraform modules](#5-interact-with-terraform-modules)
  - [5a Contrast and use different module source options including the public Terraform Module Registry](#5a-contrast-and-use-different-module-source-options-including-the-public-terraform-module-registry)
  - [5b Interact with module inputs and outputs](#5b-interact-with-module-inputs-and-outputs)
  - [5c Describe variable scope within moduleschild modules](#5c-describe-variable-scope-within-moduleschild-modules)
  - [5d Set module version](#5d-set-module-version)
- [6 Use the core Terraform workflow](#6-use-the-core-terraform-workflow)
  - [6a Describe Terraform workflow Write Plan Create](#6a-describe-terraform-workflow-write-plan-create)
  - [6b Initialize a Terraform working directory terraform init](#6b-initialize-a-terraform-working-directory-terraform-init)
  - [6c Validate a Terraform configuration terraform validate](#6c-validate-a-terraform-configuration-terraform-validate)
  - [6d Generate and review an execution plan for Terraform terraform plan](#6d-generate-and-review-an-execution-plan-for-terraform-terraform-plan)
  - [6e Execute changes to infrastructure with Terraform terraform apply](#6e-execute-changes-to-infrastructure-with-terraform-terraform-apply)
  - [6f Destroy Terraform managed infrastructure terraform destroy](#6f-destroy-terraform-managed-infrastructure-terraform-destroy)
  - [6g Apply formatting and style adjustments to a configuration terraform fmt](#6g-apply-formatting-and-style-adjustments-to-a-configuration-terraform-fmt)
- [7 Implement and maintain state](#7-implement-and-maintain-state)
  - [7a Describe default local backend](#7a-describe-default-local-backend)
  - [7b Describe state locking](#7b-describe-state-locking)
  - [7c Handle backend and cloud integration authentication methods](#7c-handle-backend-and-cloud-integration-authentication-methods)
  - [7d Differentiate remote state back end options](#7d-differentiate-remote-state-back-end-options)
  - [7e Manage resource drift and Terraform state](#7e-manage-resource-drift-and-terraform-state)
  - [7f Describe backend block and cloud integration in configuration](#7f-describe-backend-block-and-cloud-integration-in-configuration)
  - [7g Understand secret management in state files](#7g-understand-secret-management-in-state-files)
- [8 Read, generate, and modify configuration](#8-read-generate-and-modify-configuration)
  - [8a Demonstrate use of variables and outputs](#8a-demonstrate-use-of-variables-and-outputs)
  - [8b Describe secure secret injection best practice](#8b-describe-secure-secret-injection-best-practice)
  - [8c Understand the use of collection and structural types](#8c-understand-the-use-of-collection-and-structural-types)
  - [8d Create and differentiate resource and data configuration](#8d-create-and-differentiate-resource-and-data-configuration)
  - [8e Use resource addressing and resource parameters to connect resources together](#8e-use-resource-addressing-and-resource-parameters-to-connect-resources-together)
  - [8f Use HCL and Terraform functions to write configuration](#8f-use-hcl-and-terraform-functions-to-write-configuration)
  - [8g Describe built-in dependency management order of execution based](#8g-describe-built-in-dependency-management-order-of-execution-based)
- [9 Understand HCP Terraform capabilities](#9-understand-hcp-terraform-capabilities)
  - [9a Explain how HCP Terraform helps to manage infrastructure](#9a-explain-how-hcp-terraform-helps-to-manage-infrastructure)
  - [9b Describe how HCP Terraform enables collaboration and governance](#9b-describe-how-hcp-terraform-enables-collaboration-and-governance)


# Hands-on-labs Udemy

[Course: HashiCorp Certified: Terraform Associate - Hands-On Labs | Udemy Business](https://computacenter.udemy.com/course/terraform-hands-on-labs/learn/lecture/33255092#content)

# Exam Script

[hashicorp/terraform at master · btkrausen/hashicorp](https://github.com/btkrausen/hashicorp/tree/master/terraform)

## 1         Understand Infrastructure as Code (IaC) concepts
### 1a       Explain what IaC is
# What is Terraform?

Terraform is an infrastructure as code tool that lets you build, change, and version cloud and on-prem resources safely and efficiently.

HashiCorp Terraform is an infrastructure as code tool that lets you define both cloud and on-prem resources in human-readable configuration files that you can version, reuse, and share. You can then use a consistent workflow to provision and manage all of your infrastructure throughout its lifecycle. Terraform can manage low-level components like compute, storage, and networking resources, as well as high-level components like DNS entries and SaaS features.

> **Hands On:** Try the Get Started tutorials to start managing infrastructure on popular cloud providers: [Amazon Web Services](https://developer.hashicorp.com/terraform/tutorials/aws-get-started), [Azure](https://developer.hashicorp.com/terraform/tutorials/azure-get-started), [Google Cloud Platform](https://developer.hashicorp.com/terraform/tutorials/gcp-get-started), [Oracle Cloud Infrastructure](https://developer.hashicorp.com/terraform/tutorials/oci-get-started), and [Docker](https://developer.hashicorp.com/terraform/tutorials/docker-get-started).

## [](https://developer.hashicorp.com/terraform/intro#how-does-terraform-work)How does Terraform work?

Terraform creates and manages resources on cloud platforms and other services through their application programming interfaces (APIs). Providers enable Terraform to work with virtually any platform or service with an accessible API.

![Terraform creates and manages cloud platforms and services through their APIs](https://web-unified-docs-hashicorp.vercel.app/api/assets/terraform/latest/img/docs/intro-terraform-apis.png)

HashiCorp and the Terraform community have already written **thousands of providers** to manage many different types of resources and services. You can find all publicly available providers on the [Terraform Registry](https://registry.terraform.io/), including Amazon Web Services (AWS), Azure, Google Cloud Platform (GCP), Kubernetes, Helm, GitHub, Splunk, DataDog, and many more.

The core Terraform workflow consists of three stages:

- **Write:** You define resources, which may be across multiple cloud providers and services. For example, you might create a configuration to deploy an application on virtual machines in a Virtual Private Cloud (VPC) network with security groups and a load balancer.
- **Plan:** Terraform creates an execution plan describing the infrastructure it will create, update, or destroy based on the existing infrastructure and your configuration.
- **Apply:** On approval, Terraform performs the proposed operations in the correct order, respecting any resource dependencies. For example, if you update the properties of a VPC and change the number of virtual machines in that VPC, Terraform will recreate the VPC before scaling the virtual machines.

![The Terraform workflow has three steps: Write, Plan, and Apply](https://web-unified-docs-hashicorp.vercel.app/api/assets/terraform/latest/img/docs/intro-terraform-workflow.png)

### 1b      Describe advantages of IaC patterns
## [](https://developer.hashicorp.com/terraform/intro#why-terraform)Why Terraform?

### [](https://developer.hashicorp.com/terraform/intro#manage-any-infrastructure)Manage any infrastructure

Find providers for many of the platforms and services you already use in the [Terraform Registry](https://registry.terraform.io/). You can also [write your own](https://developer.hashicorp.com/terraform/plugin). Terraform takes an [immutable approach to infrastructure](https://www.hashicorp.com/resources/what-is-mutable-vs-immutable-infrastructure), reducing the complexity of upgrading or modifying your services and infrastructure.

### [](https://developer.hashicorp.com/terraform/intro#track-your-infrastructure)Track your infrastructure

Terraform generates a plan and prompts you for your approval before modifying your infrastructure. It also keeps track of your real infrastructure in a [state file](https://developer.hashicorp.com/terraform/language/state), which acts as a source of truth for your environment. Terraform uses the state file to determine the changes to make to your infrastructure so that it will match your configuration.

### [](https://developer.hashicorp.com/terraform/intro#automate-changes)Automate changes

Terraform configuration files are declarative, meaning that they describe the end state of your infrastructure. You do not need to write step-by-step instructions to create resources because Terraform handles the underlying logic. Terraform builds a resource graph to determine resource dependencies and creates or modifies non-dependent resources in parallel. This allows Terraform to provision resources efficiently.

### [](https://developer.hashicorp.com/terraform/intro#standardize-configurations)Standardize configurations

Terraform supports reusable configuration components called [modules](https://developer.hashicorp.com/terraform/language/modules) that define configurable collections of infrastructure, saving time and encouraging best practices. You can use publicly available modules from the Terraform Registry, or write your own.

### [](https://developer.hashicorp.com/terraform/intro#collaborate)Collaborate

Since your configuration is written in a file, you can commit it to a Version Control System (VCS) and use [HCP Terraform](https://developer.hashicorp.com/terraform/intro/terraform-editions#hcp-terraform) to efficiently manage Terraform workflows across teams. HCP Terraform runs Terraform in a consistent, reliable environment and provides secure access to shared state and secret data, role-based access controls, a private registry for sharing both modules and providers, and more.

**Tip:** Learn more about [Terraform use cases](https://developer.hashicorp.com/terraform/intro/use-cases) and [how Terraform compares to alternatives](https://developer.hashicorp.com/terraform/intro/vs).

## [](https://developer.hashicorp.com/terraform/intro#community)Community
 
We welcome questions, suggestions, and contributions from the community.

- Ask questions in [HashiCorp Discuss](https://discuss.hashicorp.com/c/terraform-core/27).
- Read our [contributing guide](https://github.com/hashicorp/terraform/blob/main/.github/CONTRIBUTING.md).
- [Submit an issue](https://github.com/hashicorp/terraform/issues/new/choose) for bugs and feature requests.



## 2         Understand the purpose of Terraform (vs other IaC)

### 2a       Explain multi-cloud and provider-agnostic benefits

**Multi-Cloud Deployment**

Provisioning infrastructure across multiple clouds increases fault-tolerance, allowing for more graceful recovery from cloud provider outages. However, multi-cloud deployments add complexity because each provider has its own interfaces, tools, and workflows. Terraform lets you use the same workflow to manage multiple providers and handle cross-cloud dependencies. This simplifies management and orchestration for large-scale, multi-cloud infrastructures.

**Resources**

- Try our [Deploy Federated Multi-Cloud Kubernetes Clusters](https://developer.hashicorp.com/terraform/tutorials/networking/multicloud-kubernetes) tutorial to provision Kubernetes clusters in both Azure and AWS environments, configure Consul federation with mesh gateways across the two clusters, and deploy microservices across the two clusters to verify federation.
- Browse the [Terraform Registry](https://registry.terraform.io/browse/providers) to find thousands of publicly available providers.

### 2b       Explain the benefits of state

# Purpose of Terraform State

State is a necessary requirement for Terraform to function. It is often asked if it is possible for Terraform to work without state, or for Terraform to not use state and just inspect real world resources on every run. This page will help explain why Terraform state is required.

As you'll see from the reasons below, state is required. And in the scenarios where Terraform may be able to get away without state, doing so would require shifting massive amounts of complexity from one place (state) to another place (the replacement concept).

## [](https://developer.hashicorp.com/terraform/language/state/purpose#mapping-to-the-real-world)Mapping to the Real World

Terraform requires some sort of database to map Terraform config to the real world. For example, when you have a resource `resource "aws_instance" "foo"` in your configuration, Terraform uses this mapping to know that the resource `resource "aws_instance" "foo"` represents a real world object with the instance ID `i-abcd1234` on a remote system.

For some providers like AWS, Terraform could theoretically use something like AWS tags. Early prototypes of Terraform actually had no state files and used this method. However, we quickly ran into problems. The first major issue was a simple one: not all resources support tags, and not all cloud providers support tags.

Therefore, for mapping configuration to resources in the real world, Terraform uses its own state structure.

Terraform expects that each remote object is bound to only one resource instance in the configuration. If a remote object is bound to multiple resource instances, the mapping from configuration to the remote object in the state becomes ambiguous, and Terraform may behave unexpectedly. Terraform can guarantee a one-to-one mapping when it creates objects and records their identities in the state. When importing objects created outside of Terraform, you must make sure that each distinct object is imported to only one resource instance.

## [](https://developer.hashicorp.com/terraform/language/state/purpose#metadata)Metadata

Alongside the mappings between resources and remote objects, Terraform must also track metadata such as resource dependencies.

Terraform typically uses the configuration to determine dependency order. However, when you delete a resource from a Terraform configuration, Terraform must know how to delete that resource from the remote system. Terraform can see that a mapping exists in the state file for a resource not in your configuration and plan to destroy. However, since the configuration no longer exists, the order cannot be determined from the configuration alone.

To ensure correct operation, Terraform retains a copy of the most recent set of dependencies within the state. Now Terraform can still determine the correct order for destruction from the state when you delete one or more items from the configuration.

Terraform could take another approach to dependency order by using an underlying hierarchy of order between resource types. For example, Terraform could know that servers must be deleted before the subnets they are a part of. The complexity for this approach quickly explodes, however: in addition to Terraform having to understand the ordering semantics of every resource for every _provider_, Terraform must also understand the ordering _across providers_.

Terraform also stores other metadata for similar reasons, such as a pointer to the provider configuration that was most recently used with the resource in situations where multiple aliased providers are present.

## [](https://developer.hashicorp.com/terraform/language/state/purpose#performance)Performance

In addition to basic mapping, Terraform stores a cache of the attribute values for all resources in the state. This is the most optional feature of Terraform state and is done only as a performance improvement.

When running a `terraform plan`, Terraform must know the current state of resources in order to effectively determine the changes that it needs to make to reach your desired configuration.

For small infrastructures, Terraform can query your providers and sync the latest attributes from all your resources. This is the default behavior of Terraform: for every plan and apply, Terraform will sync all resources in your state.

For larger infrastructures, querying every resource is too slow. Many cloud providers do not provide APIs to query multiple resources at once, and the round trip time for each resource is hundreds of milliseconds. On top of this, cloud providers almost always have API rate limiting so Terraform can only request a certain number of resources in a period of time. Larger users of Terraform make heavy use of the `-refresh=false` flag as well as the `-target` flag in order to work around this. In these scenarios, the cached state is treated as the record of truth.

## [](https://developer.hashicorp.com/terraform/language/state/purpose#syncing)Syncing

In the default configuration, Terraform stores the state in a file in the current working directory where Terraform was run. This is okay for getting started, but when using Terraform in a team it is important for everyone to be working with the same state so that operations will be applied to the same remote objects.

[Remote state](https://developer.hashicorp.com/terraform/language/state/remote) is the recommended solution to this problem. With a fully-featured state backend, Terraform can use remote locking as a measure to avoid two or more different users accidentally running Terraform at the same time, and thus ensure that each Terraform run begins with the most recent updated state.

## 3         Understand Terraform basics

# Terraform Language Documentation

Use the Terraform configuration language to describe the infrastructure that Terraform manages.

This is the documentation for Terraform's configuration language. It is relevant to users of [Terraform CLI](https://developer.hashicorp.com/terraform/cli), [HCP Terraform](https://cloud.hashicorp.com/products/terraform), and [Terraform Enterprise](https://developer.hashicorp.com/terraform/enterprise). Terraform's language is its primary user interface. Configuration files you write in Terraform language tell Terraform what plugins to install, what infrastructure to create, and what data to fetch. Terraform language also lets you define dependencies between resources and create multiple similar resources from a single configuration block.

> **Hands-on:** Try the [Write Terraform Configuration](https://developer.hashicorp.com/terraform/tutorials/configuration-language) tutorials.

## [](https://developer.hashicorp.com/terraform/language#about-the-terraform-language)About the Terraform Language

The main purpose of the Terraform language is declaring [resources](https://developer.hashicorp.com/terraform/language/resources), which represent infrastructure objects. All other language features exist only to make the definition of resources more flexible and convenient.

A _Terraform configuration_ is a complete document in the Terraform language that tells Terraform how to manage a given collection of infrastructure. A configuration can consist of multiple files and directories.

The syntax of the Terraform language consists of only a few basic elements:

```
resource "aws_vpc" "main" {
  cidr_block = var.base_cidr_block
}

<BLOCK TYPE> "<BLOCK LABEL>" "<BLOCK LABEL>" {
  # Block body
  <IDENTIFIER> = <EXPRESSION> # Argument
}
```

- _Blocks_ are containers for other content and usually represent the configuration of some kind of object, like a resource. Blocks have a _block type,_ can have zero or more _labels,_ and have a _body_ that contains any number of arguments and nested blocks. Most of Terraform's features are controlled by top-level blocks in a configuration file.
- _Arguments_ assign a value to a name. They appear within blocks.
- _Expressions_ represent a value, either literally or by referencing and combining other values. They appear as values for arguments, or within other expressions.

The Terraform language is declarative, describing an intended goal rather than the steps to reach that goal. The ordering of blocks and the files they are organized into are generally not significant; Terraform only considers implicit and explicit relationships between resources when determining an order of operations.

### [](https://developer.hashicorp.com/terraform/language#example)Example

The following example describes a simple network topology for Amazon Web Services, just to give a sense of the overall structure and syntax of the Terraform language. Similar configurations can be created for other virtual network services, using resource types defined by other providers, and a practical network configuration will often contain additional elements not shown here.

```
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 1.0.4"
    }
  }
}

variable "aws_region" {}

variable "base_cidr_block" {
  description = "A /16 CIDR range definition, such as 10.1.0.0/16, that the VPC will use"
  default = "10.1.0.0/16"
}

variable "availability_zones" {
  description = "A list of availability zones in which to create subnets"
  type = list(string)
}

provider "aws" {
  region = var.aws_region
}

resource "aws_vpc" "main" {
  # Referencing the base_cidr_block variable allows the network address
  # to be changed without modifying the configuration.
  cidr_block = var.base_cidr_block
}

resource "aws_subnet" "az" {
  # Create one subnet for each given availability zone.
  count = length(var.availability_zones)

  # For each subnet, use one of the specified availability zones.
  availability_zone = var.availability_zones[count.index]

  # By referencing the aws_vpc.main object, Terraform knows that the subnet
  # must be created only after the VPC is created.
  vpc_id = aws_vpc.main.id

  # Built-in functions and operators can be used for simple transformations of
  # values, such as computing a subnet address. Here we create a /20 prefix for
  # each subnet, using consecutive addresses for each availability zone,
  # such as 10.1.16.0/20 .
  cidr_block = cidrsubnet(aws_vpc.main.cidr_block, 4, count.index+1)
}
```


### 3a       Install and version Terraform providers

# Provider Configuration

Providers allow Terraform to interact with cloud providers, SaaS providers, and other APIs.

Some providers require you to configure them with endpoint URLs, cloud regions, or other settings before Terraform can use them. This page documents how to configure settings for providers.

Additionally, all Terraform configurations must declare which providers they require so that Terraform can install and use them. The [Provider Requirements](https://developer.hashicorp.com/terraform/language/providers/requirements) page documents how to declare providers so Terraform can install them.

## [](https://developer.hashicorp.com/terraform/language/providers/configuration#provider-configuration-1)Provider Configuration

Provider configurations belong in the root module of a Terraform configuration. (Child modules receive their provider configurations from the root module; for more information, see [The Module `providers` Meta-Argument](https://developer.hashicorp.com/terraform/language/meta-arguments/module-providers) and [Module Development: Providers Within Modules](https://developer.hashicorp.com/terraform/language/modules/develop/providers).)

A provider configuration is created using a `provider` block:

```
provider "google" {
  project = "acme-app"
  region  = "us-central1"
}
```

The name given in the block header (`"google"` in this example) is the [local name](https://developer.hashicorp.com/terraform/language/providers/requirements#local-names) of the provider to configure. This provider should already be included in a `required_providers` block.

The body of the block (between `{` and `}`) contains configuration arguments for the provider. Most arguments in this section are defined by the provider itself; in this example both `project` and `region` are specific to the `google` provider.

You can use [expressions](https://developer.hashicorp.com/terraform/language/expressions) in the values of these configuration arguments, but can only reference values that are known before the configuration is applied. This means you can safely reference input variables, but not attributes exported by resources (with an exception for resource arguments that are specified directly in the configuration).

A provider's documentation should list which configuration arguments it expects. For providers distributed on the [Terraform Registry](https://registry.terraform.io/), versioned documentation is available on each provider's page, via the "Documentation" link in the provider's header.

Some providers can use shell environment variables (or other alternate sources, like VM instance profiles) as values for some of their arguments; when available, we recommend using this as a way to keep credentials out of your version-controlled Terraform code.

There are also two "meta-arguments" that are defined by Terraform itself and available for all `provider` blocks:

- [`alias`, for using the same provider with different configurations for different resources](https://developer.hashicorp.com/terraform/language/providers/configuration#alias-multiple-provider-configurations)
- [`version`, which we no longer recommend](https://developer.hashicorp.com/terraform/language/providers/configuration#provider-versions) (use [provider requirements](https://developer.hashicorp.com/terraform/language/providers/requirements) instead)

Unlike many other objects in the Terraform language, a `provider` block may be omitted if its contents would otherwise be empty. Terraform assumes an empty default configuration for any provider that is not explicitly configured.

## [](https://developer.hashicorp.com/terraform/language/providers/configuration#alias-multiple-provider-configurations)`alias`: Multiple Provider Configurations

You can optionally define multiple configurations for the same provider, and select which one to use on a per-resource or per-module basis. The primary reason for this is to support multiple regions for a cloud platform; other examples include targeting multiple Docker hosts, multiple Consul hosts, etc.

To create multiple configurations for a given provider, include multiple `provider` blocks with the same provider name. For each additional non-default configuration, use the `alias` meta-argument to provide an extra name segment. For example:

```
# The default provider configuration; resources that begin with `aws_` will use
# it as the default, and it can be referenced as `aws`.
provider "aws" {
  region = "us-east-1"
}

# Additional provider configuration for west coast region; resources can
# reference this as `aws.west`.
provider "aws" {
  alias  = "west"
  region = "us-west-2"
}
```

To declare a configuration alias within a module in order to receive an alternate provider configuration from the parent module, add the `configuration_aliases` argument to that provider's `required_providers` entry. The following example declares both the `mycloud` and `mycloud.alternate` provider configuration names within the containing module:

```
terraform {
  required_providers {
    mycloud = {
      source  = "mycorp/mycloud"
      version = "~> 1.0"
      configuration_aliases = [ mycloud.alternate ]
    }
  }
}
```

### [](https://developer.hashicorp.com/terraform/language/providers/configuration#default-provider-configurations)Default Provider Configurations

A `provider` block without an `alias` argument is the _default_ configuration for that provider. Resources that don't set the `provider` meta-argument will use the default provider configuration that matches the first word of the resource type name. (For example, an `aws_instance` resource uses the default `aws` provider configuration unless otherwise stated.)

If every explicit configuration of a provider has an alias, Terraform uses the implied empty configuration as that provider's default configuration. (If the provider has any required configuration arguments, Terraform will raise an error when resources default to the empty configuration.)

### [](https://developer.hashicorp.com/terraform/language/providers/configuration#referring-to-alternate-provider-configurations)Referring to Alternate Provider Configurations

When Terraform needs the name of a provider configuration, it expects a reference of the form `<PROVIDER NAME>.<ALIAS>`. In the example above, `aws.west` would refer to the provider with the `us-west-2` region.

These references are special expressions. Like references to other named entities (for example, `var.image_id`), they aren't strings and don't need to be quoted. But they are only valid in specific meta-arguments of `resource`, `data`, and `module` blocks, and can't be used in arbitrary expressions.

### [](https://developer.hashicorp.com/terraform/language/providers/configuration#selecting-alternate-provider-configurations)Selecting Alternate Provider Configurations

By default, resources use a default provider configuration (one without an `alias` argument) inferred from the first word of the resource type name.

To use an alternate provider configuration for a resource or data source, set its `provider` meta-argument to a `<PROVIDER NAME>.<ALIAS>` reference:

```
resource "aws_instance" "foo" {
  provider = aws.west

  # ...
}
```

To select alternate provider configurations for a child module, use its `providers` meta-argument to specify which provider configurations should be mapped to which local provider names inside the module:

```
module "aws_vpc" {
  source = "./aws_vpc"
  providers = {
    aws = aws.west
  }
}
```

Modules have some special requirements when passing in providers; see [The Module `providers` Meta-Argument](https://developer.hashicorp.com/terraform/language/meta-arguments/module-providers) for more details. In most cases, only _root modules_ should define provider configurations, with all child modules obtaining their provider configurations from their parents.

[](https://developer.hashicorp.com/terraform/language/providers/configuration#)

## [](https://developer.hashicorp.com/terraform/language/providers/configuration#version-deprecated)`version` (Deprecated)

The `version` meta-argument specifies a version constraint for a provider, and works the same way as the `version` argument in a [`required_providers` block](https://developer.hashicorp.com/terraform/language/providers/requirements). The version constraint in a provider configuration is only used if `required_providers` does not include one for that provider.

~**Warning:** The `version` argument in provider configurations is deprecated, and we will remove it in a future Terraform version.

In Terraform 0.13 and later, always declare provider version constraints in [the `required_providers` block](https://developer.hashicorp.com/terraform/language/providers/requirements).

# terraform block reference

This topic provides reference information about the `terraform` block. The `terraform` block allows you to configure Terraform behavior, including the Terraform version, backend, integration with HCP Terraform, and required providers.

## [](https://developer.hashicorp.com/terraform/language/terraform#configuration-model)Configuration model

The `terraform` block supports the following arguments:

- [`terraform`](https://developer.hashicorp.com/terraform/language/terraform#terraform)
    - [`required_version`](https://developer.hashicorp.com/terraform/language/terraform#required_version):   string
    - [`required_providers`](https://developer.hashicorp.com/terraform/language/terraform#required_providers):   block
        - [`<PROVIDER>`](https://developer.hashicorp.com/terraform/language/terraform#provider):   block
            - [`version`](https://developer.hashicorp.com/terraform/language/terraform#provider):   string
            - [`source`](https://developer.hashicorp.com/terraform/language/terraform#provider):   string
    - [`provider_meta "<LABEL>"`](https://developer.hashicorp.com/terraform/language/terraform#provider_meta):   block
    - [`backend "<BACKEND_TYPE>"`](https://developer.hashicorp.com/terraform/language/terraform#backend):   block | mutually exclusive with `cloud`
    - [`cloud`](https://developer.hashicorp.com/terraform/language/terraform#cloud):   block | mutually exclusive with `backend`
        - [`organization`](https://developer.hashicorp.com/terraform/language/terraform#organization):   string | required when connecting to HCP Terraform
        - [`workspaces`](https://developer.hashicorp.com/terraform/language/terraform#workspaces):   block | required when connecting to HCP Terraform
            - [`tags`](https://developer.hashicorp.com/terraform/language/terraform#workspaces):   list | mutually exclusive with `name`
            - [`name`](https://developer.hashicorp.com/terraform/language/terraform#workspaces):   string | mutually exclusive with `tags`
            - [`project`](https://developer.hashicorp.com/terraform/language/terraform#workspaces):   string
        - [`hostname`](https://developer.hashicorp.com/terraform/language/terraform#hostname):   string | `app.terraform.io`
        - [`token`](https://developer.hashicorp.com/terraform/language/terraform#token):   string
    - [`experiments`](https://developer.hashicorp.com/terraform/language/terraform#experiments):   list

## [](https://developer.hashicorp.com/terraform/language/terraform#complete-configuration)Complete configuration

The following `terraform` block defines all of the supported built-in arguments you can set:

```

terraform {
  required_version = "<version>"
  required_providers {
    <PROVIDER> {
      version = "<version-constraint>"
      source = "<provider-address>"
    }
  }
  provider_meta "<LABEL>" { 
    # Shown for completeness but only used for specific cases     
  }
  backend "<TYPE>" {        
    # `backend` is mutually exclusive with `cloud` 
    "<ARGUMENTS>"
  }
  cloud {                   
    # `cloud` is mutually exclusive with `backend` 
    organization = "<organization-name>"
    workspaces {
      tags = [ "<tag>" ]
      name = "<workspace-name>"
      project = "<project-name>"
    }
    hostname = "app.terraform.io"
    token - "<TOKEN>"
  }
  experiments = [ "<feature-name>" ]
}
```

## [](https://developer.hashicorp.com/terraform/language/terraform#specification)Specification

The `terraform` block supports the following configuration.

### [](https://developer.hashicorp.com/terraform/language/terraform#terraform-block)`terraform` block

Parent block that contains configurations that define Terraform behavior. You can only use constant values in the `terraform` block. Arguments in the `terraform` block cannot refer to named objects, such as resources and input variables. Additionally, you cannot use built-in Terraform language functions in the block.

### [](https://developer.hashicorp.com/terraform/language/terraform#required_version)`required_version`

Specifies which version of the Terraform CLI is allowed to run the configuration.

```
terraform {
  required_version = "<Terraform version>"
  # . . .
}
```

Refer to [Version constraints](https://developer.hashicorp.com/terraform/language/expressions/version-constraints) for details about the supported syntax for specifying version constraints.

Use Terraform version constraints in a collaborative environment to ensure that everyone is using a specific Terraform version, or using at least a minimum Terraform version that has behavior expected by the configuration.

Terraform prints an error and exits without taking actions when you use a version of Terraform that does not meet the version constraints to run the configuration.

Modules associated with a configuration may also specify version constraints. You must use a Terraform version that satisfies all version constraints associated with the configuration, including constraints defined in modules, to perform operations. Refer to [Modules](https://developer.hashicorp.com/terraform/language/modules) for additional information about Terraform modules.

The `required_version` configuration applies only to the version of Terraform CLI and not versions of provider plugins. Refer to [Provider Requirements](https://developer.hashicorp.com/terraform/language/providers/requirements) for additional information.

#### [](https://developer.hashicorp.com/terraform/language/terraform#summary)Summary

- Data type: String.
- Default: None.
- Example:[Add a provider](https://developer.hashicorp.com/terraform/language/terraform#add-a-provider)

### [](https://developer.hashicorp.com/terraform/language/terraform#required_providers)`required_providers`

Specifies all provider plugins required to create and manage resources specified in the configuration.

```
terraform {
  required_providers {
    <PROVIDER> {}
  }
  # . . .
}
```

Each local provider name maps to a source address and a version constraint. Refer to each Terraform provider’s documentation in the [public Terraform Registry](https://registry.terraform.io/browse/providers), or your private registry, for instructions on how to configure attributes in the `required_providers` block.

#### [](https://developer.hashicorp.com/terraform/language/terraform#summary-1)Summary

- Data type: Block.
- Default: None.
- Example:[Add a provider](https://developer.hashicorp.com/terraform/language/terraform#add-a-provider)

### [](https://developer.hashicorp.com/terraform/language/terraform#provider-specific-settings)Provider-specific settings

Specifies the name of the provider you want to require. Refer to [Provide Configuration](https://developer.hashicorp.com/terraform/language/providers/configuration) for instructions on how to configure providers.

```
terraform {
  required_providers {
    <PROVIDER> {
      version = "<version-constraint>"
      source = "<address>"      
    }
  }
  # . . .
}
```

You can specify the following arguments:

|Argument|Description|Data type|Default|
|---|---|---|---|
|`version`|Specifies the version of the provider that this configuration must use. You can use operators to constrain version to specify a range of versions. Refer to [Version constraints](https://developer.hashicorp.com/terraform/language/expressions/version-constraints) for additional information.|String|Terraform installs the newest version by default.|
|`source`|Specifies the global source address for the provider. Refer to [Requiring Providers](https://developer.hashicorp.com/terraform/language/providers/requirements) for additional information.|String|None|

#### [](https://developer.hashicorp.com/terraform/language/terraform#summary-2)Summary

- Data type: Block.
- Default: None.
- Example:[Add a provider](https://developer.hashicorp.com/terraform/language/terraform#add-a-provider)

### [](https://developer.hashicorp.com/terraform/language/terraform#provider_meta)`provider_meta "<LABEL>"`

Specifies metadata fields that a provider may expect.

```
terraform {
  provider_meta {
    <DATA>
  }
  # . . .
}
```

Individual modules can populate the metadata fields independently of any provider configuration. Refer to [Provider Metadata](https://developer.hashicorp.com/terraform/internals/provider-meta) for additional information.

#### [](https://developer.hashicorp.com/terraform/language/terraform#summary-3)Summary

- Data type: Block.
- Default: None.

### [](https://developer.hashicorp.com/terraform/language/terraform#backend)`backend "<BACKEND_TYPE>"`

Specifies a mechanism for storing Terraform state files.

```
terraform {
  backend "<TYPE>" {
    <backend-configuration>
  }
  # . . .
}
```

The `backend` block takes a backend type as an argument. Refer to [Backend Configuration](https://developer.hashicorp.com/terraform/language/backend) for details about configuring the `backend` block.

You cannot configure a `backend` block when the configuration also contains a [`cloud` configuration](https://developer.hashicorp.com/terraform/language/terraform#terraform-cloud) for storing state data.

#### [](https://developer.hashicorp.com/terraform/language/terraform#summary-4)Summary

- Data type: Block.
- Default: [`local`](https://developer.hashicorp.com/terraform/language/backend/local)

### [](https://developer.hashicorp.com/terraform/language/terraform#cloud)`cloud`

Specifies a set of attributes that allow the Terraform configuration to connect to either HCP Terraform or a Terraform Enterprise installation.

```
terraform {
  cloud  {
    <cloud-configuration>
  }
  # . . .
}
```

HCP Terraform and Terraform Enterprise provide state storage, remote execution, and other benefits. Refer to the [HCP Terraform](https://developer.hashicorp.com/terraform/cloud-docs) and [Terraform Enterprise](https://developer.hashicorp.com/terraform/enterprise) documentation for additional information.

You can only provide one `cloud` block per configuration.

You cannot configure a `cloud` block when the configuration also contains a [`backend` configuration](https://developer.hashicorp.com/terraform/language/terraform#terraform-backend) for storing state data.

The `cloud` block cannot refer to named values, such as input variables, locals, or data source attributes.

#### [](https://developer.hashicorp.com/terraform/language/terraform#summary-5)Summary

- Data type: Block.
- Default: None.
- Example: [Connect to HCP Terraform](https://developer.hashicorp.com/terraform/language/terraform#connect-to-hcp-terraform)

### [](https://developer.hashicorp.com/terraform/language/terraform#organization)`organization`

Specifies the name of the organization you want to connect to.

```
terraform {
  cloud  {
    organization = "<organization-name>"
  }
  # . . .
}
```

Instead of hardcoding the organization as a string, you can alternatively use the [`TF_CLOUD_ORGANIZATION`](https://developer.hashicorp.com/terraform/language/terraform#tf_cloud_organization) environment variable.

#### [](https://developer.hashicorp.com/terraform/language/terraform#summary-6)Summary

- Data type: String
- Required when connecting to HCP Terraform
- Example: [Connect to HCP Terraform](https://developer.hashicorp.com/terraform/language/terraform#connect-to-hcp-terraform)

### [](https://developer.hashicorp.com/terraform/language/terraform#workspaces)`workspaces`

Specifies metadata for matching workspaces in HCP Terraform.

```
terraform {
  cloud  {
    workspaces {
      tags = [ "<workspace-tag>" ] # Mutually exclusive with `name`
      name = "<workspace-name>" # Mutually exclusive with `tags`
      project = "<project-name>"
    }            
  }
  # . . .
}
```

Terraform associates the configuration with workspaces managed in HCP Terraform that match the specified tags, name, or project. You can specify the following metadata in the `workspaces` block:

|Attribute|Description|Data type|
|---|---|---|
|`tags`|Specifies either a map of strings as key-value tags or a list of single-value, key-only tags. Terraform associates the configuration with workspaces that match all tags. New workspaces created from the working directory inherit the tags. You cannot set this attribute and the `name` attribute in the same configuration. Using a map type with both keys and values requires Terraform 1.10+.|Array of strings or map of strings|
|`name`|Specifies an HCP Terraform workspace name to associate the Terraform configuration with. You can only use the working directory with the workspace named in the configuration. You cannot manage the workspace from the Terraform CLI. You cannot set this attribute and the `tags` attribute in the same configuration.<br><br>Instead of hardcoding a single workspace as a string, you can alternatively use the [`TF_WORKSPACE`](https://developer.hashicorp.com/terraform/language/terraform#tf_workspace) environment variable.|String|
|`project`|Specifies the name of an HCP Terraform project. Terraform creates all workspaces that use this configuration in the project. Using the [`terraform workspace list` command](https://developer.hashicorp.com/terraform/cli/commands/workspace/list) in the working directory returns only workspaces in the specified project.<br><br>Instead of hardcoding the project as a string, you can alternatively use the [`TF_CLOUD_PROJECT`](https://developer.hashicorp.com/terraform/language/terraform#tf_cloud_project) environment variable.|String|

#### [](https://developer.hashicorp.com/terraform/language/terraform#summary-7)Summary

- Data type: Block.
- Required when connecting to HCP Terraform
- Example: [Connect to HCP Terraform](https://developer.hashicorp.com/terraform/language/terraform#connect-to-hcp-terraform)

### [](https://developer.hashicorp.com/terraform/language/terraform#hostname)`hostname`

Specifies the hostname for a Terraform Enterprise deployment.

```
terraform {
  cloud  {
    hostname = "app.terraform.io"
  }
  # . . .
}
```

Instead of hardcoding the hostname of the Terraform Enterprise deployment, you can alternatively use the [`TF_CLOUD_HOSTNAME`](https://developer.hashicorp.com/terraform/language/terraform#tf_cloud_hostname) environment variable.

#### [](https://developer.hashicorp.com/terraform/language/terraform#summary-8)Summary

- Data type: String.
- Required when connecting to Terraform Enterprise.
- Default: `app.terraform.io`
- Example: [Connect to Terraform Enterprise](https://developer.hashicorp.com/terraform/language/terraform#connect-to-terraform-enterprise)

### [](https://developer.hashicorp.com/terraform/language/terraform#token)`token`

Specifies a token for authenticating with HCP Terraform.

```
terraform {
  cloud  {
    token = "<token>"
  }
  # . . .
}
```

We recommend omitting the token from the configuration and either using the [`terraform login` command](https://developer.hashicorp.com/terraform/cli/commands/login) or manually configuring credentials in the [CLI configuration file](https://developer.hashicorp.com/terraform/cli/config/config-file#credentials) instead.

#### [](https://developer.hashicorp.com/terraform/language/terraform#summary-9)Summary

- Data type: String.
- Default: None.
- Example: [Connect to Terraform Enterprise](https://developer.hashicorp.com/terraform/language/terraform#connect-to-terraform-enterprise)

### [](https://developer.hashicorp.com/terraform/language/terraform#experiments)`experiments`

Specifies a list of experimental feature names that you want to opt into.

```
terraform {
  experiments = [ "<feature-name>" ]
  # . . .
}
```

In releases where experimental features are available, you can enable them on a per-module basis.

Experiments are subject to arbitrary changes in later releases and, depending on the outcome of the experiment, may change significantly before final release or may not be released in stable form at all. Breaking changes may appear in minor and patch releases. We do not recommend using experimental features in Terraform modules intended for production.

Modules with experiments enabled generate a warning on every `terraform plan` or `terraform apply` operation. If you want to try experimental features in a shared module, we recommend enabling the experiment only in alpha or beta releases of the module.

Refer to the [Terraform changelog](https://github.com/hashicorp/terraform/blob/main/CHANGELOG.md) for information about experiments and to monitor the release notes about experiment keywords that may be available.

#### [](https://developer.hashicorp.com/terraform/language/terraform#summary-10)Summary

- Data type: List.
- Default: None.

## [](https://developer.hashicorp.com/terraform/language/terraform#environment-variables-for-the-cloud-block)Environment variables for the `cloud` block

You can use environment variables to configure one or more `cloud` block attributes. This is helpful when you want to use the same Terraform configuration in different HCP Terraform organizations and projects. Terraform only uses these variables if you do not define corresponding attributes in your configuration. If you choose to configure the `cloud` block entirely through environment variables, you must still add an empty `cloud` block in your configuration file.

Warning

You can use environment variables to automate Terraform operations, which has specific security considerations. Refer to [Non-Interactive Workflows](https://developer.hashicorp.com/terraform/cloud-docs/run/cli#non-interactive-workflows) for details.

Use the following environment variables to configure the `cloud` block:

- [](https://developer.hashicorp.com/terraform/language/terraform#)
    
    [`TF_CLOUD_ORGANIZATION`](https://developer.hashicorp.com/terraform/language/terraform#tf_cloud_organization): Specifies the name of the organization. Terraform reads this variable when `organization` is omitted from the `cloud` block`. If both are specified, the configuration takes precedence.
    
- [](https://developer.hashicorp.com/terraform/language/terraform#)
    
    [`TF_CLOUD_HOSTNAME`](https://developer.hashicorp.com/terraform/language/terraform#tf_cloud_hostname): Specifies the hostname of a Terraform Enterprise installation. Terraform reads this when `hostname` is omitted from the `cloud` block. If both are specified, the configuration takes precedence.
    
- [](https://developer.hashicorp.com/terraform/language/terraform#)
    
    [`TF_CLOUD_PROJECT`](https://developer.hashicorp.com/terraform/language/terraform#tf_cloud_project): Specifies the name of an HCP Terraform project. Terraform reads this when `workspaces.project` is omitted from the `cloud` block. If both are specified, the cloud block configuration takes precedence.
    
- [](https://developer.hashicorp.com/terraform/language/terraform#)
    
    [`TF_WORKSPACE`](https://developer.hashicorp.com/terraform/language/terraform#tf_workspace): Specifies the name of a single HCP Terraform workspace. Terraform reads this when `workspaces` is omitted from the `cloud` block. HCP Terraform does not create a new workspace from this variable. The workspace must already exist in the specified organization. You can set `TF_WORKSPACE` if the `cloud` block uses tags. However, you must include the value of `TF_WORKSPACE` in the set of tags. This variable also selects the workspace in your local environment. Refer to [TF_WORKSPACE](https://developer.hashicorp.com/terraform/cli/config/environment-variables#tf_workspace) for details.
    

## [](https://developer.hashicorp.com/terraform/language/terraform#examples)Examples

The following examples show how to write configuration for common use cases.

### [](https://developer.hashicorp.com/terraform/language/terraform#add-a-provider)Add a provider

The following configuration requires the `aws` provider version 2.7.0 or later from the public Terraform registry:

```
terraform {
  required_providers {
    aws = {
      version = ">= 2.7.0"
      source = "hashicorp/aws"
    }
  }
}
```

### [](https://developer.hashicorp.com/terraform/language/terraform#connect-to-hcp-terraform)Connect to HCP Terraform

In the following example, the configuration links the working directory to workspaces in the `example_corp` organization that contain the `layer=app` tag:

```
terraform {
  cloud {
    organization = "example_corp"
    workspaces {
      tags = {
        layer = "app"
      }
    }
  }
}
```

### [](https://developer.hashicorp.com/terraform/language/terraform#connect-to-terraform-enterprise)Connect to Terraform Enterprise

In the following example, the configuration links the working directory to workspaces in the `example_corp` organization that contain the `app` key-only tag. Key-only tags must be used with versions of Terraform Enterprise prior to v202411-1 or versions of Terraform prior to v1.10. The `hostname` field is required in the configuration unless you use the `TF_CLOUD_HOSTNAME` environment variable:

```
terraform {
  cloud {
    organization = "example_corp"
    hostname = "my.terraform-enterprise.host"
    workspaces {
      tags = ["app"]
    }
  }
}
```

### [](https://developer.hashicorp.com/terraform/language/terraform#connect-to-terraform-enterprise-using-environment-variables)Connect to Terraform Enterprise using environment variables

In the following example, Terraform checks the `TF_CLOUD_ORGANIZATION` and `TF_CLOUD_HOSTNAME` environment variables and automatically populates the `organization` and `hostname` arguments. During initialization, the local Terraform CLI connects the working directory to Terraform Enterprise using those values. As a result, Terraform links the configuration to either HCP Terraform or Terraform Enterprise and allows teams to reuse the configuration in different continuous integration pipelines:

```
terraform {
  cloud {
    workspaces {
      tags = ["app"]
    }
  }
}
```

### 3c       Write Terraform configuration using multiple providers

### 3d       Describe how Terraform finds and fetches providers

# Provider Configuration

Providers allow Terraform to interact with cloud providers, SaaS providers, and other APIs.

Some providers require you to configure them with endpoint URLs, cloud regions, or other settings before Terraform can use them. This page documents how to configure settings for providers.

Additionally, all Terraform configurations must declare which providers they require so that Terraform can install and use them. The [Provider Requirements](https://developer.hashicorp.com/terraform/language/providers/requirements) page documents how to declare providers so Terraform can install them.

## [](https://developer.hashicorp.com/terraform/language/providers/configuration#provider-configuration-1)Provider Configuration

Provider configurations belong in the root module of a Terraform configuration. (Child modules receive their provider configurations from the root module; for more information, see [The Module `providers` Meta-Argument](https://developer.hashicorp.com/terraform/language/meta-arguments/module-providers) and [Module Development: Providers Within Modules](https://developer.hashicorp.com/terraform/language/modules/develop/providers).)

A provider configuration is created using a `provider` block:

```
provider "google" {
  project = "acme-app"
  region  = "us-central1"
}
```

The name given in the block header (`"google"` in this example) is the [local name](https://developer.hashicorp.com/terraform/language/providers/requirements#local-names) of the provider to configure. This provider should already be included in a `required_providers` block.

The body of the block (between `{` and `}`) contains configuration arguments for the provider. Most arguments in this section are defined by the provider itself; in this example both `project` and `region` are specific to the `google` provider.

You can use [expressions](https://developer.hashicorp.com/terraform/language/expressions) in the values of these configuration arguments, but can only reference values that are known before the configuration is applied. This means you can safely reference input variables, but not attributes exported by resources (with an exception for resource arguments that are specified directly in the configuration).

A provider's documentation should list which configuration arguments it expects. For providers distributed on the [Terraform Registry](https://registry.terraform.io/), versioned documentation is available on each provider's page, via the "Documentation" link in the provider's header.

Some providers can use shell environment variables (or other alternate sources, like VM instance profiles) as values for some of their arguments; when available, we recommend using this as a way to keep credentials out of your version-controlled Terraform code.

There are also two "meta-arguments" that are defined by Terraform itself and available for all `provider` blocks:

- [`alias`, for using the same provider with different configurations for different resources](https://developer.hashicorp.com/terraform/language/providers/configuration#alias-multiple-provider-configurations)
- [`version`, which we no longer recommend](https://developer.hashicorp.com/terraform/language/providers/configuration#provider-versions) (use [provider requirements](https://developer.hashicorp.com/terraform/language/providers/requirements) instead)

Unlike many other objects in the Terraform language, a `provider` block may be omitted if its contents would otherwise be empty. Terraform assumes an empty default configuration for any provider that is not explicitly configured.

## [](https://developer.hashicorp.com/terraform/language/providers/configuration#alias-multiple-provider-configurations)`alias`: Multiple Provider Configurations

You can optionally define multiple configurations for the same provider, and select which one to use on a per-resource or per-module basis. The primary reason for this is to support multiple regions for a cloud platform; other examples include targeting multiple Docker hosts, multiple Consul hosts, etc.

To create multiple configurations for a given provider, include multiple `provider` blocks with the same provider name. For each additional non-default configuration, use the `alias` meta-argument to provide an extra name segment. For example:

```
# The default provider configuration; resources that begin with `aws_` will use
# it as the default, and it can be referenced as `aws`.
provider "aws" {
  region = "us-east-1"
}

# Additional provider configuration for west coast region; resources can
# reference this as `aws.west`.
provider "aws" {
  alias  = "west"
  region = "us-west-2"
}
```

To declare a configuration alias within a module in order to receive an alternate provider configuration from the parent module, add the `configuration_aliases` argument to that provider's `required_providers` entry. The following example declares both the `mycloud` and `mycloud.alternate` provider configuration names within the containing module:

```
terraform {
  required_providers {
    mycloud = {
      source  = "mycorp/mycloud"
      version = "~> 1.0"
      configuration_aliases = [ mycloud.alternate ]
    }
  }
}
```

### [](https://developer.hashicorp.com/terraform/language/providers/configuration#default-provider-configurations)Default Provider Configurations

A `provider` block without an `alias` argument is the _default_ configuration for that provider. Resources that don't set the `provider` meta-argument will use the default provider configuration that matches the first word of the resource type name. (For example, an `aws_instance` resource uses the default `aws` provider configuration unless otherwise stated.)

If every explicit configuration of a provider has an alias, Terraform uses the implied empty configuration as that provider's default configuration. (If the provider has any required configuration arguments, Terraform will raise an error when resources default to the empty configuration.)

### [](https://developer.hashicorp.com/terraform/language/providers/configuration#referring-to-alternate-provider-configurations)Referring to Alternate Provider Configurations

When Terraform needs the name of a provider configuration, it expects a reference of the form `<PROVIDER NAME>.<ALIAS>`. In the example above, `aws.west` would refer to the provider with the `us-west-2` region.

These references are special expressions. Like references to other named entities (for example, `var.image_id`), they aren't strings and don't need to be quoted. But they are only valid in specific meta-arguments of `resource`, `data`, and `module` blocks, and can't be used in arbitrary expressions.

### [](https://developer.hashicorp.com/terraform/language/providers/configuration#selecting-alternate-provider-configurations)Selecting Alternate Provider Configurations

By default, resources use a default provider configuration (one without an `alias` argument) inferred from the first word of the resource type name.

To use an alternate provider configuration for a resource or data source, set its `provider` meta-argument to a `<PROVIDER NAME>.<ALIAS>` reference:

```
resource "aws_instance" "foo" {
  provider = aws.west

  # ...
}
```

To select alternate provider configurations for a child module, use its `providers` meta-argument to specify which provider configurations should be mapped to which local provider names inside the module:

```
module "aws_vpc" {
  source = "./aws_vpc"
  providers = {
    aws = aws.west
  }
}
```

Modules have some special requirements when passing in providers; see [The Module `providers` Meta-Argument](https://developer.hashicorp.com/terraform/language/meta-arguments/module-providers) for more details. In most cases, only _root modules_ should define provider configurations, with all child modules obtaining their provider configurations from their parents.

[](https://developer.hashicorp.com/terraform/language/providers/configuration#)

## [](https://developer.hashicorp.com/terraform/language/providers/configuration#version-deprecated)`version` (Deprecated)

The `version` meta-argument specifies a version constraint for a provider, and works the same way as the `version` argument in a [`required_providers` block](https://developer.hashicorp.com/terraform/language/providers/requirements). The version constraint in a provider configuration is only used if `required_providers` does not include one for that provider.

~**Warning:** The `version` argument in provider configurations is deprecated, and we will remove it in a future Terraform version.

In Terraform 0.13 and later, always declare provider version constraints in [the `required_providers` block](https://developer.hashicorp.com/terraform/language/providers/requirements).

# Provisioners

You can use provisioners to model specific actions on the local machine or on a remote machine in order to prepare servers or other infrastructure objects for service.

**Note:** We removed the Chef, Habitat, Puppet, and Salt Masterless provisioners in Terraform v0.15.0. Information about these legacy provisioners is still available in the documentation for [Terraform v1.1 (and earlier)](https://developer.hashicorp.com/terraform/language/v1.1.x/resources/provisioners/syntax).

## [](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax#provisioners-are-a-last-resort)Provisioners are a Last Resort

> **Hands-on:** Try the [Provision Infrastructure Deployed with Terraform](https://developer.hashicorp.com/terraform/tutorials/provision?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS) tutorials to learn about more declarative ways to handle provisioning actions.

Terraform includes the concept of provisioners as a measure of pragmatism, knowing that there are always certain behaviors that cannot be directly represented in Terraform's declarative model.

However, they also add a considerable amount of complexity and uncertainty to Terraform usage. Firstly, Terraform cannot model the actions of provisioners as part of a plan because they can in principle take any action. Secondly, successful use of provisioners requires coordinating many more details than Terraform usage usually requires: direct network access to your servers, issuing Terraform credentials to log in, making sure that all of the necessary external software is installed, etc.

The following sections describe some situations which can be solved with provisioners in principle, but where better solutions are also available. We do not recommend using provisioners for any of the use-cases described in the following sections.

Even if your specific use-case is not described in the following sections, we still recommend attempting to solve it using other techniques first, and use provisioners only if there is no other option.

### [](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax#passing-data-into-virtual-machines-and-other-compute-resources)Passing data into virtual machines and other compute resources

When deploying virtual machines or other similar compute resources, we often need to pass in data about other related infrastructure that the software on that server will need to do its job.

The various provisioners that interact with remote servers over SSH or WinRM can potentially be used to pass such data by logging in to the server and providing it directly, but most cloud computing platforms provide mechanisms to pass data to instances at the time of their creation such that the data is immediately available on system boot. For example:

- Alibaba Cloud: `user_data` on [`alicloud_instance`](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/instance) or [`alicloud_launch_template`](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/launch_template).
- Amazon EC2: `user_data` or `user_data_base64` on [`aws_instance`](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance), [`aws_launch_template`](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/launch_template), and [`aws_launch_configuration`](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/launch_configuration).
- Amazon Lightsail: `user_data` on [`aws_lightsail_instance`](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lightsail_instance).
- Microsoft Azure: `custom_data` on [`azurerm_virtual_machine`](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/virtual_machine) or [`azurerm_virtual_machine_scale_set`](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/virtual_machine_scale_set).
- Google Cloud Platform: `metadata` on [`google_compute_instance`](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_instance) or [`google_compute_instance_group`](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/compute_instance_group).
- Oracle Cloud Infrastructure: `metadata` or `extended_metadata` on [`oci_core_instance`](https://registry.terraform.io/providers/oracle/oci/) or [`oci_core_instance_configuration`](https://registry.terraform.io/providers/oracle/oci/).
- VMware vSphere: Attach a virtual CDROM to [`vsphere_virtual_machine`](https://registry.terraform.io/providers/hashicorp/vsphere/latest/docs/resources/virtual_machine) using the `cdrom` block, containing a file called `user-data.txt`.

Many official Linux distribution disk images include software called [cloud-init](https://cloudinit.readthedocs.io/en/latest/) that can automatically process in various ways data passed via the means described above, allowing you to run arbitrary scripts and do basic system configuration immediately during the boot process and without the need to access the machine over SSH.

> **Hands-on:** Try the [Provision Infrastructure with Cloud-Init](https://developer.hashicorp.com/terraform/tutorials/provision/cloud-init?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS) tutorial.

If you are building custom machine images, you can make use of the "user data" or "metadata" passed by the above means in whatever way makes sense to your application, by referring to your vendor's documentation on how to access the data at runtime.

This approach is _required_ if you intend to use any mechanism in your cloud provider for automatically launching and destroying servers in a group, because in that case individual servers will launch unattended while Terraform is not around to provision them.

Even if you're deploying individual servers directly with Terraform, passing data this way will allow faster boot times and simplify deployment by avoiding the need for direct network access from Terraform to the new server and for remote access credentials to be provided.

### [](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax#provisioning-files-using-cloud-config)Provisioning files using cloud-config

You can add the [`cloudinit_config`](https://registry.terraform.io/providers/hashicorp/cloudinit/latest/docs) data source to your Terraform configuration and specify the files you want to provision as `text/cloud-config` content. The `cloudinit_config` data source renders multi-part MIME configurations for use with [cloud-init](https://cloudinit.readthedocs.io/en/latest/). Pass the files in the `content` field as YAML-encoded configurations using the `write_files` block.

In the following example, the `my_cloud_config` data source specifies a `text/cloud-config` MIME part named `cloud.conf`. The `part.content` field is set to [`yamlencode`](https://developer.hashicorp.com/terraform/language/functions/yamlencode), which encodes the `write_files` JSON object as YAML so that the system can provision the referenced files.

```
data "cloudinit_config" "my_cloud_config" {
  gzip          = false
  base64_encode = false

  part {
    content_type = "text/cloud-config"
    filename     = "cloud.conf"
    content = yamlencode(
      {
        "write_files" : [
          {
            "path" : "/etc/foo.conf",
            "content" : "foo contents",
          },
          {
            "path" : "/etc/bar.conf",
            "content" : file("bar.conf"),
          },
          {
            "path" : "/etc/baz.conf",
            "content" : templatefile("baz.tpl.conf", { SOME_VAR = "qux" }),
          },
        ],
      }
    )
  }
}
```

### [](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax#running-configuration-management-software)Running configuration management software

As a convenience to users who are forced to use generic operating system distribution images, Terraform includes a number of specialized provisioners for launching specific configuration management products.

We strongly recommend not using these, and instead running system configuration steps during a custom image build process. For example, [HashiCorp Packer](https://www.packer.io/) offers a similar complement of configuration management provisioners and can run their installation steps during a separate build process, before creating a system disk image that you can deploy many times.

> **Hands-on:** Try the [Provision Infrastructure with Packer](https://developer.hashicorp.com/terraform/tutorials/provision/packer?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS) tutorial.

If you are using configuration management software that has a centralized server component, you will need to delay the _registration_ step until the final system is booted from your custom image. To achieve that, use one of the mechanisms described above to pass the necessary information into each instance so that it can register itself with the configuration management server immediately on boot, without the need to accept commands from Terraform over SSH or WinRM.

### [](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax#first-class-terraform-provider-functionality-may-be-available)First-class Terraform provider functionality may be available

It is technically possible to use the `local-exec` provisioner to run the CLI for your target system in order to create, update, or otherwise interact with remote objects in that system.

If you are trying to use a new feature of the remote system that isn't yet supported in its Terraform provider, that might be the only option. However, if there _is_ provider support for the feature you intend to use, prefer to use that provider functionality rather than a provisioner so that Terraform can be fully aware of the object and properly manage ongoing changes to it.

Even if the functionality you need is not available in a provider today, we suggest to consider `local-exec` usage a temporary workaround and to also open an issue in the relevant provider's repository to discuss adding first-class provider support. Provider development teams often prioritize features based on interest, so opening an issue is a way to record your interest in the feature.

Provisioners are used to execute scripts on a local or remote machine as part of resource creation or destruction. Provisioners can be used to bootstrap a resource, cleanup before destroy, run configuration management, etc.

## [](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax#how-to-use-provisioners)How to use Provisioners

**Note:** Provisioners should only be used as a last resort. For most common situations there are better alternatives. For more information, see the sections above.

If you are certain that provisioners are the best way to solve your problem after considering the advice in the sections above, you can add a `provisioner` block inside the `resource` block of a compute instance.

```
resource "aws_instance" "web" {
  # ...

  provisioner "local-exec" {
    command = "echo The server's IP address is ${self.private_ip}"
  }
}
```

The `local-exec` provisioner requires no other configuration, but most other provisioners must connect to the remote system using SSH or WinRM. You must include [a `connection` block](https://developer.hashicorp.com/terraform/language/resources/provisioners/connection) so that Terraform knows how to communicate with the server.

Terraform includes several built-in provisioners. You can also use third-party provisioners as plugins, by placing them in `%APPDATA%\terraform.d\plugins`, `~/.terraform.d/plugins`, or the same directory where the Terraform binary is installed. However, we do not recommend using any provisioners except the built-in `file`, `local-exec`, and `remote-exec` provisioners.

All provisioners support the `when` and `on_failure` meta-arguments, which are described below (see [Destroy-Time Provisioners](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax#destroy-time-provisioners) and [Failure Behavior](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax#failure-behavior)).

### [](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax#the-self-object)The `self` Object

Expressions in `provisioner` blocks cannot refer to their parent resource by name. Instead, they can use the special `self` object.

The `self` object represents the provisioner's parent resource, and has all of that resource's attributes. For example, use `self.public_ip` to reference an `aws_instance`'s `public_ip` attribute.

**Technical note:** Resource references are restricted here because references create dependencies. Referring to a resource by name within its own block would create a dependency cycle.

### [](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax#ephemeral-values)Ephemeral values

**Note**: Ephemeral values are available in Terraform v1.10 and later.

The configuration for a `provisioner` block may use ephemeral values, such as [`ephemeral` resources](https://developer.hashicorp.com/terraform/language/resources/ephemeral), [`ephemeral` local values](https://developer.hashicorp.com/terraform/language/values/locals#ephemeral-values), [`ephemeral` variables](https://developer.hashicorp.com/terraform/language/values/variables#ephemeral), or [`ephemeral` output values](https://developer.hashicorp.com/terraform/language/values/outputs#ephemeral-avoid-storing-values-in-state-or-plan-files).

Terraform does not store these values in your plan or state, or output them in logs.

### [](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax#sensitive-values)Sensitive values

The configuration for a `provisioner` block may use sensitive values, such as [`sensitive` variables](https://developer.hashicorp.com/terraform/language/values/variables#suppressing-values-in-cli-output) or [`sensitive` output values](https://developer.hashicorp.com/terraform/language/values/outputs#sensitive-suppressing-values-in-cli-output). Terraform suppresses sensitive values in all log output.

## [](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax#creation-time-provisioners)Creation-Time Provisioners

By default, provisioners run when the resource they are defined within is created. Creation-time provisioners are only run during _creation_, not during updating or any other lifecycle. They are meant as a means to perform bootstrapping of a system.

If a creation-time provisioner fails, the resource is marked as **tainted**. A tainted resource will be planned for destruction and recreation upon the next `terraform apply`. Terraform does this because a failed provisioner can leave a resource in a semi-configured state. Because Terraform cannot reason about what the provisioner does, the only way to ensure proper creation of a resource is to recreate it. This is tainting.

You can change this behavior by setting the `on_failure` attribute to `continue`. Refer to [Failure Behavior](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax#failure-behavior) for additional information.

## [](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax#destroy-time-provisioners)Destroy-Time Provisioners

If `when = destroy` is specified, the provisioner will run when the resource it is defined within is _destroyed_.

```
resource "aws_instance" "web" {
  # ...

  provisioner "local-exec" {
    when    = destroy
    command = "echo 'Destroy-time provisioner'"
  }
}
```

Destroy provisioners are run before the resource is destroyed. If they fail, Terraform will error and rerun the provisioners again on the next `terraform apply`. Due to this behavior, care should be taken for destroy provisioners to be safe to run multiple times.

**Note**: A resource's destroy-time provisioners do not run if you enable [`create_before_destroy`](https://developer.hashicorp.com/terraform/language/meta-arguments/lifecycle#syntax-and-arguments) on that resource.

Destroy-time provisioners can only run if they remain in the configuration at the time a resource is destroyed. If a resource block with a destroy-time provisioner is removed entirely from the configuration, its provisioner configurations are removed along with it and thus the destroy provisioner won't run. To work around this, a multi-step process can be used to safely remove a resource with a destroy-time provisioner:

- Update the resource configuration to include `count = 0`.
- Apply the configuration to destroy any existing instances of the resource, including running the destroy provisioner.
- Remove the resource block entirely from configuration, along with its `provisioner` blocks.
- Apply again, at which point no further action should be taken since the resources were already destroyed.

Because of this limitation, you should use destroy-time provisioners sparingly and with care.

**NOTE:** A destroy-time provisioner within a resource that is tainted _will not_ run. This includes resources that are marked tainted from a failed creation-time provisioner or tainted manually using `terraform taint`.

## [](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax#multiple-provisioners)Multiple Provisioners

Multiple provisioners can be specified within a resource. Multiple provisioners are executed in the order they're defined in the configuration file.

You may also mix and match creation and destruction provisioners. Only the provisioners that are valid for a given operation will be run. Those valid provisioners will be run in the order they're defined in the configuration file.

Example of multiple provisioners:

```
resource "aws_instance" "web" {
  # ...

  provisioner "local-exec" {
    command = "echo first"
  }

  provisioner "local-exec" {
    command = "echo second"
  }
}
```

## [](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax#failure-behavior)Failure Behavior

By default, provisioners that fail will also cause the Terraform apply itself to fail. The `on_failure` setting can be used to change this. The allowed values are:

- [](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax#)
    
    [`continue`](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax#continue) - Ignore the error and continue with creation or destruction.
    
- [](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax#)
    
    [`fail`](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax#fail) - Raise an error and stop applying (the default behavior). If this is a creation provisioner, taint the resource.
    

Example:

```
resource "aws_instance" "web" {
  # ...

  provisioner "local-exec" {
    command    = "echo The server's IP address is ${self.private_ip}"
    on_failure = continue
  }
}
```
## 4         Use Terraform outside the core workflow

### 4a       Describe when to use terraform import to import existing infrastructure into your Terraform state
# terraform fmt command

The `terraform fmt` command formats Terraform configuration file contents so that it matches the canonical format and style. This command applies a subset of the [Terraform language style conventions](https://developer.hashicorp.com/terraform/language/style#code-formatting), along with other minor adjustments for readability.

## [](https://developer.hashicorp.com/terraform/cli/commands/fmt#introduction)Introduction

Terraform commands that generate Terraform configuration produce configuration files that conform to the style imposed by `terraform fmt`. Follow this style in your files to ensure consistency.

The canonical format may change in minor ways between Terraform versions, so after upgrading Terraform we recommend to proactively run `terraform fmt` on your modules along with any other changes you are making to adopt the new version.

We do not consider new formatting rules in `terraform fmt` to be a breaking change in new versions of Terraform, but we minimize changes for configurations that already follow the style examples shown in the Terraform documentation. New formatting rules programmed into the `terraform fmt` command are usually expansions to include existing rules from the documentation. We recommend following the documented style even for decisions that `terraform fmt` does not yet apply automatically.

Formatting decisions are always subjective and so you might disagree with the decisions that `terraform fmt` makes. This command is intentionally opinionated and has no customization options because its primary goal is to encourage consistency of style between different Terraform codebases, even though the chosen style can never be everyone's favorite.

We recommend that you follow the style conventions applied by `terraform fmt` when writing Terraform modules, but if you find the results particularly objectionable then you may choose not to use this command, and possibly choose to use a third-party formatting tool instead. If you choose to use a third-party tool then you should also run it on files that are generated automatically by Terraform, to get consistency between your hand-written files and the generated files.

## [](https://developer.hashicorp.com/terraform/cli/commands/fmt#usage)Usage

Usage: `terraform fmt [options] [target...]`

By default, the `terraform fmt` command scans your current directory for configuration files. You can also provide a `target` argument to tell `terraform fmt` to scan:

- A directory
- A specific file
- Standard input by supplying a single dash (`-`).

The `terraform fmt` command accepts the following arguments.

|Flag|Description|Required|
|:--|:--|:--|
|`-list=false`|Prevents the command from listing the files containing formatting inconsistencies.|Optional|
|`-diff`|Displays the diffs of formatting changes.|Optional|
|`-write=false`|Prevents the command from overwriting files. This behavior is implied by the `-check` flag or if the input is from `STDIN`.|Optional|
|`-check`|Checks if the input is formatted. The exit status is `0` if the command's input is properly formatted. Otherwise, the exit status is non-zero, and the command outputs a list of improperly formatted file names.|Optional|
|`-recursive`|Processes files in subdirectories in addition to the current directory. By default, the command only processes the specified, or current, directory.|Optional|

### 4b       Use terraform state to view Terraform state

# terraform taint command

The `terraform taint` command marks specified objects in the Terraform state as tainted. Use the `terraform taint` command when objects become degraded or damaged. Terraform prompts you to replace the tainted objects in the next plan you create.

This command is deprecated. Instead, add the `-replace` option to your [`terraform apply` command](https://developer.hashicorp.com/terraform/cli/commands/apply).

## [](https://developer.hashicorp.com/terraform/cli/commands/taint#recommended-alternative)Recommended Alternative

For Terraform v0.15.2 and later, we recommend using the [`-replace` option](https://developer.hashicorp.com/terraform/cli/commands/plan#replace-address) with `terraform apply` to force Terraform to replace an object even though there are no configuration changes that would require it.

```
$ terraform apply -replace="aws_instance.example[0]"
```

We recommend the `-replace` option because the change will be reflected in the Terraform plan, letting you understand how it will affect your infrastructure before you take any externally-visible action. When you use `terraform taint`, other users could create a new plan against your tainted object before you can review the effects.

## [](https://developer.hashicorp.com/terraform/cli/commands/taint#usage)Usage

```
$ terraform taint [options] <address>
```

The `address` argument is the address of the resource to mark as tainted. The address is in [the resource address syntax](https://developer.hashicorp.com/terraform/cli/state/resource-addressing), as shown in the output from other commands, such as:

- [](https://developer.hashicorp.com/terraform/cli/commands/taint#)[`aws_instance.foo`](https://developer.hashicorp.com/terraform/cli/commands/taint#aws_instance-foo)
- [](https://developer.hashicorp.com/terraform/cli/commands/taint#)[`aws_instance.bar[1]`](https://developer.hashicorp.com/terraform/cli/commands/taint#aws_instance-bar-1)
- [](https://developer.hashicorp.com/terraform/cli/commands/taint#)[`aws_instance.baz[\"key\"]`](https://developer.hashicorp.com/terraform/cli/commands/taint#aws_instance-baz-key) (quotes in resource addresses must be escaped on the command line, so that they will not be interpreted by your shell)
- [](https://developer.hashicorp.com/terraform/cli/commands/taint#)[`module.foo.module.bar.aws_instance.qux`](https://developer.hashicorp.com/terraform/cli/commands/taint#module-foo-module-bar-aws_instance-qux)

This command accepts the following options:

- [](https://developer.hashicorp.com/terraform/cli/commands/taint#)
    
    [`-allow-missing`](https://developer.hashicorp.com/terraform/cli/commands/taint#allow-missing) - If specified, the command will succeed (exit code 0) even if the resource is missing. The command might still return an error for other situations, such as if there is a problem reading or writing the state.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/taint#)
    
    [`-lock=false`](https://developer.hashicorp.com/terraform/cli/commands/taint#lock-false) - Disables Terraform's default behavior of attempting to take a read/write lock on the state for the duration of the operation.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/taint#)
    
    [`-lock-timeout=DURATION`](https://developer.hashicorp.com/terraform/cli/commands/taint#lock-timeout-duration) - Unless locking is disabled with `-lock=false`, instructs Terraform to retry acquiring a lock for a period of time before returning an error. The duration syntax is a number followed by a time unit letter, such as "3s" for three seconds.
    

For configurations using the [HCP Terraform CLI integration](https://developer.hashicorp.com/terraform/cli/cloud) or the [`remote` backend](https://developer.hashicorp.com/terraform/language/backend/remote) only, `terraform taint` also accepts the option [`-ignore-remote-version`](https://developer.hashicorp.com/terraform/cli/cloud/command-line-arguments#ignore-remote-version).

For configurations using [the `local` backend](https://developer.hashicorp.com/terraform/language/backend/local) only, `terraform taint` also accepts the legacy options [`-state`, `-state-out`, and `-backup`](https://developer.hashicorp.com/terraform/language/backend/local#command-line-arguments).

### 4c       Describe when to enable verbose logging and what the outcome/value is

# terraform import command reference

The `terraform import` command imports existing resources into Terraform. Refer to [Import](https://developer.hashicorp.com/terraform/cli/import) for additional information.

> **Hands-on:** Try the [Import Terraform Configuration](https://developer.hashicorp.com/terraform/tutorials/state/state-import?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS) tutorial.

## [](https://developer.hashicorp.com/terraform/cli/commands/import#usage)Usage

Usage: `terraform import [options] ADDRESS ID`

Import will find the existing resource from ID and import it into your Terraform state at the given ADDRESS.

ADDRESS must be a valid [resource address](https://developer.hashicorp.com/terraform/cli/state/resource-addressing). Because any resource address is valid, the import command can import resources into modules as well as directly into the root of your state.

ID is dependent on the resource type being imported. For example, for AWS EC2 instances it is the instance ID (`i-abcd1234`) but for AWS Route53 zones it is the zone ID (`Z12ABC4UGMOZ2N`). Please reference the provider documentation for details on the ID format. If you're unsure, feel free to just try an ID. If the ID is invalid, you'll just receive an error message.

Warning: Terraform expects that each remote object it is managing will be bound to only one resource address, which is normally guaranteed by Terraform itself having created all objects. If you import existing objects into Terraform, be careful to import each remote object to only one Terraform resource address. If you import the same object multiple times, Terraform may exhibit unwanted behavior. For more information on this assumption, see [the State section](https://developer.hashicorp.com/terraform/language/state).

Instead of manually importing resources, you can add the `import` block to your Terraform configurations so that Terraform imports resources when you run the `terraform apply` command. Using Terraform configurations lets you automate resource imports as part of your CI/CD pipelines. Refer to the [`import` block reference documentation](https://developer.hashicorp.com/terraform/language/import) for additional information.

The command-line flags are all optional. The following flags are available:

- [](https://developer.hashicorp.com/terraform/cli/commands/import#)
    
    [`-config=path`](https://developer.hashicorp.com/terraform/cli/commands/import#config-path) - Path to directory of Terraform configuration files that configure the provider for import. This defaults to your working directory. If this directory contains no Terraform configuration files, the provider must be configured via manual input or environmental variables.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/import#)
    
    [`-input=true`](https://developer.hashicorp.com/terraform/cli/commands/import#input-true) - Whether to ask for input for provider configuration.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/import#)
    
    [`-lock=false`](https://developer.hashicorp.com/terraform/cli/commands/import#lock-false) - Don't hold a state lock during the operation. This is dangerous if others might concurrently run commands against the same workspace.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/import#)
    
    [`-lock-timeout=0s`](https://developer.hashicorp.com/terraform/cli/commands/import#lock-timeout-0s) - Duration to retry a state lock.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/import#)
    
    [`-no-color`](https://developer.hashicorp.com/terraform/cli/commands/import#no-color) - If specified, output won't contain any color.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/import#)
    
    [`-parallelism=n`](https://developer.hashicorp.com/terraform/cli/commands/import#parallelism-n) - Limit the number of concurrent operations as Terraform [walks the graph](https://developer.hashicorp.com/terraform/internals/graph#walking-the-graph). Defaults to 10.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/import#)
    
    [`-provider=provider`](https://developer.hashicorp.com/terraform/cli/commands/import#provider-provider) - **Deprecated** Override the provider configuration to use when importing the object. By default, Terraform uses the provider specified in the configuration for the target resource, and that is the best behavior in most cases.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/import#)
    
    [`-var 'foo=bar'`](https://developer.hashicorp.com/terraform/cli/commands/import#var-foo-bar) - Set a variable in the Terraform configuration. This flag can be set multiple times. Variable values are interpreted as [literal expressions](https://developer.hashicorp.com/terraform/language/expressions/types) in the Terraform language, so list and map values can be specified via this flag.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/import#)
    
    [`-var-file=foo`](https://developer.hashicorp.com/terraform/cli/commands/import#var-file-foo) - Set variables in the Terraform configuration from a [variable file](https://developer.hashicorp.com/terraform/language/values/variables#variable-definitions-tfvars-files). If `terraform.tfvars` or any `.auto.tfvars` files are present in the current directory, they are automatically loaded. Terraform loads `terraform.tfvars` first and the `.auto.tfvars` files after in alphabetical order. Any files specified by `-var-file` override any values set automatically from files in the working directory. This flag can be used multiple times. This is only useful with the `-config` flag.
    

For configurations using the [HCP Terraform CLI integration](https://developer.hashicorp.com/terraform/cli/cloud) or the [`remote` backend](https://developer.hashicorp.com/terraform/language/backend/remote) only, `terraform import` also accepts the option [`-ignore-remote-version`](https://developer.hashicorp.com/terraform/cli/cloud/command-line-arguments#ignore-remote-version).

For configurations using [the `local` backend](https://developer.hashicorp.com/terraform/language/backend/local) only, `terraform import` also accepts the legacy options [`-state`, `-state-out`, and `-backup`](https://developer.hashicorp.com/terraform/language/backend/local#command-line-arguments).

## [](https://developer.hashicorp.com/terraform/cli/commands/import#provider-configuration)Provider Configuration

Terraform will attempt to load configuration files that configure the provider being used for import. If no configuration files are present or no configuration for that specific provider is present, Terraform will prompt you for access credentials. You may also specify environmental variables to configure the provider.

The only limitation Terraform has when reading the configuration files is that the import provider configurations must not depend on non-variable inputs. For example, a provider configuration cannot depend on a data source.

As a working example, if you're importing AWS resources and you have a configuration file with the contents below, then Terraform will configure the AWS provider with this file.

```
variable "access_key" {}
variable "secret_key" {}

provider "aws" {
  access_key = var.access_key
  secret_key = var.secret_key
}
```

## [](https://developer.hashicorp.com/terraform/cli/commands/import#example-import-into-resource)Example: Import into Resource

This example will import an AWS instance into the `aws_instance` resource named `foo`:

```
$ terraform import aws_instance.foo i-abcd1234
```

## [](https://developer.hashicorp.com/terraform/cli/commands/import#example-import-into-module)Example: Import into Module

The example below will import an AWS instance into the `aws_instance` resource named `bar` into a module named `foo`:

```
$ terraform import module.foo.aws_instance.bar i-abcd1234
```

## [](https://developer.hashicorp.com/terraform/cli/commands/import#example-import-into-resource-configured-with-count)Example: Import into Resource configured with count

The example below will import an AWS instance into the first instance of the `aws_instance` resource named `baz` configured with [`count`](https://developer.hashicorp.com/terraform/language/meta-arguments/count):

```
$ terraform import 'aws_instance.baz[0]' i-abcd1234
```

## [](https://developer.hashicorp.com/terraform/cli/commands/import#example-import-into-resource-configured-with-for_each)Example: Import into Resource configured with for_each

The example below will import an AWS instance into the `"example"` instance of the `aws_instance` resource named `baz` configured with [`for_each`](https://developer.hashicorp.com/terraform/language/meta-arguments/for_each):

Linux, Mac OS, and UNIX:

```
$ terraform import 'aws_instance.baz["example"]' i-abcd1234
```

PowerShell:

```
$ terraform import 'aws_instance.baz[\"example\"]' i-abcd1234
```

Windows `cmd.exe`:

```
$ terraform import aws_instance.baz[\"example\"] i-abcd1234
```

# Workspaces

Each Terraform configuration has an associated [backend](https://developer.hashicorp.com/terraform/language/backend) that defines how Terraform executes operations and where Terraform stores persistent data, like [state](https://developer.hashicorp.com/terraform/language/state/purpose).

The persistent data stored in the backend belongs to a workspace. The backend initially has only one workspace containing one Terraform state associated with that configuration. Some backends support multiple named workspaces, allowing multiple states to be associated with a single configuration. The configuration still has only one backend, but you can deploy multiple distinct instances of that configuration without configuring a new backend or changing authentication credentials.

**Note**: The Terraform CLI workspaces are different from [workspaces in HCP Terraform](https://developer.hashicorp.com/terraform/cloud-docs/workspaces). Refer to [Connect to HCP Terraform](https://developer.hashicorp.com/terraform/cli/cloud/settings) for details about migrating a configuration with multiple workspaces to HCP Terraform.

## [](https://developer.hashicorp.com/terraform/language/state/workspaces#backends-supporting-multiple-workspaces)Backends Supporting Multiple Workspaces

You can use multiple workspaces with the following backends:

- [AzureRM](https://developer.hashicorp.com/terraform/language/backend/azurerm)
- [Consul](https://developer.hashicorp.com/terraform/language/backend/consul)
- [COS](https://developer.hashicorp.com/terraform/language/backend/cos)
- [GCS](https://developer.hashicorp.com/terraform/language/backend/gcs)
- [Kubernetes](https://developer.hashicorp.com/terraform/language/backend/kubernetes)
- [Local](https://developer.hashicorp.com/terraform/language/backend/local)
- [OSS](https://developer.hashicorp.com/terraform/language/backend/oss)
- [Postgres](https://developer.hashicorp.com/terraform/language/backend/pg)
- [Remote](https://developer.hashicorp.com/terraform/language/backend/remote)
- [S3](https://developer.hashicorp.com/terraform/language/backend/s3)

## [](https://developer.hashicorp.com/terraform/language/state/workspaces#using-workspaces)Using Workspaces

**Important:** Workspaces are not appropriate for system decomposition or deployments requiring separate credentials and access controls. Refer to [Use Cases](https://developer.hashicorp.com/terraform/cli/workspaces#use-cases) in the Terraform CLI documentation for details and recommended alternatives.

Terraform starts with a single, default workspace named `default` that you cannot delete. If you have not created a new workspace, you are using the default workspace in your Terraform working directory.

When you run `terraform plan` in a new workspace, Terraform does not access existing resources in other workspaces. These resources still physically exist, but you must switch workspaces to manage them.

Refer to the [Terraform CLI workspaces](https://developer.hashicorp.com/terraform/cli/workspaces) documentation for full details about how to create and use workspaces.

## [](https://developer.hashicorp.com/terraform/language/state/workspaces#current-workspace-interpolation)Current Workspace Interpolation

Within your Terraform configuration, you may include the name of the current workspace using the `${terraform.workspace}` interpolation sequence. This can be used anywhere interpolations are allowed.

Referencing the current workspace is useful for changing behavior based on the workspace. For example, for non-default workspaces, it may be useful to spin up smaller cluster sizes. For example:

```
resource "aws_instance" "example" {
  count = terraform.workspace == "default" ? 5 : 1

  # ... other arguments
}
```

Another popular use case is using the workspace name as part of naming or tagging behavior:

```
resource "aws_instance" "example" {
  tags = {
    Name = "web - ${terraform.workspace}"
  }

  # ... other arguments
}
```

# terraform state commands

The `terraform state` commands enable advanced state management.

## [](https://developer.hashicorp.com/terraform/cli/commands/state#introduction)Introduction

You can use the `terraform state` commands to modify the [Terraform state](https://developer.hashicorp.com/terraform/language/state) instead modifying the state directly.

## [](https://developer.hashicorp.com/terraform/cli/commands/state#usage)Usage

Usage: `terraform state <subcommand> [options] [args]`

Refer to the following subcommands for additional information:

- [`terraform state list`](https://developer.hashicorp.com/terraform/cli/commands/state/list)
- [`terraform state mv`](https://developer.hashicorp.com/terraform/cli/commands/state/mv)
- [`terraform state pull`](https://developer.hashicorp.com/terraform/cli/commands/state/pull)
- [`terraform state replace-provider`](https://developer.hashicorp.com/terraform/cli/commands/state/replace-provider)
- [`terraform state rm`](https://developer.hashicorp.com/terraform/cli/commands/state/rm)
- [`terraform state show`](https://developer.hashicorp.com/terraform/cli/commands/state/show)

## [](https://developer.hashicorp.com/terraform/cli/commands/state#remote-state)Remote State

The Terraform state subcommands all work with remote state just as if it was local state. Reads and writes may take longer than normal as each read and each write do a full network roundtrip. Otherwise, backups are still written to disk and the CLI usage is the same as if it were local state.

## [](https://developer.hashicorp.com/terraform/cli/commands/state#backups)Backups

All `terraform state` subcommands that modify the state write backup files. The path of these backup file can be controlled with `-backup`.

Subcommands that are read-only (such as [list](https://developer.hashicorp.com/terraform/cli/commands/state/list)) do not write any backup files since they aren't modifying the state.

Note that backups for state modification _can not be disabled_. Due to the sensitivity of the state file, Terraform forces every state modification command to write a backup file. You'll have to remove these files manually if you don't want to keep them around.

## [](https://developer.hashicorp.com/terraform/cli/commands/state#command-line-friendly)Command-Line Friendly

The output and command-line structure of the state subcommands is designed to be usable with Unix command-line tools such as grep, awk, and similar PowerShell commands.

For advanced filtering and modification, we recommend piping Terraform state subcommands together with other command line tools.
## 5         Interact with Terraform modules

### 5a       Contrast and use different module source options including the public Terraform Module Registry

# Module Blocks

> **Hands-on:** Try the [Reuse Configuration with Modules](https://developer.hashicorp.com/terraform/tutorials/modules?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS) tutorials.

A _module_ is a container for multiple resources that are used together.

Every Terraform configuration has at least one module, known as its _root module_, which consists of the resources defined in the `.tf` files in the main working directory.

A module can call other modules, which lets you include the child module's resources into the configuration in a concise way. Modules can also be called multiple times, either within the same configuration or in separate configurations, allowing resource configurations to be packaged and re-used.

This page describes how to call one module from another. For more information about creating re-usable child modules, see [Module Development](https://developer.hashicorp.com/terraform/language/modules/develop).

## [](https://developer.hashicorp.com/terraform/language/modules/syntax#calling-a-child-module)Calling a Child Module

To _call_ a module means to include the contents of that module into the configuration with specific values for its [input variables](https://developer.hashicorp.com/terraform/language/values/variables). Modules are called from within other modules using `module` blocks:

```
module "servers" {
  source = "./app-cluster"

  servers = 5
}
```

A module that includes a `module` block like this is the _calling module_ of the child module.

The label immediately after the `module` keyword is a local name, which the calling module can use to refer to this instance of the module.

Within the block body (between `{` and `}`) are the arguments for the module. Module calls use the following kinds of arguments:

- The `source` argument is mandatory for all modules.
    
- The `version` argument is recommended for modules from a registry.
    
- Most other arguments correspond to [input variables](https://developer.hashicorp.com/terraform/language/values/variables) defined by the module. (The `servers` argument in the example above is one of these.)
    
- Terraform defines a few other meta-arguments that can be used with all modules, including `for_each` and `depends_on`.
    

### [](https://developer.hashicorp.com/terraform/language/modules/syntax#source)Source

All modules **require** a `source` argument, which is a meta-argument defined by Terraform. Its value is either the path to a local directory containing the module's configuration files, or a remote module source that Terraform should download and use. This value must be a literal string with no template sequences; arbitrary expressions are not allowed. For more information on possible values for this argument, see [Module Sources](https://developer.hashicorp.com/terraform/language/modules/sources).

The same source address can be specified in multiple `module` blocks to create multiple copies of the resources defined within, possibly with different variable values.

After adding, removing, or modifying `module` blocks, you must re-run `terraform init` to allow Terraform the opportunity to adjust the installed modules. By default this command will not upgrade an already-installed module; use the `-upgrade` option to instead upgrade to the newest available version.

### [](https://developer.hashicorp.com/terraform/language/modules/syntax#version)Version

When using modules installed from a module registry, we recommend explicitly constraining the acceptable version numbers to avoid unexpected or unwanted changes.

Use the `version` argument in the `module` block to specify versions:

```
module "consul" {
  source  = "hashicorp/consul/aws"
  version = "0.0.5"

  servers = 3
}
```

The `version` argument accepts a [version constraint string](https://developer.hashicorp.com/terraform/language/expressions/version-constraints). Terraform will use the newest installed version of the module that meets the constraint; if no acceptable versions are installed, it will download the newest version that meets the constraint.

Version constraints are supported only for modules installed from a module registry, such as the public [Terraform Registry](https://registry.terraform.io/) or [HCP Terraform's private module registry](https://developer.hashicorp.com/terraform/cloud-docs/registry). Other module sources can provide their own versioning mechanisms within the source string itself, or might not support versions at all. In particular, modules sourced from local file paths do not support `version`; since they're loaded from the same source repository, they always share the same version as their caller.

### [](https://developer.hashicorp.com/terraform/language/modules/syntax#meta-arguments)Meta-arguments

Along with `source` and `version`, Terraform defines a few more optional meta-arguments that have special meaning across all modules, described in more detail in the following pages:

- [](https://developer.hashicorp.com/terraform/language/modules/syntax#)
    
    [`count`](https://developer.hashicorp.com/terraform/language/modules/syntax#count) - Creates multiple instances of a module from a single `module` block. See [the `count` page](https://developer.hashicorp.com/terraform/language/meta-arguments/count) for details.
    
- [](https://developer.hashicorp.com/terraform/language/modules/syntax#)
    
    [`for_each`](https://developer.hashicorp.com/terraform/language/modules/syntax#for_each) - Creates multiple instances of a module from a single `module` block. See [the `for_each` page](https://developer.hashicorp.com/terraform/language/meta-arguments/for_each) for details.
    
- [](https://developer.hashicorp.com/terraform/language/modules/syntax#)
    
    [`providers`](https://developer.hashicorp.com/terraform/language/modules/syntax#providers) - Passes provider configurations to a child module. See [the `providers` page](https://developer.hashicorp.com/terraform/language/meta-arguments/module-providers) for details. If not specified, the child module inherits all of the default (un-aliased) provider configurations from the calling module.
    
- [](https://developer.hashicorp.com/terraform/language/modules/syntax#)
    
    [`depends_on`](https://developer.hashicorp.com/terraform/language/modules/syntax#depends_on) - Creates explicit dependencies between the entire module and the listed targets. See [the `depends_on` page](https://developer.hashicorp.com/terraform/language/meta-arguments/depends_on) for details.
    

Terraform does not use the `lifecycle` argument. However, the `lifecycle` block is reserved for future versions.## Accessing Module Output Values

The resources defined in a module are encapsulated, so the calling module cannot access their attributes directly. However, the child module can declare [output values](https://developer.hashicorp.com/terraform/language/values/outputs) to selectively export certain values to be accessed by the calling module.

For example, if the `./app-cluster` module referenced in the example above exported an output value named `instance_ids` then the calling module can reference that result using the expression `module.servers.instance_ids`:

```
resource "aws_elb" "example" {
  # ...

  instances = module.servers.instance_ids
}
```

For more information about referring to named values, see [Expressions](https://developer.hashicorp.com/terraform/language/expressions).

## [](https://developer.hashicorp.com/terraform/language/modules/syntax#transferring-resource-state-into-modules)Transferring Resource State Into Modules

Moving `resource` blocks from one module into several child modules causes Terraform to see the new location as an entirely different resource. As a result, Terraform plans to destroy all resource instances at the old address and create new instances at the new address.

To preserve existing objects, you can use [refactoring blocks](https://developer.hashicorp.com/terraform/language/modules/develop/refactoring) to record the old and new addresses for each resource instance. This directs Terraform to treat existing objects at the old addresses as if they had originally been created at the corresponding new addresses.

## [](https://developer.hashicorp.com/terraform/language/modules/syntax#replacing-resources-within-a-module)Replacing resources within a module

You may have an object that needs to be replaced with a new object for a reason that isn't automatically visible to Terraform, such as if a particular virtual machine is running on degraded underlying hardware. In this case, you can use [the `-replace=...` planning option](https://developer.hashicorp.com/terraform/cli/commands/plan#replace-address) to force Terraform to propose replacing that object.

If the object belongs to a resource within a nested module, specify the full path to that resource including all of the nested module steps leading to it. For example:

```
$ terraform plan -replace=module.example.aws_instance.example
```

The above selects a `resource "aws_instance" "example"` declared inside a `module "example"` child module declared inside your root module.

Because replacing is a very disruptive action, Terraform only allows selecting individual resource instances. There is no syntax to force replacing _all_ resource instances belonging to a particular module.

## [](https://developer.hashicorp.com/terraform/language/modules/syntax#removing-modules)Removing Modules

**Note:** The `removed` block is available in Terraform v1.7 and later. For earlier Terraform versions, you can use the [`terraform state rm` CLI command](https://developer.hashicorp.com/terraform/cli/commands/state/rm) as a separate step.

To remove a module from Terraform, simply delete the module call from your Terraform configuration.

By default, after you remove the `module` block, Terraform will plan to destroy any resources it is managing that were declared in that module. This is because when you remove the module call, that module's configuration is no longer included in your Terraform configuration.

Sometimes you may wish to remove a module from your Terraform configuration without destroying the real infrastructure objects it manages. In this case, the resources will be removed from the [Terraform state](https://developer.hashicorp.com/terraform/language/state), but the real infrastructure objects will not be destroyed.

To declare that a module was removed from Terraform configuration but that its managed objects should not be destroyed, remove the `module` block from your configuration and replace it with a `removed` block:

```
removed {
  from = module.example

  lifecycle {
    destroy = false
  }
}
```

The `from` argument is the address of the module you want to remove, without any instance keys (such as "module.example[1]").

The `lifecycle` block is required. The `destroy` argument determines whether Terraform will attempt to destroy the objects managed by the module or not. A value of `false` means that Terraform will remove the resources from state without destroying them.
### 5b       Interact with module inputs and outputs

### 5c       Describe variable scope within modules/child modules

# Input Variables

> **Hands-on:** Try the [Customize Terraform Configuration with Variables](https://developer.hashicorp.com/terraform/tutorials/configuration-language/variables?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS) tutorial.

Input variables let you customize aspects of Terraform modules without altering the module's own source code. This functionality allows you to share modules across different Terraform configurations, making your module composable and reusable.

When you declare variables in the root module of your configuration, you can set their values using CLI options and environment variables. When you declare them in [child modules](https://developer.hashicorp.com/terraform/language/modules), the calling module should pass values in the `module` block.

If you're familiar with traditional programming languages, it can be useful to compare Terraform modules to function definitions:

- Input variables are like function arguments.
- [Output values](https://developer.hashicorp.com/terraform/language/values/outputs) are like function return values.
- [Local values](https://developer.hashicorp.com/terraform/language/values/locals) are like a function's temporary local variables.

**Note:** For brevity, input variables are often referred to as just "variables" or "Terraform variables" when it is clear from context what sort of variable is being discussed. Other kinds of variables in Terraform include _environment variables_ (set by the shell where Terraform runs) and _expression variables_ (used to indirectly represent a value in an [expression](https://developer.hashicorp.com/terraform/language/expressions)).

## [](https://developer.hashicorp.com/terraform/language/values/variables#declaring-an-input-variable)Declaring an Input Variable

Each input variable accepted by a module must be declared using a `variable` block:

```
variable "image_id" {
  type = string
}

variable "availability_zone_names" {
  type    = list(string)
  default = ["us-west-1a"]
}

variable "docker_ports" {
  type = list(object({
    internal = number
    external = number
    protocol = string
  }))
  default = [
    {
      internal = 8300
      external = 8300
      protocol = "tcp"
    }
  ]
}
```

The label after the `variable` keyword is a name for the variable, which must be unique among all variables in the same module. This name is used to assign a value to the variable from outside and to reference the variable's value from within the module.

The name of a variable can be any valid [identifier](https://developer.hashicorp.com/terraform/language/syntax/configuration#identifiers) _except_ the following: `source`, `version`, `providers`, `count`, `for_each`, `lifecycle`, `depends_on`, `locals`.

These names are reserved for meta-arguments in [module configuration blocks](https://developer.hashicorp.com/terraform/language/modules/syntax), and cannot be declared as variable names.

## [](https://developer.hashicorp.com/terraform/language/values/variables#arguments)Arguments

Terraform CLI defines the following optional arguments for variable declarations:

- [`default`](https://developer.hashicorp.com/terraform/language/values/variables#default-values) - A default value which then makes the variable optional.
- [`type`](https://developer.hashicorp.com/terraform/language/values/variables#type-constraints) - This argument specifies what value types are accepted for the variable.
- [`description`](https://developer.hashicorp.com/terraform/language/values/variables#input-variable-documentation) - This specifies the input variable's documentation.
- [`validation`](https://developer.hashicorp.com/terraform/language/values/variables#custom-validation-rules) - A block to define validation rules, usually in addition to type constraints.
- [`ephemeral`](https://developer.hashicorp.com/terraform/language/values/variables#exclude-values-from-state) - This variable is available during runtime, but not written to state or plan files.
- [`sensitive`](https://developer.hashicorp.com/terraform/language/values/variables#suppressing-values-in-cli-output) - Limits Terraform UI output when the variable is used in configuration.
- [`nullable`](https://developer.hashicorp.com/terraform/language/values/variables#disallowing-null-input-values) - Specify if the variable can be `null` within the module.

### [](https://developer.hashicorp.com/terraform/language/values/variables#default-values)Default values

The variable declaration can also include a `default` argument. If present, the variable is considered to be _optional_ and the default value will be used if no value is set when calling the module or running Terraform. The `default` argument requires a literal value and cannot reference other objects in the configuration.

### [](https://developer.hashicorp.com/terraform/language/values/variables#type-constraints)Type Constraints

The `type` argument in a `variable` block allows you to restrict the [type of value](https://developer.hashicorp.com/terraform/language/expressions/types) that will be accepted as the value for a variable. If no type constraint is set then a value of any type is accepted.

While type constraints are optional, we recommend specifying them; they can serve as helpful reminders for users of the module, and they allow Terraform to return a helpful error message if the wrong type is used.

Type constraints are created from a mixture of type keywords and type constructors. The supported type keywords are:

- [](https://developer.hashicorp.com/terraform/language/values/variables#)[`string`](https://developer.hashicorp.com/terraform/language/values/variables#string)
- [](https://developer.hashicorp.com/terraform/language/values/variables#)[`number`](https://developer.hashicorp.com/terraform/language/values/variables#number)
- [](https://developer.hashicorp.com/terraform/language/values/variables#)[`bool`](https://developer.hashicorp.com/terraform/language/values/variables#bool)

The type constructors allow you to specify complex types such as collections:

- [](https://developer.hashicorp.com/terraform/language/values/variables#)[`list(<TYPE>)`](https://developer.hashicorp.com/terraform/language/values/variables#list)
- [](https://developer.hashicorp.com/terraform/language/values/variables#)[`set(<TYPE>)`](https://developer.hashicorp.com/terraform/language/values/variables#set)
- [](https://developer.hashicorp.com/terraform/language/values/variables#)[`map(<TYPE>)`](https://developer.hashicorp.com/terraform/language/values/variables#map)
- [](https://developer.hashicorp.com/terraform/language/values/variables#)[`object({<ATTR NAME> = <TYPE>, ... })`](https://developer.hashicorp.com/terraform/language/values/variables#object)
- [](https://developer.hashicorp.com/terraform/language/values/variables#)[`tuple([<TYPE>, ...])`](https://developer.hashicorp.com/terraform/language/values/variables#tuple)

The keyword `any` may be used to indicate that any type is acceptable. For more information on the meaning and behavior of these different types, as well as detailed information about automatic conversion of complex types, see [Type Constraints](https://developer.hashicorp.com/terraform/language/expressions/types).

If both the `type` and `default` arguments are specified, the given default value must be convertible to the specified type.

### [](https://developer.hashicorp.com/terraform/language/values/variables#input-variable-documentation)Input Variable Documentation

Because the input variables of a module are part of its user interface, you can briefly describe the purpose of each variable using the optional `description` argument:

```
variable "image_id" {
  type        = string
  description = "The id of the machine image (AMI) to use for the server."
}
```

The description should concisely explain the purpose of the variable and what kind of value is expected. This description string might be included in documentation about the module, and so it should be written from the perspective of the user of the module rather than its maintainer. For commentary for module maintainers, use comments.

### [](https://developer.hashicorp.com/terraform/language/values/variables#custom-validation-rules)Custom Validation Rules

This feature was introduced in Terraform CLI v0.13.0.

You can specify custom validation rules for a particular variable by adding a `validation` block within the corresponding `variable` block. The example below checks whether the AMI ID has the correct syntax.

```
variable "image_id" {
  type        = string
  description = "The id of the machine image (AMI) to use for the server."

  validation {
    condition     = length(var.image_id) > 4 && substr(var.image_id, 0, 4) == "ami-"
    error_message = "The image_id value must be a valid AMI id, starting with \"ami-\"."
  }
}
```

Refer to [Custom Condition Checks](https://developer.hashicorp.com/terraform/language/expressions/custom-conditions#input-variable-validation) for more details.

### [](https://developer.hashicorp.com/terraform/language/values/variables#exclude-values-from-state)Exclude values from state

**Note**: Ephemeral variables are available in Terraform v1.10 and later.

Setting a variable as `ephemeral` makes it available during runtime, but Terraform omits ephemeral values from state and plan files. Marking an input variable as `ephemeral` is useful for data that only needs to exist temporarily, such as a short-lived token or session identifier.

Mark an input variable as ephemeral by setting the `ephemeral` argument to `true`:

```
variable "session_token" {
  type      = string
  ephemeral = true
}
```

Ephemeral variables are available during the current Terraform operation, and Terraform does not store them in state or plan files. So, unlike [`sensitive`](https://developer.hashicorp.com/terraform/language/values/variables#sensitive) inputs, Terraform ensures ephemeral values are not available beyond the lifetime of the current Terraform run.

You can only reference ephemeral variables in specific contexts or Terraform throws an error. The following are valid contexts for referencing ephemeral variables:

- In a [write-only argument](https://developer.hashicorp.com/terraform/language/resources/ephemeral/write-only)
- Another ephemeral variable
- In [local values](https://developer.hashicorp.com/terraform/language/values/locals#ephemeral-values)
- In [ephemeral resources](https://developer.hashicorp.com/terraform/language/resources/ephemeral)
- In [ephemeral outputs](https://developer.hashicorp.com/terraform/language/values/outputs#ephemeral-avoid-storing-values-in-state-or-plan-files)
- Configuring providers in the `provider` block
- In [provisioner](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax) and [connection](https://developer.hashicorp.com/terraform/language/resources/provisioners/connection) blocks

If another expression references an `ephemeral` variable, that expression implicitly becomes ephemeral.

```
variable "password" {
  type      = string
  ephemeral = true
}

locals {
  # local.database_password is implicitly ephemeral because 
  # var.password is ephemeral.
  database_password = var.password
}
```

The `local.database_password` value is implicitly ephemeral because it depends on `var.password`.

### [](https://developer.hashicorp.com/terraform/language/values/variables#suppressing-values-in-cli-output)Suppressing Values in CLI Output

> **Hands-on:** Try the [Protect Sensitive Input Variables](https://developer.hashicorp.com/terraform/tutorials/configuration-language/sensitive-variables?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS) tutorial.

Setting a variable as `sensitive` prevents Terraform from showing its value in the `plan` or `apply` output, when you use that variable elsewhere in your configuration.

Terraform will still record sensitive values in the [state](https://developer.hashicorp.com/terraform/language/state), and so anyone who can access the state data will have access to the sensitive values in cleartext. If you want to omit a value from state, mark that value as [`ephemeral`](https://developer.hashicorp.com/terraform/language/values/variables#ephemeral). For more information, refer to [Sensitive Data in State](https://developer.hashicorp.com/terraform/language/state/sensitive-data).

Declare a variable as sensitive by setting the `sensitive` argument to `true`:

```
variable "user_information" {
  type = object({
    name    = string
    address = string
  })
  sensitive = true
}

resource "some_resource" "a" {
  name    = var.user_information.name
  address = var.user_information.address
}
```

Any expressions whose result depends on the sensitive variable will be treated as sensitive themselves, and so in the above example the two arguments of `resource "some_resource" "a"` will also be hidden in the plan output:

```
Terraform will perform the following actions:
 
  # some_resource.a will be created
  + resource "some_resource" "a" {
      + name    = (sensitive value)
      + address = (sensitive value)
    }
 
Plan: 1 to add, 0 to change, 0 to destroy.
```

In some cases where you use a sensitive variable inside a nested block, Terraform may treat the entire block as redacted. This happens for resource types where all of the blocks of a particular type are required to be unique, and so disclosing the content of one block might imply the content of a sibling block.

```
  # some_resource.a will be updated in-place
  ~ resource "some_resource" "a" {
      ~ nested_block {
          # At least one attribute in this block is (or was) sensitive,
          # so its contents will not be displayed.
        }
    }
```

A provider can also [declare an attribute as sensitive](https://developer.hashicorp.com/terraform/plugin/sdkv2/best-practices/sensitive-state#using-the-sensitive-flag), which will cause Terraform to hide it from regular output regardless of how you assign it a value. For more information, see [Sensitive Resource Attributes](https://developer.hashicorp.com/terraform/language/expressions/references#sensitive-resource-attributes).

If you use a sensitive value as part of an [output value](https://developer.hashicorp.com/terraform/language/values/outputs) then Terraform will require you to also mark the output value itself as sensitive, to confirm that you intended to export it.

#### [](https://developer.hashicorp.com/terraform/language/values/variables#cases-where-terraform-may-disclose-a-sensitive-variable)Cases where Terraform may disclose a sensitive variable

A `sensitive` variable is a configuration-centered concept, and values are sent to providers without any obfuscation. A provider error could disclose a value if that value is included in the error message. For example, a provider might return the following error even if "foo" is a sensitive value: `"Invalid value 'foo' for field"`

If a resource attribute is used as, or part of, the provider-defined resource id, an `apply` will disclose the value. In the example below, the `prefix` attribute has been set to a sensitive variable, but then that value ("jae") is later disclosed as part of the resource id:

```
  # random_pet.animal will be created
  + resource "random_pet" "animal" {
      + id        = (known after apply)
      + length    = 2
      + prefix    = (sensitive value)
      + separator = "-"
    }
 
Plan: 1 to add, 0 to change, 0 to destroy.
 
...
 
random_pet.animal: Creating...
random_pet.animal: Creation complete after 0s [id=jae-known-mongoose]
```

### [](https://developer.hashicorp.com/terraform/language/values/variables#disallowing-null-input-values)Disallowing Null Input Values

This feature is available in Terraform v1.1.0 and later.

The `nullable` argument in a variable block controls whether the module caller may assign the value `null` to the variable.

```
variable "example" {
  type     = string
  nullable = false
}
```

The default value for `nullable` is `true`. When `nullable` is `true`, `null` is a valid value for the variable, and the module configuration must always account for the possibility of the variable value being `null`. Passing a `null` value as a module input argument will override any `default` value.

Setting `nullable` to `false` ensures that the variable value will never be `null` within the module. If `nullable` is `false` and the variable has a `default` value, then Terraform uses the default when a module input argument is `null`.

The `nullable` argument only controls where the direct value of the variable may be `null`. For variables of collection or structural types, such as lists or objects, the caller may still use `null` in nested elements or attributes, as long as the collection or structure itself is not null.

## [](https://developer.hashicorp.com/terraform/language/values/variables#using-input-variable-values)Using Input Variable Values

Within the module that declared a variable, its value can be accessed from within [expressions](https://developer.hashicorp.com/terraform/language/expressions) as `var.<NAME>`, where `<NAME>` matches the label given in the declaration block:

**Note:** Input variables are _created_ by a `variable` block, but you _reference_ them as attributes on an object named `var`.

```
resource "aws_instance" "example" {
  instance_type = "t2.micro"
  ami           = var.image_id
}
```

The value assigned to a variable can only be accessed in expressions within the module where it was declared.

## [](https://developer.hashicorp.com/terraform/language/values/variables#assigning-values-to-root-module-variables)Assigning Values to Root Module Variables

When variables are declared in the root module of your configuration, they can be set in a number of ways:

- [In an HCP Terraform workspace](https://developer.hashicorp.com/terraform/cloud-docs/workspaces/variables).
- Individually, with the `-var` command line option.
- In variable definitions (`.tfvars`) files, either specified on the command line or automatically loaded.
- As environment variables.

The following sections describe these options in more detail. This section does not apply to _child_ modules, where values for input variables are instead assigned in the configuration of their parent module, as described in [_Modules_](https://developer.hashicorp.com/terraform/language/modules).

### [](https://developer.hashicorp.com/terraform/language/values/variables#variables-on-the-command-line)Variables on the Command Line

To specify individual variables on the command line, use the `-var` option when running the `terraform plan` and `terraform apply` commands:

```
terraform apply -var="image_id=ami-abc123"
terraform apply -var='image_id_list=["ami-abc123","ami-def456"]' -var="instance_type=t2.micro"
terraform apply -var='image_id_map={"us-east-1":"ami-abc123","us-east-2":"ami-def456"}'
```

The above examples show appropriate syntax for Unix-style shells, such as on Linux or macOS. For more information on shell quoting, including additional examples for Windows Command Prompt, see [Input Variables on the Command Line](https://developer.hashicorp.com/terraform/cli/commands/plan#input-variables-on-the-command-line).

You can use the `-var` option multiple times in a single command to set several different variables.

[](https://developer.hashicorp.com/terraform/language/values/variables#)

### [](https://developer.hashicorp.com/terraform/language/values/variables#variable-definitions-tfvars-files)Variable Definitions (`.tfvars`) Files

To set lots of variables, it is more convenient to specify their values in a _variable definitions file_ (with a filename ending in either `.tfvars` or `.tfvars.json`) and then specify that file on the command line with `-var-file`:

Linux, Mac OS, and UNIX:

```
terraform apply -var-file="testing.tfvars"
```

PowerShell:

```
terraform apply -var-file='testing.tfvars'
```

Windows `cmd.exe`:

```
terraform apply -var-file="testing.tfvars"
```

**Note:** This is how HCP Terraform passes [workspace variables](https://developer.hashicorp.com/terraform/cloud-docs/workspaces/variables) to Terraform.

A variable definitions file uses the same basic syntax as Terraform language files, but consists only of variable name assignments:

```
image_id = "ami-abc123"
availability_zone_names = [
  "us-east-1a",
  "us-west-1c",
]
```

Terraform also automatically loads a number of variable definitions files if they are present:

- Files named exactly `terraform.tfvars` or `terraform.tfvars.json`.
- Any files with names ending in `.auto.tfvars` or `.auto.tfvars.json`.

Files whose names end with `.json` are parsed instead as JSON objects, with the root object properties corresponding to variable names:

```
{
  "image_id": "ami-abc123",
  "availability_zone_names": ["us-west-1a", "us-west-1c"]
}
```

### [](https://developer.hashicorp.com/terraform/language/values/variables#environment-variables)Environment Variables

As a fallback for the other ways of defining variables, Terraform searches the environment of its own process for environment variables named `TF_VAR_` followed by the name of a declared variable.

This can be useful when running Terraform in automation, or when running a sequence of Terraform commands in succession with the same variables. For example, at a `bash` prompt on a Unix system:

```
$ export TF_VAR_image_id=ami-abc123
$ terraform plan
...
```

On operating systems where environment variable names are case-sensitive, Terraform matches the variable name exactly as given in configuration, and so the required environment variable name will usually have a mix of upper and lower case letters as in the above example.

### [](https://developer.hashicorp.com/terraform/language/values/variables#complex-typed-values)Complex-typed Values

When variable values are provided in a variable definitions file, you can use Terraform's usual syntax for [literal expressions](https://developer.hashicorp.com/terraform/language/expressions/types#literal-expressions) to assign complex-typed values, like lists and maps.

Some special rules apply to the `-var` command line option and to environment variables. For convenience, Terraform defaults to interpreting `-var` and environment variable values as literal strings, which need only shell quoting, and no special quoting for Terraform. For example, in a Unix-style shell:

```
$ export TF_VAR_image_id='ami-abc123'
```

However, if a root module variable uses a [type constraint](https://developer.hashicorp.com/terraform/language/values/variables#type-constraints) to require a complex value (list, set, map, object, or tuple), Terraform will instead attempt to parse its value using the same syntax used within variable definitions files, which requires careful attention to the string escaping rules in your shell:

```
$ export TF_VAR_availability_zone_names='["us-west-1b","us-west-1d"]'
```

For readability, and to avoid the need to worry about shell escaping, we recommend always setting complex variable values via variable definitions files. For more information on quoting and escaping for `-var` arguments, see [Input Variables on the Command Line](https://developer.hashicorp.com/terraform/cli/commands/plan#input-variables-on-the-command-line).

### [](https://developer.hashicorp.com/terraform/language/values/variables#values-for-undeclared-variables)Values for Undeclared Variables

If you have defined a variable value, but not its corresponding `variable {}` definition, you may get an error or warning depending on how you have provided that value.

If you provide values for undeclared variables defined as [environment variables](https://developer.hashicorp.com/terraform/language/values/variables#environment-variables) you will not get an error or warning. This is because environment variables may be declared but not used in all configurations that might be run.

If you provide values for undeclared variables defined [in a file](https://developer.hashicorp.com/terraform/language/values/variables#variable-definitions-tfvars-files) you will get a warning. This is to help in cases where you have provided a variable value _meant_ for a variable declaration, but perhaps there is a mistake in the value definition. For example, the following configuration:

```
variable "moose" {
  type = string
}
```

And the following `.tfvars` file:

```
mosse = "Moose"
```

Will cause Terraform to warn you that there is no variable declared `"mosse"`, which can help you spot this mistake.

If you use `.tfvars` files across multiple configurations and expect to continue to see this warning, you can use the [`-compact-warnings`](https://developer.hashicorp.com/terraform/cli/commands/plan#compact-warnings) option to simplify your output.

If you provide values for undeclared variables on the [command line](https://developer.hashicorp.com/terraform/language/values/variables#variables-on-the-command-line), Terraform will return an error. To avoid this error, either declare a variable block for the value, or remove the variable value from your Terraform call.

### [](https://developer.hashicorp.com/terraform/language/values/variables#variable-definition-precedence)Variable Definition Precedence

The above mechanisms for setting variables can be used together in any combination. If the same variable is assigned multiple values, Terraform uses the _last_ value it finds, overriding any previous values. Note that the same variable cannot be assigned multiple values within a single source.

Terraform loads variables in the following order, with later sources taking precedence over earlier ones:

- Environment variables
- The `terraform.tfvars` file, if present.
- The `terraform.tfvars.json` file, if present.
- Any `*.auto.tfvars` or `*.auto.tfvars.json` files, processed in lexical order of their filenames.
- Any `-var` and `-var-file` options on the command line, in the order they are provided. (This includes variables set by an HCP Terraform workspace.)

**Important:** In Terraform 0.12 and later, variables with map and object values behave the same way as other variables: the last value found overrides the previous values. This is a change from previous versions of Terraform, which would _merge_ map values instead of overriding them.

#### [](https://developer.hashicorp.com/terraform/language/values/variables#variable-precedence-within-terraform-tests)Variable precedence within Terraform tests

Within Terraform test files, you can specify variable values within `variables` blocks, either nested within `run` blocks or defined directly within the file.

Variables defined in this way take precedence over all other mechanisms during test execution, with variables defined within `run` blocks taking precedence over those defined within the file.

### 5d       Set module version

## 6         Use the core Terraform workflow

### 6a       Describe Terraform workflow ( Write -> Plan -> Create )

# Core Terraform Workflow Overview

The core Terraform workflow has three steps:

1. **Write** - Author infrastructure as code.
2. **Plan** - Preview changes before applying.
3. **Apply** - Provision reproducible infrastructure.

This guide walks through how each of these three steps plays out in the context of working as an individual practitioner, how they evolve when a team is collaborating on infrastructure, and how HCP Terraform enables this workflow to run smoothly for entire organizations.

## [](https://developer.hashicorp.com/terraform/intro/core-workflow#working-as-an-individual-practitioner)Working as an Individual Practitioner

Let's first walk through how these parts fit together as an individual working on infrastructure as code.

### [](https://developer.hashicorp.com/terraform/intro/core-workflow#write)Write

You write Terraform configuration just like you write code: in your editor of choice. It's common practice to store your work in a version controlled repository even when you're just operating as an individual.

```
# Create repository
$ git init my-infra && cd my-infra

Initialized empty Git repository in /.../my-infra/.git/

# Write initial config
$ vim main.tf

# Initialize Terraform
$ terraform init

Initializing provider plugins...
# ...
Terraform has been successfully initialized!
```

As you make progress on authoring your config, repeatedly running plans can help flush out syntax errors and ensure that your config is coming together as you expect.

```
# Make edits to config
$ vim main.tf

# Review plan
$ terraform plan

# Make additional edits, and repeat
$ vim main.tf
```

This parallels working on application code as an individual, where a tight feedback loop between editing code and running test commands is useful.

### [](https://developer.hashicorp.com/terraform/intro/core-workflow#plan)Plan

When the feedback loop of the Write step has yielded a change that looks good, it's time to commit your work and review the final plan.

```
$ git add main.tf
$ git commit -m 'Managing infrastructure as code!'

[main (root-commit) f735520] Managing infrastructure as code!
 1 file changed, 1 insertion(+)
```

Because `terraform apply` will display a plan for confirmation before proceeding to change any infrastructure, that's the command you run for final review.

```
$ terraform apply

An execution plan has been generated and is shown below.
# ...
```

### [](https://developer.hashicorp.com/terraform/intro/core-workflow#apply)Apply

After one last check, you are ready to tell Terraform to provision real infrastructure.

```
Do you want to perform these actions?

  Terraform will perform the actions described above.
  Only 'yes' will be accepted to approve.
  Enter a value: yes

# ...

Apply complete! Resources: 1 added, 0 changed, 0 destroyed.
```

At this point, it's common to push your version control repository to a remote location for safekeeping.

```
$ git remote add origin https://github.com/*user*/*repo*.git
$ git push origin main
```

This core workflow is a loop; the next time you want to make changes, you start the process over from the beginning.

Notice how closely this workflow parallels the process of writing application code or scripts as an individual? This is what we mean when we talk about Terraform enabling infrastructure as code.

## [](https://developer.hashicorp.com/terraform/intro/core-workflow#working-as-a-team)Working as a Team

Once multiple people are collaborating on Terraform configuration, new steps must be added to each part of the core workflow to ensure everyone is working together smoothly. You'll see that many of these steps parallel the workflow changes we make when we work on application code as teams rather than as individuals.

### [](https://developer.hashicorp.com/terraform/intro/core-workflow#write-1)Write

While each individual on a team still makes changes to Terraform configuration in their editor of choice, they save their changes to version control _branches_ to avoid colliding with each other's work. Working in branches enables team members to resolve mutually incompatible infrastructure changes using their normal merge conflict workflow.

```
$ git checkout -b add-load-balancer

Switched to a new branch 'add-load-balancer'
```

Running iterative plans is still useful as a feedback loop while authoring configuration, though having each team member's computer able to run them becomes more difficult with time. As the team and the infrastructure grows, so does the number of sensitive input variables (e.g. API Keys, SSL Cert Pairs) required to run a plan.

To avoid the burden and the security risk of each team member arranging all sensitive inputs locally, it's common for teams to migrate to a model in which Terraform operations are executed in a shared Continuous Integration (CI) environment. The work needed to create such a CI environment is nontrivial, and is outside the scope of this core workflow overview, but a full deep dive on this topic can be found in our [Running Terraform in Automation](https://developer.hashicorp.com/terraform/tutorials/automation/automate-terraform?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS) guide.

This longer iteration cycle of committing changes to version control and then waiting for the CI pipeline to execute is often lengthy enough to prohibit using speculative plans as a feedback loop while authoring individual Terraform configuration changes. Speculative plans are still useful before new Terraform changes are applied or even merged to the main development branch, however, as we'll see in a minute.

### [](https://developer.hashicorp.com/terraform/intro/core-workflow#plan-1)Plan

For teams collaborating on infrastructure, Terraform's plan output creates an opportunity for team members to review each other's work. This allows the team to ask questions, evaluate risks, and catch mistakes before any potentially harmful changes are made.

The natural place for these reviews to occur is alongside pull requests within version control--the point at which an individual proposes a merge from their working branch to the shared team branch. If team members review proposed config changes alongside speculative plan output, they can evaluate whether the intent of the change is being achieved by the plan.

The problem becomes producing that speculative plan output for the team to review. Some teams that still run Terraform locally make a practice that pull requests should include an attached copy of speculative plan output generated by the change author. Others arrange for their CI system to post speculative plan output to pull requests automatically.

![Screenshot of Pull Request with manually posted Terraform plan output](https://web-unified-docs-hashicorp.vercel.app/api/assets/terraform/latest/img/docs/manually-pasted-plan-output.png)

In addition to reviewing the plan for the proper expression of its author's intent, the team can also make an evaluation whether they want this change to happen now. For example, if a team notices that a certain change could result in service disruption, they may decide to delay merging its pull request until they can schedule a maintenance window.

### [](https://developer.hashicorp.com/terraform/intro/core-workflow#apply-1)Apply

Once a pull request has been approved and merged, it's important for the team to review the final concrete plan that's run against the shared team branch and the latest version of the state file.

This plan has the potential to be different than the one reviewed on the pull request due to issues like merge order or recent infrastructural changes. For example, if a manual change was made to your infrastructure since the plan was reviewed, the plan might be different when you merge.

It is at this point that the team asks questions about the potential implications of applying the change. Do we expect any service disruption from this change? Is there any part of this change that is high risk? Is there anything in our system that we should be watching as we apply this? Is there anyone we need to notify that this change is happening?

Depending on the change, sometimes team members will want to watch the apply output as it is happening. For teams that are running Terraform locally, this may involve a screen share with the team. For teams running Terraform in CI, this may involve gathering around the build log.

Just like the workflow for individuals, the core workflow for teams is a loop that plays out for each change. For some teams this loop happens a few times a week, for others, many times a day.

## [](https://developer.hashicorp.com/terraform/intro/core-workflow#the-core-workflow-enhanced-by-hcp-terraform)The Core Workflow Enhanced by HCP Terraform

While the above described workflows enable the safe, predictable, and reproducible creating or changing of infrastructure, there are multiple collaboration points that can be streamlined, especially as teams and organizations scale. We designed HCP Terraform to support and enhance the core Terraform workflow for anyone collaborating on infrastructure, from small teams to large organizations. Let's look at how HCP Terraform makes for a better experience at each step.

### [](https://developer.hashicorp.com/terraform/intro/core-workflow#write-2)Write

HCP Terraform provides a centralized and secure location for storing input variables and state while also bringing back a tight feedback loop for speculative plans for config authors. Terraform configuration can interact with HCP Terraform through the [CLI integration](https://developer.hashicorp.com/terraform/cli/cloud).

```
terraform {
  cloud {
    organization = "my-org"
    hostname = "app.terraform.io" # Optional; defaults to app.terraform.io

    workspaces {
      tags = {
        layer = "networking"
        source = "cli"
      }
      
      # For terraform versions below 1.10, you must specify key-only tags
      # using a list of strings. Example:
      # tags = ["networking", "source:cli"]
    }
  }
}
```

After you configure the integration, an HCP Terraform API key is all your team members need to edit config and run speculative plans against the latest version of the state file using all the remotely stored input variables.

```
$ terraform workspace select my-app-dev
Switched to workspace "my-app-dev".

$ terraform plan

Running plan remotely in Terraform Enterprise.

Output will stream here. To view this plan in a browser, visit:

https://app.terraform.io/my-org/my-app-dev/.../

Refreshing Terraform state in-memory prior to plan...

# ...

Plan: 1 to add, 0 to change, 0 to destroy.
```

With the assistance of this plan output, team members can each work on authoring config until it is ready to propose as a change via a pull request.

### [](https://developer.hashicorp.com/terraform/intro/core-workflow#plan-2)Plan

Once a pull request is ready for review, HCP Terraform makes the process of reviewing a speculative plan easier for team members. First, the plan is automatically run when the pull request is created. Status updates to the pull request indicate while the plan is in progress.

Once the plan is complete, the status update indicates whether there were any changes in the speculative plan, right from the pull request view.

![Screenshot of Pull Request with resource changes in the status update](https://web-unified-docs-hashicorp.vercel.app/api/assets/terraform/latest/img/docs/pull-request.png)

For certain types of changes, this information is all that's needed for a team member to be able to approve the pull request. When a teammate needs to do a full review of the plan, clicking the link to HCP Terraform brings up a view that allows them to quickly analyze the full plan details.

![Screenshot of Pull Request run in HCP Terraform](https://web-unified-docs-hashicorp.vercel.app/api/assets/terraform/latest/img/docs/pr-plan.png)

This page allows the reviewer to quickly determine if the plan is matching the config author's intent and evaluate the risk of the change.

### [](https://developer.hashicorp.com/terraform/intro/core-workflow#apply-2)Apply

After merge, HCP Terraform presents the concrete plan to the team for review and approval.

![Screenshot of concrete plan](https://web-unified-docs-hashicorp.vercel.app/api/assets/terraform/latest/img/docs/concrete-plan.png)

The team can discuss any outstanding questions about the plan before the change is made.

![Screenshot of back-and-forth in HCP Terraform comments](https://web-unified-docs-hashicorp.vercel.app/api/assets/terraform/latest/img/docs/plan-comments.png)

Once the Apply is confirmed, HCP Terraform displays the progress live to anyone who'd like to watch.

![Screenshot of in-progress Apply](https://web-unified-docs-hashicorp.vercel.app/api/assets/terraform/latest/img/docs/in-progress-apply.png)

## [](https://developer.hashicorp.com/terraform/intro/core-workflow#conclusion)Conclusion

There are many different ways to use Terraform: as an individual user, a single team, or an entire organization at scale. Choosing the best approach for the density of collaboration needed will provide the most return on your investment in the core Terraform workflow. For organizations using Terraform at scale, HCP Terraform introduces new layers that build on this core workflow to solve problems unique to teams and organizations.

### 6b       Initialize a Terraform working directory (terraform init)

# terraform init command

The `terraform init` command initializes a working directory containing Terraform configuration files. This is the first command you should run after writing a new Terraform configuration or cloning an existing configuration from version control. It is safe to run this command multiple times.

> **Hands-on:** Try the [Terraform: Get Started](https://developer.hashicorp.com/terraform/tutorials/aws-get-started?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS) tutorials. For more in-depth details on the `init` command, check out the [Initialize Terraform Configuration tutorial](https://developer.hashicorp.com/terraform/tutorials/cli/init?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS).

## [](https://developer.hashicorp.com/terraform/cli/commands/init#usage)Usage

Usage: `terraform init [options]`

This command performs several different initialization steps in order to prepare the current working directory for use with Terraform. More details on these are in the sections below, but in most cases it is not necessary to worry about these individual steps.

This command is always safe to run multiple times, to bring the working directory up to date with changes in the configuration. Though subsequent runs may give errors, this command will never delete your existing configuration or state.

## [](https://developer.hashicorp.com/terraform/cli/commands/init#general-options)General Options

The following options apply to all of (or several of) the initialization steps:

- [](https://developer.hashicorp.com/terraform/cli/commands/init#)
    
    [`-input=true`](https://developer.hashicorp.com/terraform/cli/commands/init#input-true) Ask for input if necessary. If false, will error if input was required.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/init#)
    
    [`-lock=false`](https://developer.hashicorp.com/terraform/cli/commands/init#lock-false) Disable locking of state files during state-related operations.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/init#)
    
    [`-lock-timeout=<duration>`](https://developer.hashicorp.com/terraform/cli/commands/init#lock-timeout) Override the time Terraform will wait to acquire a state lock. The default is `0s` (zero seconds), which causes immediate failure if the lock is already held by another process.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/init#)
    
    [`-no-color`](https://developer.hashicorp.com/terraform/cli/commands/init#no-color) Disable color codes in the command output.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/init#)
    
    [`-upgrade`](https://developer.hashicorp.com/terraform/cli/commands/init#upgrade) Opt to upgrade modules and plugins as part of their respective installation steps. See the sections below for more details.
    

## [](https://developer.hashicorp.com/terraform/cli/commands/init#copy-a-source-module)Copy a Source Module

By default, `terraform init` assumes that the working directory already contains a configuration and will attempt to initialize that configuration.

Optionally, init can be run against an empty directory with the `-from-module=MODULE-SOURCE` option, in which case the given module will be copied into the target directory before any other initialization steps are run.

This special mode of operation supports two use-cases:

- Given a version control source, it can serve as a shorthand for checking out a configuration from version control and then initializing the working directory for it.
    
- If the source refers to an _example_ configuration, it can be copied into a local directory to be used as a basis for a new configuration.
    

For routine use it is recommended to check out configuration from version control separately, using the version control system's own commands. This way it is possible to pass extra flags to the version control system when necessary, and to perform other preparation steps (such as configuration generation, or activating credentials) before running `terraform init`.

## [](https://developer.hashicorp.com/terraform/cli/commands/init#backend-initialization)Backend Initialization

During init, the root configuration directory is consulted for [backend configuration](https://developer.hashicorp.com/terraform/language/backend) and the chosen backend is initialized using the given configuration settings.

Re-running init with an already-initialized backend will update the working directory to use the new backend settings. Either `-reconfigure` or `-migrate-state` must be supplied to update the backend configuration.

The `-migrate-state` option will attempt to copy existing state to the new backend, and depending on what changed, may result in interactive prompts to confirm migration of workspace states. The `-force-copy` option suppresses these prompts and answers "yes" to the migration questions. Enabling `-force-copy` also automatically enables the `-migrate-state` option.

The `-reconfigure` option disregards any existing configuration, preventing migration of any existing state.

To skip backend configuration, use `-backend=false`. Note that some other init steps require an initialized backend, so it is recommended to use this flag only when the working directory was already previously initialized for a particular backend.

The `-backend-config=...` option can be used for [partial backend configuration](https://developer.hashicorp.com/terraform/language/backend#partial-configuration), in situations where the backend settings are dynamic or sensitive and so cannot be statically specified in the configuration file.

## [](https://developer.hashicorp.com/terraform/cli/commands/init#child-module-installation)Child Module Installation

During init, the configuration is searched for `module` blocks, and the source code for referenced [modules](https://developer.hashicorp.com/terraform/language/modules/develop) is retrieved from the locations given in their `source` arguments.

Re-running init with modules already installed will install the sources for any modules that were added to configuration since the last init, but will not change any already-installed modules. Use `-upgrade` to override this behavior, updating all modules to the latest available source code.

To skip child module installation, use `-get=false`. Note that some other init steps can complete only when the module tree is complete, so it's recommended to use this flag only when the working directory was already previously initialized with its child modules.

## [](https://developer.hashicorp.com/terraform/cli/commands/init#plugin-installation)Plugin Installation

Most Terraform providers are published separately from Terraform as plugins. During init, Terraform searches the configuration for both direct and indirect references to providers and attempts to install the plugins for those providers.

For providers that are published in either [the public Terraform Registry](https://registry.terraform.io/) or in a third-party provider registry, `terraform init` will automatically find, download, and install the necessary provider plugins. If you cannot or do not wish to install providers from their origin registries, you can customize how Terraform installs providers using [the provider installation settings in the CLI configuration](https://developer.hashicorp.com/terraform/cli/config/config-file#provider-installation).

For more information about specifying which providers are required for each of your modules, see [Provider Requirements](https://developer.hashicorp.com/terraform/language/providers/requirements).

After successful installation, Terraform writes information about the selected providers to [the dependency lock file](https://developer.hashicorp.com/terraform/language/files/dependency-lock). You should commit this file to your version control system to ensure that when you run `terraform init` again in future Terraform will select exactly the same provider versions. Use the `-upgrade` option if you want Terraform to ignore the dependency lock file and consider installing newer versions.

You can modify `terraform init`'s plugin behavior with the following options:

- [](https://developer.hashicorp.com/terraform/cli/commands/init#)
    
    [`-upgrade`](https://developer.hashicorp.com/terraform/cli/commands/init#upgrade-1) Upgrade all previously-selected plugins to the newest version that complies with the configuration's version constraints. This will cause Terraform to ignore any selections recorded in the dependency lock file, and to take the newest available version matching the configured version constraints.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/init#)
    
    [`-get-plugins=false`](https://developer.hashicorp.com/terraform/cli/commands/init#get-plugins-false) — Skip plugin installation.
    
    Note: Since Terraform 0.13, this option has been superseded by the [`provider_installation`](https://developer.hashicorp.com/terraform/cli/config/config-file#provider-installation) and [`plugin_cache_dir`](https://developer.hashicorp.com/terraform/cli/config/config-file#plugin_cache_dir) settings. It should not be used in Terraform versions 0.13+, and this option was removed in Terraform 0.15.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/init#)
    
    [`-plugin-dir=PATH`](https://developer.hashicorp.com/terraform/cli/commands/init#plugin-dir-path) — Force plugin installation to read plugins _only_ from the specified directory, as if it had been configured as a `filesystem_mirror` in the CLI configuration. If you intend to routinely use a particular filesystem mirror then we recommend [configuring Terraform's installation methods globally](https://developer.hashicorp.com/terraform/cli/config/config-file#provider-installation). You can use `-plugin-dir` as a one-time override for exceptional situations, such as if you are testing a local build of a provider plugin you are currently developing.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/init#)
    
    [`-lockfile=MODE`](https://developer.hashicorp.com/terraform/cli/commands/init#lockfile-mode) Set a dependency lockfile mode.
    

The valid values for the lockfile mode are as follows:

- [](https://developer.hashicorp.com/terraform/cli/commands/init#)[`readonly`](https://developer.hashicorp.com/terraform/cli/commands/init#readonly): suppress the lockfile changes, but verify checksums against the information already recorded. It conflicts with the `-upgrade` flag. If you update the lockfile with third-party dependency management tools, it would be useful to control when it changes explicitly.

## [](https://developer.hashicorp.com/terraform/cli/commands/init#running-terraform-init-in-automation)Running `terraform init` in automation

For teams that use Terraform as a key part of a change management and deployment pipeline, it can be desirable to orchestrate Terraform runs in some sort of automation in order to ensure consistency between runs, and provide other interesting features such as integration with version control hooks.

There are some special concerns when running `init` in such an environment, including optionally making plugins available locally to avoid repeated re-installation. For more information, see the [Running Terraform in Automation](https://developer.hashicorp.com/terraform/tutorials/automation/automate-terraform?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS) tutorial.

## [](https://developer.hashicorp.com/terraform/cli/commands/init#passing-a-different-configuration-directory)Passing a Different Configuration Directory

Terraform v0.13 and earlier also accepted a directory path in place of the plan file argument to `terraform apply`, in which case Terraform would use that directory as the root module instead of the current working directory.

That usage is still supported in Terraform v0.14, but is now deprecated and removed in Terraform v0.15. If your workflow relies on overriding the root module directory, use [the `-chdir` global option](https://developer.hashicorp.com/terraform/cli/commands#switching-working-directory-with-chdir) instead, which works across all commands and makes Terraform consistently look in the given directory for all files it would normally read or write in the current working directory.

If your previous use of this legacy pattern was also relying on Terraform writing the `.terraform` subdirectory into the current working directory even though the root module directory was overridden, use [the `TF_DATA_DIR` environment variable](https://developer.hashicorp.com/terraform/cli/config/environment-variables#tf_data_dir) to direct Terraform to write the `.terraform` directory to a location other than the current working directory.

### 6c       Validate a Terraform configuration (terraform validate)

# Terraform validate command

The `terraform validate` command validates the configuration files in a directory. It does not validate remote services, such as remote state or provider APIs.

## [](https://developer.hashicorp.com/terraform/cli/commands/validate#introduction)Introduction

Validate runs checks that verify whether a configuration is syntactically valid and internally consistent, regardless of any provided variables or existing state. It is thus primarily useful for general verification of reusable modules, including correctness of attribute names and value types.

It is safe to run this command automatically, for example as a post-save check in a text editor or as a test step for a reusable module in a CI system.

Validation requires an initialized working directory with any referenced plugins and modules installed. To initialize a working directory for validation without accessing any configured backend, use:

```
$ terraform init -backend=false
```

To verify the configuration in the context of a particular run (a particular target workspace, input variable values, etc), use the `terraform plan` command instead, which includes an implied validation check.

## [](https://developer.hashicorp.com/terraform/cli/commands/validate#usage)Usage

Usage: `terraform validate [options]`

This command accepts the following options:

- [](https://developer.hashicorp.com/terraform/cli/commands/validate#)
    
    [`-json`](https://developer.hashicorp.com/terraform/cli/commands/validate#json) - Produce output in a machine-readable JSON format, suitable for use in text editor integrations and other automated systems. Always disables color.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/validate#)
    
    [`-no-color`](https://developer.hashicorp.com/terraform/cli/commands/validate#no-color) - If specified, output won't contain any color.
    

## [](https://developer.hashicorp.com/terraform/cli/commands/validate#json-output-format)JSON Output Format

When you use the `-json` option, Terraform will produce validation results in JSON format to allow using the validation result for tool integrations, such as highlighting errors in a text editor.

As with all JSON output options, it's possible that Terraform will encounter an error prior to beginning the validation task that will thus not be subject to the JSON output setting. For that reason, external software consuming Terraform's output should be prepared to find data on stdout that _isn't_ valid JSON, which it should then treat as a generic error case.

The output includes a `format_version` key, which as of Terraform 1.1.0 has value `"1.0"`. The semantics of this version are:

- We will increment the minor version, e.g. `"1.1"`, for backward-compatible changes or additions. Ignore any object properties with unrecognized names to remain forward-compatible with future minor versions.
- We will increment the major version, e.g. `"2.0"`, for changes that are not backward-compatible. Reject any input which reports an unsupported major version.

We will introduce new major versions only within the bounds of [the Terraform 1.0 Compatibility Promises](https://developer.hashicorp.com/terraform/language/v1-compatibility-promises).

In the normal case, Terraform will print a JSON object to the standard output stream. The top-level JSON object will have the following properties:

- [](https://developer.hashicorp.com/terraform/cli/commands/validate#)
    
    [`valid`](https://developer.hashicorp.com/terraform/cli/commands/validate#valid) (boolean): Summarizes the overall validation result, by indicating `true` if Terraform considers the current configuration to be valid or `false` if it detected any errors.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/validate#)
    
    [`error_count`](https://developer.hashicorp.com/terraform/cli/commands/validate#error_count) (number): A zero or positive whole number giving the count of errors Terraform detected. If `valid` is `true` then `error_count` will always be zero, because it is the presence of errors that indicates that a configuration is invalid.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/validate#)
    
    [`warning_count`](https://developer.hashicorp.com/terraform/cli/commands/validate#warning_count) (number): A zero or positive whole number giving the count of warnings Terraform detected. Warnings do not cause Terraform to consider a configuration to be invalid, but they do indicate potential caveats that a user should consider and possibly resolve.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/validate#)
    
    [`diagnostics`](https://developer.hashicorp.com/terraform/cli/commands/validate#diagnostics) (array of objects): A JSON array of nested objects that each describe an error or warning from Terraform.
    

The nested objects in `diagnostics` have the following properties:

- [](https://developer.hashicorp.com/terraform/cli/commands/validate#)
    
    [`severity`](https://developer.hashicorp.com/terraform/cli/commands/validate#severity) (string): A string keyword, either `"error"` or `"warning"`, indicating the diagnostic severity.
    
    The presence of errors causes Terraform to consider a configuration to be invalid, while warnings are just advice or caveats to the user which do not block working with the configuration. Later versions of Terraform may introduce new severity keywords, so consumers should be prepared to accept and ignore severity values they don't understand.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/validate#)
    
    [`summary`](https://developer.hashicorp.com/terraform/cli/commands/validate#summary) (string): A short description of the nature of the problem that the diagnostic is reporting.
    
    In Terraform's usual human-oriented diagnostic messages, the summary serves as a sort of "heading" for the diagnostic, printed after the "Error:" or "Warning:" indicator.
    
    Summaries are typically short, single sentences, but can sometimes be longer as a result of returning errors from subsystems that are not designed to return full diagnostics, where the entire error message becomes the summary. In those cases, the summary might include newline characters which a renderer should honor when presenting the message visually to a user.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/validate#)
    
    [`detail`](https://developer.hashicorp.com/terraform/cli/commands/validate#detail) (string): An optional additional message giving more detail about the problem.
    
    In Terraform's usual human-oriented diagnostic messages, the detail provides the paragraphs of text that appear after the heading and the source location reference.
    
    Detail messages are often multiple paragraphs and possibly interspersed with non-paragraph lines, so tools that aim to present detailed messages to the user should distinguish between lines without leading spaces, treating them as paragraphs, and lines with leading spaces, treating them as preformatted text. Renderers should then soft-wrap the paragraphs to fit the width of the rendering container, but leave the preformatted lines unwrapped.
    
    Some Terraform detail messages contain an approximation of bullet lists using ASCII characters to mark the bullets. This is not a contractual formatting convention, so renderers should avoid depending on it and should instead treat those lines as either paragraphs or preformatted text.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/validate#)
    
    [`range`](https://developer.hashicorp.com/terraform/cli/commands/validate#range) (object): An optional object referencing a portion of the configuration source code that the diagnostic message relates to. For errors, this will typically indicate the bounds of the specific block header, attribute, or expression which was detected as invalid.
    
    A source range is an object with a property `filename` that gives the filename as a relative path from the current working directory, and then two properties `start` and `end` which are both themselves objects describing source positions, as described below.
    
    Not all diagnostic messages are connected with specific portions of the configuration, so `range` will be omitted or `null` for diagnostic messages where it isn't relevant.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/validate#)
    
    [`snippet`](https://developer.hashicorp.com/terraform/cli/commands/validate#snippet) (object): An optional object including an excerpt of the configuration source code that the diagnostic message relates to.
    
    The snippet information includes:
    
    - [](https://developer.hashicorp.com/terraform/cli/commands/validate#)
        
        [`context`](https://developer.hashicorp.com/terraform/cli/commands/validate#context) (string): An optional summary of the root context of the diagnostic. For example, this might be the resource block containing the expression that triggered the diagnostic. For some diagnostics, this information is not available, and then this property will be `null`.
        
    - [](https://developer.hashicorp.com/terraform/cli/commands/validate#)
        
        [`code`](https://developer.hashicorp.com/terraform/cli/commands/validate#code) (string): A snippet of Terraform configuration including the source of the diagnostic. This can be multiple lines and may include additional configuration source code around the expression which triggered the diagnostic.
        
    - [](https://developer.hashicorp.com/terraform/cli/commands/validate#)
        
        [`start_line`](https://developer.hashicorp.com/terraform/cli/commands/validate#start_line) (number): A one-based line count representing the position in the source file at which the `code` excerpt begins. This is not necessarily the same value as `range.start.line`, as it is possible for `code` to include one or more lines of context before the source of the diagnostic.
        
    - [](https://developer.hashicorp.com/terraform/cli/commands/validate#)
        
        [`highlight_start_offset`](https://developer.hashicorp.com/terraform/cli/commands/validate#highlight_start_offset) (number): A zero-based character offset into the `code` string, pointing at the start of the expression which triggered the diagnostic.
        
    - [](https://developer.hashicorp.com/terraform/cli/commands/validate#)
        
        [`highlight_end_offset`](https://developer.hashicorp.com/terraform/cli/commands/validate#highlight_end_offset) (number): A zero-based character offset into the `code` string, pointing at the end of the expression which triggered the diagnostic.
        
    - [](https://developer.hashicorp.com/terraform/cli/commands/validate#)
        
        [`values`](https://developer.hashicorp.com/terraform/cli/commands/validate#values) (array of objects): Contains zero or more expression values which may be useful in understanding the source of a diagnostic in a complex expression. These expression value objects are described below.
        

### [](https://developer.hashicorp.com/terraform/cli/commands/validate#source-position)Source Position

A source position object, as used in the `range` property of a diagnostic object, has the following properties:

- [](https://developer.hashicorp.com/terraform/cli/commands/validate#)
    
    [`byte`](https://developer.hashicorp.com/terraform/cli/commands/validate#byte) (number): A zero-based byte offset into the indicated file.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/validate#)
    
    [`line`](https://developer.hashicorp.com/terraform/cli/commands/validate#line) (number): A one-based line count for the line containing the relevant position in the indicated file.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/validate#)
    
    [`column`](https://developer.hashicorp.com/terraform/cli/commands/validate#column) (number): A one-based count of _Unicode characters_ from the start of the line indicated in `line`.
    

A `start` position is inclusive while an `end` position is exclusive. The exact positions used for particular error messages are intended for human interpretation only.

### [](https://developer.hashicorp.com/terraform/cli/commands/validate#expression-value)Expression Value

An expression value object gives additional information about a value that is part of the expression which triggered the diagnostic. This is especially useful when using `for_each` or similar constructs, in order to identify exactly which values are responsible for an error. The object has two properties:

- [](https://developer.hashicorp.com/terraform/cli/commands/validate#)
    
    [`traversal`](https://developer.hashicorp.com/terraform/cli/commands/validate#traversal) (string): An HCL-like traversal string, such as `var.instance_count`. Complex index key values may be elided, so this will not always be valid, parseable HCL. The contents of this string are intended to be human-readable.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/validate#)
    
    [`statement`](https://developer.hashicorp.com/terraform/cli/commands/validate#statement) (string): A short English-language fragment describing the value of the expression when the diagnostic was triggered. The contents of this string are intended to be human-readable and are subject to change in future versions of Terraform.

### 6d       Generate and review an execution plan for Terraform (terraform plan)

# terraform plan command

The `terraform plan` command creates an execution plan, which lets you preview the changes that Terraform plans to make to your infrastructure.

## [](https://developer.hashicorp.com/terraform/cli/commands/plan#introduction)Introduction

By default, Terraform performs the following operations when it creates a plan:

- Reads the current state of any already-existing remote objects to make sure that the Terraform state is up-to-date.
- Compares the current configuration to the prior state and noting any differences.
- Proposes a set of change actions that should, if applied, make the remote objects match the configuration.

> **Hands-on:** Try the [Terraform: Get Started](https://developer.hashicorp.com/terraform/tutorials/aws-get-started?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS) tutorials. For more in-depth details on the `plan` command, check out the [Create a Terraform Plan tutorial](https://developer.hashicorp.com/terraform/tutorials/cli/plan?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS).

The `plan` command alone does not actually carry out the proposed changes You can use this command to check whether the proposed changes match what you expected before you apply the changes or share your changes with your team for broader review.

If Terraform detects that no changes are needed to resource instances or to root module output values, `terraform plan` will report that no actions need to be taken.

If you are using Terraform directly in an interactive terminal and you expect to apply the changes Terraform proposes, you can alternatively run [`terraform apply`](https://developer.hashicorp.com/terraform/cli/commands/apply) directly. By default, the "apply" command automatically generates a new plan and prompts for you to approve it.

You can use the optional `-out=FILE` option to save the generated plan to a file on disk, which you can later execute by passing the file to [`terraform apply`](https://developer.hashicorp.com/terraform/cli/commands/apply) as an extra argument. This two-step workflow is primarily intended for when [running Terraform in automation](https://developer.hashicorp.com/terraform/tutorials/automation/automate-terraform?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS).

If you run `terraform plan` without the `-out=FILE` option then it will create a _speculative plan_, which is a description of the effect of the plan but without any intent to actually apply it.

In teams that use a version control and code review workflow for making changes to real infrastructure, developers can use speculative plans to verify the effect of their changes before submitting them for code review. However, it's important to consider that other changes made to the target system in the meantime might cause the final effect of a configuration change to be different than what an earlier speculative plan indicated, so you should always re-check the final non-speculative plan before applying to make sure that it still matches your intent.

## [](https://developer.hashicorp.com/terraform/cli/commands/plan#usage)Usage

Usage: `terraform plan [options]`

The `plan` subcommand looks in the current working directory for the root module configuration.

Because the plan command is one of the main commands of Terraform, it has a variety of different options, described in the following sections. However, most of the time you should not need to set any of these options, because a Terraform configuration should typically be designed to work with no special additional options for routine work.

The remaining sections on this page describe the various options:

- **[Planning Modes](https://developer.hashicorp.com/terraform/cli/commands/plan#planning-modes)**: There are some special alternative planning modes that you can use for some special situations where your goal is not just to change the remote system to match your configuration.
- **[Planning Options](https://developer.hashicorp.com/terraform/cli/commands/plan#planning-options)**: Alongside the special planning modes, there are also some options you can set in order to customize the planning process for unusual needs.
    - **[Resource Targeting](https://developer.hashicorp.com/terraform/cli/commands/plan#resource-targeting)** is one particular special planning option that has some important caveats associated with it.
- **[Other Options](https://developer.hashicorp.com/terraform/cli/commands/plan#other-options)**: These change the behavior of the planning command itself, rather than customizing the content of the generated plan.

## [](https://developer.hashicorp.com/terraform/cli/commands/plan#planning-modes)Planning Modes

The previous section describes Terraform's default planning behavior, which changes the remote system to match the changes you make to your configuration. Terraform has two alternative planning modes, each of which creates a plan with a different intended outcome. These options are available for both `terraform plan` and [`terraform apply`](https://developer.hashicorp.com/terraform/cli/commands/apply).

- **Destroy mode:** creates a plan whose goal is to destroy all remote objects that currently exist, leaving an empty Terraform state. It is the same as running [`terraform destroy`](https://developer.hashicorp.com/terraform/cli/commands/destroy). Destroy mode can be useful for situations like transient development environments, where the managed objects cease to be useful once the development task is complete.
    
    Activate destroy mode using the `-destroy` command line option.
    
- **Refresh-only mode:** creates a plan whose goal is only to update the Terraform state and any root module output values to match changes made to remote objects outside of Terraform. This can be useful if you've intentionally changed one or more remote objects outside of the usual workflow (e.g. while responding to an incident) and you now need to reconcile Terraform's records with those changes.
    
    Activate refresh-only mode using the `-refresh-only` command line option.
    

In situations where we need to discuss the default planning mode that Terraform uses when none of the alternative modes are selected, we refer to it as "Normal mode". Because these alternative modes are for specialized situations only, some other Terraform documentation only discusses the normal planning mode.

The planning modes are all mutually-exclusive, so activating any non-default planning mode disables the "normal" planning mode, and you can't use more than one alternative mode at the same time.

**Note:** In Terraform v0.15 and earlier, the `-destroy` option is supported only by the `terraform plan` command, and not by the `terraform apply` command. To create and apply a plan in destroy mode in earlier versions you must run [`terraform destroy`](https://developer.hashicorp.com/terraform/cli/commands/destroy).

**Note:** The `-refresh-only` option is available only in Terraform v0.15.4 and later.

> **Hands-on:** Try the [Use Refresh-Only Mode to Sync Terraform State](https://developer.hashicorp.com/terraform/tutorials/state/refresh) tutorial.

## [](https://developer.hashicorp.com/terraform/cli/commands/plan#planning-options)Planning Options

In addition to alternate [planning modes](https://developer.hashicorp.com/terraform/cli/commands/plan#planning-modes), there are several options that can modify planning behavior. These options are available for both `terraform plan` and [`terraform apply`](https://developer.hashicorp.com/terraform/cli/commands/apply).

- [](https://developer.hashicorp.com/terraform/cli/commands/plan#)
    
    [`-refresh=false`](https://developer.hashicorp.com/terraform/cli/commands/plan#refresh-false) - Disables the default behavior of synchronizing the Terraform state with remote objects before checking for configuration changes. This can make the planning operation faster by reducing the number of remote API requests. However, setting `refresh=false` causes Terraform to ignore external changes, which could result in an incomplete or incorrect plan. You cannot use `refresh=false` in refresh-only planning mode because it would effectively disable the entirety of the planning operation.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/plan#)
    
    [`-replace=ADDRESS`](https://developer.hashicorp.com/terraform/cli/commands/plan#replace-address) - Instructs Terraform to plan to replace the resource instance with the given address. This is helpful when one or more remote objects have become degraded, and you can use replacement objects with the same configuration to align with immutable infrastructure patterns. Terraform will use a "replace" action if the specified resource would normally cause an "update" action or no action at all. Include this option multiple times to replace several objects at once. You cannot use `-replace` with the `-destroy` option, and it is only available from Terraform v0.15.2 onwards. For earlier versions, use [`terraform taint`](https://developer.hashicorp.com/terraform/cli/commands/taint) to achieve a similar result.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/plan#)
    
    [`-target=ADDRESS`](https://developer.hashicorp.com/terraform/cli/commands/plan#target-address) - Instructs Terraform to focus its planning efforts only on resource instances which match the given address and on any objects that those instances depend on.
    
    **Note:** Use `-target=ADDRESS` in exceptional circumstances only, such as recovering from mistakes or working around Terraform limitations. Refer to [Resource Targeting](https://developer.hashicorp.com/terraform/cli/commands/plan#resource-targeting) for more details.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/plan#)
    
    [`-var 'NAME=VALUE'`](https://developer.hashicorp.com/terraform/cli/commands/plan#var-name-value) - Sets a value for a single [input variable](https://developer.hashicorp.com/terraform/language/values/variables) declared in the root module of the configuration. Use this option multiple times to set more than one variable. Refer to [Input Variables on the Command Line](https://developer.hashicorp.com/terraform/cli/commands/plan#input-variables-on-the-command-line) for more information.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/plan#)
    
    [`-var-file=FILENAME`](https://developer.hashicorp.com/terraform/cli/commands/plan#var-file-filename) - Sets values for potentially many [input variables](https://developer.hashicorp.com/terraform/language/values/variables) declared in the root module of the configuration, using definitions from a ["tfvars" file](https://developer.hashicorp.com/terraform/language/values/variables#variable-definitions-tfvars-files). Use this option multiple times to include values from more than one file.
    

There are several other ways to set values for input variables in the root module, aside from the `-var` and `-var-file` options. Refer to [Assigning Values to Root Module Variables](https://developer.hashicorp.com/terraform/language/values/variables#assigning-values-to-root-module-variables) for more information.

### [](https://developer.hashicorp.com/terraform/cli/commands/plan#input-variables-on-the-command-line)Input Variables on the Command Line

You can use the `-var` command line option to specify values for [input variables](https://developer.hashicorp.com/terraform/language/values/variables) declared in your root module.

However, to do so will require writing a command line that is parsable both by your chosen command line shell _and_ Terraform, which can be complicated for expressions involving lots of quotes and escape sequences. In most cases we recommend using the `-var-file` option instead, and write your actual values in a separate file so that Terraform can parse them directly, rather than interpreting the result of your shell's parsing.

**Warning:** Terraform will error if you include a space before or after the equals sign (e.g., `-var "length = 2"`).

To use `-var` on a Unix-style shell on a system like Linux or macOS we recommend writing the option argument in single quotes `'` to ensure the shell will interpret the value literally:

```
terraform plan -var 'name=value'
```

If your intended value also includes a single quote then you'll still need to escape that for correct interpretation by your shell, which also requires temporarily ending the quoted sequence so that the backslash escape character will be significant:

```
terraform plan -var 'name=va'\''lue'
```

When using Terraform on Windows, we recommend using the Windows Command Prompt (`cmd.exe`). When you pass a variable value to Terraform from the Windows Command Prompt, use double quotes `"` around the argument:

```
terraform plan -var "name=value"
```

If your intended value includes literal double quotes then you'll need to escape those with a backslash:

```
terraform plan -var "name=va\"lue"
```

PowerShell on Windows cannot correctly pass literal quotes to external programs, so we do not recommend using Terraform with PowerShell when you are on Windows. Use Windows Command Prompt instead.

The appropriate syntax for writing the variable value is different depending on the variable's [type constraint](https://developer.hashicorp.com/terraform/language/expressions/type-constraints). The primitive types `string`, `number`, and `bool` all expect a direct string value with no special punctuation except that required by your shell, as shown in the above examples. For all other type constraints, including list, map, and set types and the special `any` keyword, you must write a valid Terraform language expression representing the value, and write any necessary quoting or escape characters to ensure it will pass through your shell literally to Terraform. For example, for a `list(string)` type constraint:

```
# Unix-style shell
terraform plan -var 'name=["a", "b", "c"]'
 
# Windows Command Prompt (do not use PowerShell on Windows)
terraform plan -var "name=[\"a\", \"b\", \"c\"]"
```

Similar constraints apply when setting input variables using environment variables. For more information on the various methods for setting root module input variables, see [Assigning Values to Root Module Variables](https://developer.hashicorp.com/terraform/language/values/variables#assigning-values-to-root-module-variables).

### [](https://developer.hashicorp.com/terraform/cli/commands/plan#resource-targeting)Resource Targeting

> **Hands-on:** Try the [Target resources](https://developer.hashicorp.com/terraform/tutorials/state/resource-targeting?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS) tutorial.

You can use the `-target` option to focus Terraform's attention on only a subset of resources. You can use [resource address syntax](https://developer.hashicorp.com/terraform/cli/state/resource-addressing) to specify the constraint. Terraform interprets the resource address as follows:

- If the given address identifies one specific resource instance, Terraform will select that instance alone. For resources with either `count` or `for_each` set, a resource instance address must include the instance index part, like `aws_instance.example[0]`.
    
- If the given address identifies a resource as a whole, Terraform will select all of the instances of that resource. For resources with either `count` or `for_each` set, this means selecting _all_ instance indexes currently associated with that resource. For single-instance resources (without either `count` or `for_each`), the resource address and the resource instance address are identical, so this possibility does not apply.
    
- If the given address identifies an entire module instance, Terraform will select all instances of all resources that belong to that module instance and all of its child module instances.
    

Once Terraform has selected one or more resource instances that you've directly targeted, it will also then extend the selection to include all other objects that those selections depend on either directly or indirectly.

This targeting capability is provided for exceptional circumstances, such as recovering from mistakes or working around Terraform limitations. It is _not recommended_ to use `-target` for routine operations, since this can lead to undetected configuration drift and confusion about how the true state of resources relates to configuration.

Instead of using `-target` as a means to operate on isolated portions of very large configurations, prefer instead to break large configurations into several smaller configurations that can each be independently applied. [Data sources](https://developer.hashicorp.com/terraform/language/data-sources) can be used to access information about resources created in other configurations, allowing a complex system architecture to be broken down into more manageable parts that can be updated independently.

## [](https://developer.hashicorp.com/terraform/cli/commands/plan#other-options)Other Options

The `terraform plan` command also has some other options that are related to the input and output of the planning command, rather than customizing what sort of plan Terraform will create. These commands are not necessarily also available on `terraform apply`, unless otherwise stated in the documentation for that command.

The available options are:

- [](https://developer.hashicorp.com/terraform/cli/commands/plan#)
    
    [`-compact-warnings`](https://developer.hashicorp.com/terraform/cli/commands/plan#compact-warnings) - Shows any warning messages in a compact form which includes only the summary messages, unless the warnings are accompanied by at least one error and thus the warning text might be useful context for the errors.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/plan#)
    
    [`-detailed-exitcode`](https://developer.hashicorp.com/terraform/cli/commands/plan#detailed-exitcode) - Returns a detailed exit code when the command exits. When provided, this argument changes the exit codes and their meanings to provide more granular information about what the resulting plan contains:
    
    - 0 = Succeeded with empty diff (no changes)
    - 1 = Error
    - 2 = Succeeded with non-empty diff (changes present)

- [](https://developer.hashicorp.com/terraform/cli/commands/plan#)[`-generate-config-out=PATH`](https://developer.hashicorp.com/terraform/cli/commands/plan#generate-config-out-path) - (Experimental) If `import` blocks are present in configuration, instructs Terraform to generate HCL for any imported resources not already present. The configuration is written to a new file at PATH, which must not already exist, or Terraform will error. If the plan fails for another reason, Terraform may still attempt to write configuration.

- [](https://developer.hashicorp.com/terraform/cli/commands/plan#)
    
    [`-input=false`](https://developer.hashicorp.com/terraform/cli/commands/plan#input-false) - Disables Terraform's default behavior of prompting for input for root module input variables that have not otherwise been assigned a value. This option is particularly useful when running Terraform in non-interactive automation systems.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/plan#)
    
    [`-json`](https://developer.hashicorp.com/terraform/cli/commands/plan#json) - Enables the [machine readable JSON UI](https://developer.hashicorp.com/terraform/internals/machine-readable-ui) output. This implies `-input=false`, so the configuration must have no unassigned variable values to continue.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/plan#)
    
    [`-lock=false`](https://developer.hashicorp.com/terraform/cli/commands/plan#lock-false) - Don't hold a state lock during the operation. This is dangerous if others might concurrently run commands against the same workspace.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/plan#)
    
    [`-lock-timeout=DURATION`](https://developer.hashicorp.com/terraform/cli/commands/plan#lock-timeout-duration) - Unless locking is disabled with `-lock=false`, instructs Terraform to retry acquiring a lock for a period of time before returning an error. The duration syntax is a number followed by a time unit letter, such as "3s" for three seconds.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/plan#)
    
    [`-no-color`](https://developer.hashicorp.com/terraform/cli/commands/plan#no-color) - Disables terminal formatting sequences in the output. Use this if you are running Terraform in a context where its output will be rendered by a system that cannot interpret terminal formatting.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/plan#)
    
    [`-out=FILENAME`](https://developer.hashicorp.com/terraform/cli/commands/plan#out-filename) - Writes the generated plan to the given filename in an opaque file format that you can later pass to `terraform apply` to execute the planned changes, and to some other Terraform commands that can work with saved plan files.
    
    Terraform will allow any filename for the plan file, but a typical convention is to name it `tfplan`. **Do not** name the file with a suffix that Terraform recognizes as another file format; if you use a `.tf` suffix then Terraform will try to interpret the file as a configuration source file, which will then cause syntax errors for subsequent commands.
    
    The generated file is not in any standard format intended for consumption by other software, but the file _does_ contain your full configuration, all of the values associated with planned changes, and all of the plan options including the input variables. If your plan includes any sort of sensitive data, even if obscured in Terraform's terminal output, it will be saved in cleartext in the plan file. You should therefore treat any saved plan files as potentially-sensitive artifacts.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/plan#)
    
    [`-parallelism=n`](https://developer.hashicorp.com/terraform/cli/commands/plan#parallelism-n) - Limit the number of concurrent operations as Terraform [walks the graph](https://developer.hashicorp.com/terraform/internals/graph#walking-the-graph). Defaults to 10.
    

For configurations using [the `local` backend](https://developer.hashicorp.com/terraform/language/backend/local) only, `terraform plan` accepts the legacy command line option [`-state`](https://developer.hashicorp.com/terraform/language/backend/local#command-line-arguments).

### [](https://developer.hashicorp.com/terraform/cli/commands/plan#passing-a-different-configuration-directory)Passing a Different Configuration Directory

Terraform v0.13 and earlier accepted an additional positional argument giving a directory path, in which case Terraform would use that directory as the root module instead of the current working directory.

That usage was deprecated in Terraform v0.14 and removed in Terraform v0.15. If your workflow relies on overriding the root module directory, use [the `-chdir` global option](https://developer.hashicorp.com/terraform/cli/commands#switching-working-directory-with-chdir) instead, which works across all commands and makes Terraform consistently look in the given directory for all files it would normally read or write in the current working directory.

If your previous use of this legacy pattern was also relying on Terraform writing the `.terraform` subdirectory into the current working directory even though the root module directory was overridden, use [the `TF_DATA_DIR` environment variable](https://developer.hashicorp.com/terraform/cli/config/environment-variables#tf_data_dir) to direct Terraform to write the `.terraform` directory to a location other than the current working directory.

### 6e       Execute changes to infrastructure with Terraform (terraform apply)

# terraform apply command

The `terraform apply` command executes the actions proposed in a Terraform plan.

> **Hands On:** Try the [Apply Terraform Configuration](https://developer.hashicorp.com/terraform/tutorials/cli/apply?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS) tutorial to learn how Terraform applies a configuration, how Terraform recovers from errors during apply, and common ways to use this command.

## [](https://developer.hashicorp.com/terraform/cli/commands/apply#usage)Usage

Usage: `terraform apply [options] [plan file]`

### [](https://developer.hashicorp.com/terraform/cli/commands/apply#automatic-plan-mode)Automatic Plan Mode

When you run `terraform apply` without passing a saved plan file, Terraform automatically creates a new execution plan as if you had run [`terraform plan`](https://developer.hashicorp.com/terraform/cli/commands/plan), prompts you to approve that plan, and takes the indicated actions. You can use all of the [planning modes](https://developer.hashicorp.com/terraform/cli/commands/plan#planning-modes) and [planning options](https://developer.hashicorp.com/terraform/cli/commands/plan#planning-options) to customize how Terraform will create the plan.

You can pass the `-auto-approve` option to instruct Terraform to apply the plan without asking for confirmation.

**Warning:** If you use `-auto-approve`, we recommend making sure that no one can change your infrastructure outside of your Terraform workflow. This minimizes the risk of unpredictable changes and configuration drift.

### [](https://developer.hashicorp.com/terraform/cli/commands/apply#saved-plan-mode)Saved Plan Mode

When you pass a [saved plan file](https://developer.hashicorp.com/terraform/cli/commands/plan#out-filename) to `terraform apply`, Terraform takes the actions in the saved plan without prompting you for confirmation. You may want to use this two-step workflow when [running Terraform in automation](https://developer.hashicorp.com/terraform/tutorials/automation/automate-terraform?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS).

Use [`terraform show`](https://developer.hashicorp.com/terraform/cli/commands/show) to inspect a saved plan file before applying it.

When using a saved plan, you cannot specify any additional planning modes or options. These options only affect Terraform's decisions about which actions to take, and the plan file contains the final results of those decisions.

### [](https://developer.hashicorp.com/terraform/cli/commands/apply#plan-options)Plan Options

Without a saved plan file, `terraform apply` supports all planning modes and planning options available for `terraform plan`.

- **[Planning Modes](https://developer.hashicorp.com/terraform/cli/commands/plan#planning-modes):** These include `-destroy`, which creates a plan to destroy all remote objects, and `-refresh-only`, which creates a plan to update Terraform state and root module output values.
- **[Planning Options](https://developer.hashicorp.com/terraform/cli/commands/plan#planning-options):** These include specifying which resource instances Terraform should replace (`-replace`), setting Terraform input variables (`-var` and `-var-file`), etc.

### [](https://developer.hashicorp.com/terraform/cli/commands/apply#apply-options)Apply Options

The following options change how the apply command executes and reports on the apply operation.

- [](https://developer.hashicorp.com/terraform/cli/commands/apply#)
    
    [`-auto-approve`](https://developer.hashicorp.com/terraform/cli/commands/apply#auto-approve) - Skips interactive approval of the plan before applying. Terraform ignores this option when you pass a previously-saved plan file. This is because Terraform interprets the act of passing the plan file as the approval.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/apply#)
    
    [`-compact-warnings`](https://developer.hashicorp.com/terraform/cli/commands/apply#compact-warnings) - Shows any warning messages in a compact form which includes only the summary messages, unless the warnings are accompanied by at least one error and thus the warning text might be useful context for the errors.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/apply#)
    
    [`-input=false`](https://developer.hashicorp.com/terraform/cli/commands/apply#input-false) - Disables all of Terraform's interactive prompts. Note that this also prevents Terraform from prompting for interactive approval of a plan, so Terraform will conservatively assume that you do not wish to apply the plan, causing the operation to fail. If you wish to run Terraform in a non-interactive context, see [Running Terraform in Automation](https://developer.hashicorp.com/terraform/tutorials/automation/automate-terraform?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS) for some different approaches.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/apply#)
    
    [`-json`](https://developer.hashicorp.com/terraform/cli/commands/apply#json) - Enables the [machine readable JSON UI](https://developer.hashicorp.com/terraform/internals/machine-readable-ui) output. This implies `-input=false`, so the configuration must have no unassigned variable values to continue. To enable this flag, you must also either enable the `-auto-approve` flag or specify a previously-saved plan.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/apply#)
    
    [`-lock=false`](https://developer.hashicorp.com/terraform/cli/commands/apply#lock-false) - Don't hold a state lock during the operation. This is dangerous if others might concurrently run commands against the same workspace.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/apply#)
    
    [`-lock-timeout=DURATION`](https://developer.hashicorp.com/terraform/cli/commands/apply#lock-timeout-duration) - Unless locking is disabled with `-lock=false`, instructs Terraform to retry acquiring a lock for a period of time before returning an error. The duration syntax is a number followed by a time unit letter, such as "3s" for three seconds.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/apply#)
    
    [`-no-color`](https://developer.hashicorp.com/terraform/cli/commands/apply#no-color) - Disables terminal formatting sequences in the output. Use this if you are running Terraform in a context where its output will be rendered by a system that cannot interpret terminal formatting.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/apply#)
    
    [`-parallelism=n`](https://developer.hashicorp.com/terraform/cli/commands/apply#parallelism-n) - Limit the number of concurrent operations as Terraform [walks the graph](https://developer.hashicorp.com/terraform/internals/graph#walking-the-graph). Defaults to 10.
    
- [](https://developer.hashicorp.com/terraform/cli/commands/apply#)
    
    [`-replace=resource`](https://developer.hashicorp.com/terraform/cli/commands/apply#replace-resource) - Terraform will plan to replace this resource instance instead of doing an update or no-op action.
    
- All [planning modes](https://developer.hashicorp.com/terraform/cli/commands/plan#planning-modes) and [planning options](https://developer.hashicorp.com/terraform/cli/commands/plan#planning-options) for `terraform plan` - Customize how Terraform will create the plan. Only available when you run `terraform apply` without a saved plan file.
    

For configurations using [the `local` backend](https://developer.hashicorp.com/terraform/language/backend/local) only, `terraform apply` also accepts the legacy options [`-state`, `-state-out`, and `-backup`](https://developer.hashicorp.com/terraform/language/backend/local#command-line-arguments).

## [](https://developer.hashicorp.com/terraform/cli/commands/apply#passing-a-different-configuration-directory)Passing a Different Configuration Directory

Terraform v0.13 and earlier also accepted a directory path in place of the plan file argument to `terraform apply`, in which case Terraform would use that directory as the root module instead of the current working directory.

That usage was deprecated in Terraform v0.14 and removed in Terraform v0.15. If your workflow relies on overriding the root module directory, use [the `-chdir` global option](https://developer.hashicorp.com/terraform/cli/commands#switching-working-directory-with-chdir) instead, which works across all commands and makes Terraform consistently look in the given directory for all files it would normally read or write in the current working directory.

If your previous use of this legacy pattern was also relying on Terraform writing the `.terraform` subdirectory into the current working directory even though the root module directory was overridden, use [the `TF_DATA_DIR` environment variable](https://developer.hashicorp.com/terraform/cli/config/environment-variables#tf_data_dir) to direct Terraform to write the `.terraform` directory to a location other than the current working directory.

### 6f        Destroy Terraform managed infrastructure (terraform destroy)

# terraform destroy command

The `terraform destroy` command deprovisions all objects managed by a Terraform configuration.

While you will typically not want to destroy long-lived objects in a production environment, Terraform is sometimes used to manage ephemeral infrastructure for development purposes, in which case you can use `terraform destroy` to conveniently clean up all of those temporary objects once you are finished with your work.

## [](https://developer.hashicorp.com/terraform/cli/commands/destroy#usage)Usage

Usage: `terraform destroy [options]`

This command is just a convenience alias for the following command:

```
terraform apply -destroy
```

For that reason, this command accepts most of the options that [`terraform apply`](https://developer.hashicorp.com/terraform/cli/commands/apply) accepts, although it does not accept a plan file argument and forces the selection of the "destroy" planning mode.

You can also create a speculative destroy plan, to see what the effect of destroying would be, by running the following command:

```
terraform plan -destroy
```

This will run [`terraform plan`](https://developer.hashicorp.com/terraform/cli/commands/plan) in _destroy_ mode, showing you the proposed destroy changes without executing them.

**Note:** The `-destroy` option to `terraform apply` exists only in Terraform v0.15.2 and later. For earlier versions, you _must_ use `terraform destroy` to get the effect of `terraform apply -destroy`.

### [](https://developer.hashicorp.com/terraform/cli/commands/destroy#target-a-specific-resource)Target a specific resource

You can use the `-target` option to destroy a particular resource and its dependencies. For example, if your Terraform configuration contained a `aws_instance` resource with the label `example`, you could destroy that resource with the following command.

```
terraform destroy -target aws_instance.example
```

### 6g       Apply formatting and style adjustments to a configuration (terraform fmt)

# terraform fmt command

The `terraform fmt` command formats Terraform configuration file contents so that it matches the canonical format and style. This command applies a subset of the [Terraform language style conventions](https://developer.hashicorp.com/terraform/language/style#code-formatting), along with other minor adjustments for readability.

## [](https://developer.hashicorp.com/terraform/cli/commands/fmt#introduction)Introduction

Terraform commands that generate Terraform configuration produce configuration files that conform to the style imposed by `terraform fmt`. Follow this style in your files to ensure consistency.

The canonical format may change in minor ways between Terraform versions, so after upgrading Terraform we recommend to proactively run `terraform fmt` on your modules along with any other changes you are making to adopt the new version.

We do not consider new formatting rules in `terraform fmt` to be a breaking change in new versions of Terraform, but we minimize changes for configurations that already follow the style examples shown in the Terraform documentation. New formatting rules programmed into the `terraform fmt` command are usually expansions to include existing rules from the documentation. We recommend following the documented style even for decisions that `terraform fmt` does not yet apply automatically.

Formatting decisions are always subjective and so you might disagree with the decisions that `terraform fmt` makes. This command is intentionally opinionated and has no customization options because its primary goal is to encourage consistency of style between different Terraform codebases, even though the chosen style can never be everyone's favorite.

We recommend that you follow the style conventions applied by `terraform fmt` when writing Terraform modules, but if you find the results particularly objectionable then you may choose not to use this command, and possibly choose to use a third-party formatting tool instead. If you choose to use a third-party tool then you should also run it on files that are generated automatically by Terraform, to get consistency between your hand-written files and the generated files.

## [](https://developer.hashicorp.com/terraform/cli/commands/fmt#usage)Usage

Usage: `terraform fmt [options] [target...]`

By default, the `terraform fmt` command scans your current directory for configuration files. You can also provide a `target` argument to tell `terraform fmt` to scan:

- A directory
- A specific file
- Standard input by supplying a single dash (`-`).

The `terraform fmt` command accepts the following arguments.

|Flag|Description|Required|
|:--|:--|:--|
|`-list=false`|Prevents the command from listing the files containing formatting inconsistencies.|Optional|
|`-diff`|Displays the diffs of formatting changes.|Optional|
|`-write=false`|Prevents the command from overwriting files. This behavior is implied by the `-check` flag or if the input is from `STDIN`.|Optional|
|`-check`|Checks if the input is formatted. The exit status is `0` if the command's input is properly formatted. Otherwise, the exit status is non-zero, and the command outputs a list of improperly formatted file names.|Optional|
|`-recursive`|Processes files in subdirectories in addition to the current directory. By default, the command only processes the specified, or current, directory.|Optional|

## 7         Implement and maintain state

# Backend block configuration overview

This topic provides an overview of how to configure the `backend` block in your Terraform configuration. The `backend` defines where Terraform stores its [state](https://developer.hashicorp.com/terraform/language/state) data files.

## [](https://developer.hashicorp.com/terraform/language/backend#overview)Overview

Terraform uses persisted state data to keep track of the resources it manages. You can either [integrate with HCP Terraform](https://developer.hashicorp.com/terraform/language/terraform#terraform-cloud) to store state data or define a `backend` block to store state in a remote object. This lets multiple people access the state data and work together on that collection of infrastructure resources.

## [](https://developer.hashicorp.com/terraform/language/backend#define-a-backend-block)Define a `backend` block

Do not configure a backend when connecting your configuration to workspaces in HCP Terraform or Terraform Enterprise. These systems automatically manage state in the workspaces associated with your configuration. If your configuration includes a [`cloud` block](https://developer.hashicorp.com/terraform/language/terraform#terraform-cloud), it cannot include a `backend` block.

To configure a backend, add a nested `backend` block within the top-level `terraform` block. The following example configures the `remote` backend.

```
terraform {
  backend "remote" {
    organization = "example_corp"

    workspaces {
      name = "my-app-prod"
    }
  }
}
```

There are some important limitations on backend configuration:

- A configuration can only provide one backend block.
- A backend block cannot refer to named values (like input variables, locals, or data source attributes).
- You cannot reference values declared within backend blocks elsewhere in the configuration. Refer to [References to Resource Attributes](https://developer.hashicorp.com/terraform/language/expressions/references#references-to-resource-attributes) for more details.

### [](https://developer.hashicorp.com/terraform/language/backend#default-backend)Default backend

Terraform uses a backend called [`local`](https://developer.hashicorp.com/terraform/language/backend/local) by default. The `local` backend type stores state as a local file on disk.

### [](https://developer.hashicorp.com/terraform/language/backend#backend-types)Backend types

Terraform ships with several built-in backend types. Some backends function as remote disks for state files, while others support locking the state during Terraform operations to prevent conflicts and inconsistencies. You cannot load additional backends as plugins.

Specify the backend type as the `backend` block label. The following example instructs Terraform to use a remote backend:

```
backend "remote" {
  organization = "example_corp"
  . . . 
}
```

The specified backend must be available in the version of Terraform you are using.

### [](https://developer.hashicorp.com/terraform/language/backend#backend-arguments)Backend arguments

The arguments in the `backend` block body are specific to the backend type. They specify where and how the backend stores configuration state. Some backend types allow you to configure additional behaviors. Refer to the documentation for your backend for additional information.

Some backends allow you to provide access credentials as part of the configuration, but we do not recommend including access credentials directly in the configuration. Instead, leave credential-related arguments unset and provide them using the credentials files or environment variables that are conventional for the target system.

Refer to the page for each backend type for full details and that type's configuration arguments.

### [](https://developer.hashicorp.com/terraform/language/backend#credentials-and-sensitive-data)Credentials and sensitive data

Backends store state in a remote service, which allows multiple people to access it. Accessing remote state generally requires access credentials, since state data contains extremely sensitive information.

**Warning:** We recommend using environment variables to supply credentials and other sensitive data. If you use `-backend-config` or hardcode these values directly in your configuration, Terraform will include these values in both the `.terraform` subdirectory and in plan files. This can leak sensitive credentials.

Terraform writes the backend configuration in plain text in two separate files.

- The `.terraform/terraform.tfstate` file contains the backend configuration for the current working directory.
- All plan files capture the information in `.terraform/terraform.tfstate` at the time the plan was created. This helps ensure Terraform is applying the plan to correct set of infrastructure.

When applying a plan that you previously saved to a file, Terraform uses the backend configuration stored in that file instead of the current backend settings. If that configuration contains time-limited credentials, they may expire before you finish applying the plan. Use environment variables to pass credentials when you need to use different values between the plan and apply steps.

## [](https://developer.hashicorp.com/terraform/language/backend#initialize-the-backend)Initialize the backend

When you change a backend's configuration, you must run `terraform init` again to validate and configure the backend before you can perform any plans, applies, or state operations.

After you initialize, Terraform creates a `.terraform/` directory locally. This directory contains the most recent backend configuration, including any authentication parameters you provided to the Terraform CLI. Do not check this directory into Git, as it may contain sensitive credentials for your remote backend.

The local backend configuration is different and entirely separate from the `terraform.tfstate` file that contains [state data](https://developer.hashicorp.com/terraform/language/state) about your real-world infrastructure. Terraform stores the `terraform.tfstate` file in your remote backend.

When you change backends, Terraform gives you the option to migrate your state to the new backend. This lets you adopt backends without losing any existing state.

**Important:** Before migrating to a new backend, we strongly recommend manually backing up your state by copying your `terraform.tfstate` file to another location.

## [](https://developer.hashicorp.com/terraform/language/backend#partial-configuration)Partial configuration

You do not need to specify every required argument in the backend configuration. Omitting certain arguments may be desirable if some arguments are provided automatically by an automation script running Terraform. When some or all of the arguments are omitted, we call this a _partial configuration_.

With a partial configuration, the remaining configuration arguments must be provided as part of [the initialization process](https://developer.hashicorp.com/terraform/cli/init).

There are several ways to supply the remaining arguments:

- **File**: A configuration file may be specified via the `init` command line. To specify a file, use the `-backend-config=PATH` option when running `terraform init`. The partial configuration must have a `backend` block containing keys set to empty values. When you run the `terraform init -backend-config="<path-to-remaining-configuration>"` command, Terraform populates the keys in the partial `backend` configuration with matching key values from the specified configuration file. In the following example, the keys defined in the `backend` block of the `state.tf` configuration file are populated with values from the `state.config` configuration:
    
    ```
    $ `terraform init -backend-config="./state.config"`
    ```
    
    ```
    # state.tf
    terraform {
      backend "s3" {
        bucket = "" 
        key    = ""
        region = ""
        profile= ""
      }
    }
    ```
    
    ```
    # state.config
    bucket = "your-bucket" 
    key    = "your-state.tfstate"
    region = "eu-central-1"
    profile= "Your_Profile"
    ```
    
    When your configuration file contains secrets, you can store them in a secure data store, such as [Vault](https://www.vaultproject.io/), in which case it must be downloaded to the local disk before running Terraform.
    
- **Command-line key/value pairs**: Key/value pairs can be specified via the `init` command line. Note that many shells retain command-line flags in a history file, so this isn't recommended for secrets. To specify a single key/value pair, use the `-backend-config="KEY=VALUE"` option when running `terraform init`.
    
- **Interactively**: Terraform will interactively ask you for the required values, unless interactive input is disabled. Terraform will not prompt for optional values.
    

If backend settings are provided in multiple locations, the top-level settings are merged such that any command-line options override the settings in the main configuration and then the command-line options are processed in order, with later options overriding values set by earlier options.

The final, merged configuration is stored on disk in the `.terraform` directory, which should be ignored from version control. This means that sensitive information can be omitted from version control, but it will be present in plain text on local disk when running Terraform.

When using partial configuration, Terraform requires at a minimum that an empty backend configuration is specified in one of the root Terraform configuration files, to specify the backend type. For example:

```
terraform {
  backend "consul" {}
}
```

### [](https://developer.hashicorp.com/terraform/language/backend#file)File

A backend configuration file has the contents of the `backend` block as top-level attributes, without the need to wrap it in another `terraform` or `backend` block:

```
address = "demo.consul.io"
path    = "example_app/terraform_state"
scheme  = "https"
```

`*.backendname.tfbackend` (e.g. `config.consul.tfbackend`) is the recommended naming pattern. Terraform will not prevent you from using other names but following this convention will help your editor understand the content and likely provide better editing experience as a result.

### [](https://developer.hashicorp.com/terraform/language/backend#command-line-key-value-pairs)Command-line key/value pairs

The same settings can alternatively be specified on the command line as follows:

```
$ terraform init \
    -backend-config="address=demo.consul.io" \
    -backend-config="path=example_app/terraform_state" \
    -backend-config="scheme=https"
```

The Consul backend also requires a Consul access token. Per the recommendation above of omitting credentials from the configuration and using other mechanisms, the Consul token would be provided by setting either the `CONSUL_HTTP_TOKEN` or `CONSUL_HTTP_AUTH` environment variables. See the documentation of your chosen backend to learn how to provide credentials to it outside of its main configuration.

## [](https://developer.hashicorp.com/terraform/language/backend#change-configuration)Change configuration

You can change your backend configuration at any time. You can change both the configuration itself as well as the type of backend (for example from "consul" to "s3").

Terraform will automatically detect any changes in your configuration and request a [reinitialization](https://developer.hashicorp.com/terraform/cli/init). As part of the reinitialization process, Terraform will ask if you'd like to migrate your existing state to the new configuration. This allows you to easily switch from one backend to another.

If you're using multiple [workspaces](https://developer.hashicorp.com/terraform/language/state/workspaces), Terraform can copy all workspaces to the destination. If Terraform detects you have multiple workspaces, it will ask if this is what you want to do.

If you're just reconfiguring the same backend, Terraform will still ask if you want to migrate your state. You can respond "no" in this scenario.

## [](https://developer.hashicorp.com/terraform/language/backend#remove-a-backend-configuration)Remove a backend configuration

Remove the `backend` block from your configuration and [reinitialize](https://developer.hashicorp.com/terraform/cli/init) the directory when prompted. Terraform also prompts you to migrate the state to the default `local` backend.

### 7a       Describe default local backend

# local

**Kind: Enhanced**

The local backend stores state on the local filesystem, locks that state using system APIs, and performs operations locally.

## [](https://developer.hashicorp.com/terraform/language/backend/local#example-configuration)Example Configuration

```
terraform {
  backend "local" {
    path = "relative/path/to/terraform.tfstate"
  }
}
```

## [](https://developer.hashicorp.com/terraform/language/backend/local#data-source-configuration)Data Source Configuration

```
data "terraform_remote_state" "foo" {
  backend = "local"

  config = {
    path = "${path.module}/../../terraform.tfstate"
  }
}
```

## [](https://developer.hashicorp.com/terraform/language/backend/local#configuration-variables)Configuration variables

The following configuration options are supported:

- [](https://developer.hashicorp.com/terraform/language/backend/local#)[`path`](https://developer.hashicorp.com/terraform/language/backend/local#path) - (Optional) The path to the `tfstate` file. This defaults to "terraform.tfstate" relative to the root module by default.
- [](https://developer.hashicorp.com/terraform/language/backend/local#)[`workspace_dir`](https://developer.hashicorp.com/terraform/language/backend/local#workspace_dir) - (Optional) The path to non-default workspaces.

## [](https://developer.hashicorp.com/terraform/language/backend/local#command-line-arguments)Command Line Arguments

This section describes legacy features that we've preserved for backward compatibility but that we no longer recommend. See below for more details.

For configurations that include a `backend "local"` block or that default to the local backend by not specifying a backend at all, most commands that either read or write state snapshots from the backend accept the following additional arguments:

- [](https://developer.hashicorp.com/terraform/language/backend/local#)
    
    [`-state=FILENAME`](https://developer.hashicorp.com/terraform/language/backend/local#state-filename) - overrides the state filename when _reading_ the prior state snapshot.
    
- [](https://developer.hashicorp.com/terraform/language/backend/local#)
    
    [`-state-out=FILENAME`](https://developer.hashicorp.com/terraform/language/backend/local#state-out-filename) - overrides the state filename when _writing_ new state snapshots.
    
    If you use `-state` without also using `-state-out` then Terraform will use the `-state` filename for both `-state` and `-state-out`, which means Terraform will overwrite the input file if it creates a new state snapshot.
    
- [](https://developer.hashicorp.com/terraform/language/backend/local#)
    
    [`-backup=FILENAME`](https://developer.hashicorp.com/terraform/language/backend/local#backup-filename) - overrides the default filename that the local backend would normally choose dynamically to create backup files when it writes new state.
    
    If you use `-state` without also using `-backup` then Terraform will use the `-state` filename as a filename prefix for generating a backup filename. You can use `-backup=-` (that is, set the filename to just the ASCII dash character) to disable the creation of backup files altogether.
    

These three options are preserved for backward-compatibility with earlier workflows that predated the introduction of built-in remote state, where users would write wrapper scripts that fetch prior state before running Terraform and then save the new state after Terraform exits, in which case the three arguments would typically all be paths within a temporary directory used just for one operation.

Because these old workflows predate the introduction of the possibility of [multiple workspaces](https://developer.hashicorp.com/terraform/language/state/workspaces), setting them overrides Terraform's usual behavior of selecting a different state filename based on the selected workspace. If you use all three of these options then the selected workspace has no effect on which filenames Terraform will select for state files, and so you'll need to select different filenames yourself if you wish to keep workspace state files distinct from one another.

These three options have no effect for configurations that have a different backend type selected.

We do not recommend using these options in new systems, even if you are running Terraform in automation. Instead, [select a different backend which supports remote state](https://developer.hashicorp.com/terraform/language/backend) and configure it within your root module, which ensures that everyone working on your configuration will automatically retrieve and store state in the correct shared location without any special command line options.

### 7b       Describe state locking

# State Locking

If supported by your [backend](https://developer.hashicorp.com/terraform/language/backend), Terraform will lock your state for all operations that could write state. This prevents others from acquiring the lock and potentially corrupting your state.

State locking happens automatically on all operations that could write state. You do not see any message that it happens. If state locking fails, Terraform does not continue. You can disable state locking for most commands with the `-lock=false` flag, but we do not recommend it.

If acquiring the lock takes longer than expected, Terraform outputs a status message. If Terraform does not output a message, state locking is still occurring if your backend supports it.

Not all backends support locking. The [documentation for each backend](https://developer.hashicorp.com/terraform/language/backend) includes details on whether it supports locking or not.

## [](https://developer.hashicorp.com/terraform/language/state/locking#force-unlock)Force Unlock

Terraform has a [force-unlock command](https://developer.hashicorp.com/terraform/cli/commands/force-unlock) to manually unlock the state if unlocking failed.

**Be very careful with this command.** If you unlock the state when someone else is holding the lock it could cause multiple writers. Force unlock should only be used to unlock your own lock in the situation where automatic unlocking failed.

To protect you, the `force-unlock` command requires a unique lock ID. Terraform will output this lock ID if unlocking fails. This lock ID acts as a [nonce](https://en.wikipedia.org/wiki/Cryptographic_nonce), ensuring that locks and unlocks target the correct lock.

### 7c       Handle backend and cloud integration authentication methods

### 7d       Differentiate remote state back end options

### 7e       Manage resource drift and Terraform state

### 7f        Describe backend block and cloud integration in configuration

### 7g       Understand secret management in state files

## 8         Read, generate, and modify configuration

### 8a       Demonstrate use of variables and outputs

# Input Variables

> **Hands-on:** Try the [Customize Terraform Configuration with Variables](https://developer.hashicorp.com/terraform/tutorials/configuration-language/variables?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS) tutorial.

Input variables let you customize aspects of Terraform modules without altering the module's own source code. This functionality allows you to share modules across different Terraform configurations, making your module composable and reusable.

When you declare variables in the root module of your configuration, you can set their values using CLI options and environment variables. When you declare them in [child modules](https://developer.hashicorp.com/terraform/language/modules), the calling module should pass values in the `module` block.

If you're familiar with traditional programming languages, it can be useful to compare Terraform modules to function definitions:

- Input variables are like function arguments.
- [Output values](https://developer.hashicorp.com/terraform/language/values/outputs) are like function return values.
- [Local values](https://developer.hashicorp.com/terraform/language/values/locals) are like a function's temporary local variables.

**Note:** For brevity, input variables are often referred to as just "variables" or "Terraform variables" when it is clear from context what sort of variable is being discussed. Other kinds of variables in Terraform include _environment variables_ (set by the shell where Terraform runs) and _expression variables_ (used to indirectly represent a value in an [expression](https://developer.hashicorp.com/terraform/language/expressions)).

## [](https://developer.hashicorp.com/terraform/language/values/variables#declaring-an-input-variable)Declaring an Input Variable

Each input variable accepted by a module must be declared using a `variable` block:

```
variable "image_id" {
  type = string
}

variable "availability_zone_names" {
  type    = list(string)
  default = ["us-west-1a"]
}

variable "docker_ports" {
  type = list(object({
    internal = number
    external = number
    protocol = string
  }))
  default = [
    {
      internal = 8300
      external = 8300
      protocol = "tcp"
    }
  ]
}
```

The label after the `variable` keyword is a name for the variable, which must be unique among all variables in the same module. This name is used to assign a value to the variable from outside and to reference the variable's value from within the module.

The name of a variable can be any valid [identifier](https://developer.hashicorp.com/terraform/language/syntax/configuration#identifiers) _except_ the following: `source`, `version`, `providers`, `count`, `for_each`, `lifecycle`, `depends_on`, `locals`.

These names are reserved for meta-arguments in [module configuration blocks](https://developer.hashicorp.com/terraform/language/modules/syntax), and cannot be declared as variable names.

## [](https://developer.hashicorp.com/terraform/language/values/variables#arguments)Arguments

Terraform CLI defines the following optional arguments for variable declarations:

- [`default`](https://developer.hashicorp.com/terraform/language/values/variables#default-values) - A default value which then makes the variable optional.
- [`type`](https://developer.hashicorp.com/terraform/language/values/variables#type-constraints) - This argument specifies what value types are accepted for the variable.
- [`description`](https://developer.hashicorp.com/terraform/language/values/variables#input-variable-documentation) - This specifies the input variable's documentation.
- [`validation`](https://developer.hashicorp.com/terraform/language/values/variables#custom-validation-rules) - A block to define validation rules, usually in addition to type constraints.
- [`ephemeral`](https://developer.hashicorp.com/terraform/language/values/variables#exclude-values-from-state) - This variable is available during runtime, but not written to state or plan files.
- [`sensitive`](https://developer.hashicorp.com/terraform/language/values/variables#suppressing-values-in-cli-output) - Limits Terraform UI output when the variable is used in configuration.
- [`nullable`](https://developer.hashicorp.com/terraform/language/values/variables#disallowing-null-input-values) - Specify if the variable can be `null` within the module.

### [](https://developer.hashicorp.com/terraform/language/values/variables#default-values)Default values

The variable declaration can also include a `default` argument. If present, the variable is considered to be _optional_ and the default value will be used if no value is set when calling the module or running Terraform. The `default` argument requires a literal value and cannot reference other objects in the configuration.

### [](https://developer.hashicorp.com/terraform/language/values/variables#type-constraints)Type Constraints

The `type` argument in a `variable` block allows you to restrict the [type of value](https://developer.hashicorp.com/terraform/language/expressions/types) that will be accepted as the value for a variable. If no type constraint is set then a value of any type is accepted.

While type constraints are optional, we recommend specifying them; they can serve as helpful reminders for users of the module, and they allow Terraform to return a helpful error message if the wrong type is used.

Type constraints are created from a mixture of type keywords and type constructors. The supported type keywords are:

- [](https://developer.hashicorp.com/terraform/language/values/variables#)[`string`](https://developer.hashicorp.com/terraform/language/values/variables#string)
- [](https://developer.hashicorp.com/terraform/language/values/variables#)[`number`](https://developer.hashicorp.com/terraform/language/values/variables#number)
- [](https://developer.hashicorp.com/terraform/language/values/variables#)[`bool`](https://developer.hashicorp.com/terraform/language/values/variables#bool)

The type constructors allow you to specify complex types such as collections:

- [](https://developer.hashicorp.com/terraform/language/values/variables#)[`list(<TYPE>)`](https://developer.hashicorp.com/terraform/language/values/variables#list)
- [](https://developer.hashicorp.com/terraform/language/values/variables#)[`set(<TYPE>)`](https://developer.hashicorp.com/terraform/language/values/variables#set)
- [](https://developer.hashicorp.com/terraform/language/values/variables#)[`map(<TYPE>)`](https://developer.hashicorp.com/terraform/language/values/variables#map)
- [](https://developer.hashicorp.com/terraform/language/values/variables#)[`object({<ATTR NAME> = <TYPE>, ... })`](https://developer.hashicorp.com/terraform/language/values/variables#object)
- [](https://developer.hashicorp.com/terraform/language/values/variables#)[`tuple([<TYPE>, ...])`](https://developer.hashicorp.com/terraform/language/values/variables#tuple)

The keyword `any` may be used to indicate that any type is acceptable. For more information on the meaning and behavior of these different types, as well as detailed information about automatic conversion of complex types, see [Type Constraints](https://developer.hashicorp.com/terraform/language/expressions/types).

If both the `type` and `default` arguments are specified, the given default value must be convertible to the specified type.

### [](https://developer.hashicorp.com/terraform/language/values/variables#input-variable-documentation)Input Variable Documentation

Because the input variables of a module are part of its user interface, you can briefly describe the purpose of each variable using the optional `description` argument:

```
variable "image_id" {
  type        = string
  description = "The id of the machine image (AMI) to use for the server."
}
```

The description should concisely explain the purpose of the variable and what kind of value is expected. This description string might be included in documentation about the module, and so it should be written from the perspective of the user of the module rather than its maintainer. For commentary for module maintainers, use comments.

### [](https://developer.hashicorp.com/terraform/language/values/variables#custom-validation-rules)Custom Validation Rules

This feature was introduced in Terraform CLI v0.13.0.

You can specify custom validation rules for a particular variable by adding a `validation` block within the corresponding `variable` block. The example below checks whether the AMI ID has the correct syntax.

```
variable "image_id" {
  type        = string
  description = "The id of the machine image (AMI) to use for the server."

  validation {
    condition     = length(var.image_id) > 4 && substr(var.image_id, 0, 4) == "ami-"
    error_message = "The image_id value must be a valid AMI id, starting with \"ami-\"."
  }
}
```

Refer to [Custom Condition Checks](https://developer.hashicorp.com/terraform/language/expressions/custom-conditions#input-variable-validation) for more details.

### [](https://developer.hashicorp.com/terraform/language/values/variables#exclude-values-from-state)Exclude values from state

**Note**: Ephemeral variables are available in Terraform v1.10 and later.

Setting a variable as `ephemeral` makes it available during runtime, but Terraform omits ephemeral values from state and plan files. Marking an input variable as `ephemeral` is useful for data that only needs to exist temporarily, such as a short-lived token or session identifier.

Mark an input variable as ephemeral by setting the `ephemeral` argument to `true`:

```
variable "session_token" {
  type      = string
  ephemeral = true
}
```

Ephemeral variables are available during the current Terraform operation, and Terraform does not store them in state or plan files. So, unlike [`sensitive`](https://developer.hashicorp.com/terraform/language/values/variables#sensitive) inputs, Terraform ensures ephemeral values are not available beyond the lifetime of the current Terraform run.

You can only reference ephemeral variables in specific contexts or Terraform throws an error. The following are valid contexts for referencing ephemeral variables:

- In a [write-only argument](https://developer.hashicorp.com/terraform/language/resources/ephemeral/write-only)
- Another ephemeral variable
- In [local values](https://developer.hashicorp.com/terraform/language/values/locals#ephemeral-values)
- In [ephemeral resources](https://developer.hashicorp.com/terraform/language/resources/ephemeral)
- In [ephemeral outputs](https://developer.hashicorp.com/terraform/language/values/outputs#ephemeral-avoid-storing-values-in-state-or-plan-files)
- Configuring providers in the `provider` block
- In [provisioner](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax) and [connection](https://developer.hashicorp.com/terraform/language/resources/provisioners/connection) blocks

If another expression references an `ephemeral` variable, that expression implicitly becomes ephemeral.

```
variable "password" {
  type      = string
  ephemeral = true
}

locals {
  # local.database_password is implicitly ephemeral because 
  # var.password is ephemeral.
  database_password = var.password
}
```

The `local.database_password` value is implicitly ephemeral because it depends on `var.password`.

### [](https://developer.hashicorp.com/terraform/language/values/variables#suppressing-values-in-cli-output)Suppressing Values in CLI Output

> **Hands-on:** Try the [Protect Sensitive Input Variables](https://developer.hashicorp.com/terraform/tutorials/configuration-language/sensitive-variables?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS) tutorial.

Setting a variable as `sensitive` prevents Terraform from showing its value in the `plan` or `apply` output, when you use that variable elsewhere in your configuration.

Terraform will still record sensitive values in the [state](https://developer.hashicorp.com/terraform/language/state), and so anyone who can access the state data will have access to the sensitive values in cleartext. If you want to omit a value from state, mark that value as [`ephemeral`](https://developer.hashicorp.com/terraform/language/values/variables#ephemeral). For more information, refer to [Sensitive Data in State](https://developer.hashicorp.com/terraform/language/state/sensitive-data).

Declare a variable as sensitive by setting the `sensitive` argument to `true`:

```
variable "user_information" {
  type = object({
    name    = string
    address = string
  })
  sensitive = true
}

resource "some_resource" "a" {
  name    = var.user_information.name
  address = var.user_information.address
}
```

Any expressions whose result depends on the sensitive variable will be treated as sensitive themselves, and so in the above example the two arguments of `resource "some_resource" "a"` will also be hidden in the plan output:

```
Terraform will perform the following actions:
 
  # some_resource.a will be created
  + resource "some_resource" "a" {
      + name    = (sensitive value)
      + address = (sensitive value)
    }
 
Plan: 1 to add, 0 to change, 0 to destroy.
```

In some cases where you use a sensitive variable inside a nested block, Terraform may treat the entire block as redacted. This happens for resource types where all of the blocks of a particular type are required to be unique, and so disclosing the content of one block might imply the content of a sibling block.

```
  # some_resource.a will be updated in-place
  ~ resource "some_resource" "a" {
      ~ nested_block {
          # At least one attribute in this block is (or was) sensitive,
          # so its contents will not be displayed.
        }
    }
```

A provider can also [declare an attribute as sensitive](https://developer.hashicorp.com/terraform/plugin/sdkv2/best-practices/sensitive-state#using-the-sensitive-flag), which will cause Terraform to hide it from regular output regardless of how you assign it a value. For more information, see [Sensitive Resource Attributes](https://developer.hashicorp.com/terraform/language/expressions/references#sensitive-resource-attributes).

If you use a sensitive value as part of an [output value](https://developer.hashicorp.com/terraform/language/values/outputs) then Terraform will require you to also mark the output value itself as sensitive, to confirm that you intended to export it.

#### [](https://developer.hashicorp.com/terraform/language/values/variables#cases-where-terraform-may-disclose-a-sensitive-variable)Cases where Terraform may disclose a sensitive variable

A `sensitive` variable is a configuration-centered concept, and values are sent to providers without any obfuscation. A provider error could disclose a value if that value is included in the error message. For example, a provider might return the following error even if "foo" is a sensitive value: `"Invalid value 'foo' for field"`

If a resource attribute is used as, or part of, the provider-defined resource id, an `apply` will disclose the value. In the example below, the `prefix` attribute has been set to a sensitive variable, but then that value ("jae") is later disclosed as part of the resource id:

```
  # random_pet.animal will be created
  + resource "random_pet" "animal" {
      + id        = (known after apply)
      + length    = 2
      + prefix    = (sensitive value)
      + separator = "-"
    }
 
Plan: 1 to add, 0 to change, 0 to destroy.
 
...
 
random_pet.animal: Creating...
random_pet.animal: Creation complete after 0s [id=jae-known-mongoose]
```

### [](https://developer.hashicorp.com/terraform/language/values/variables#disallowing-null-input-values)Disallowing Null Input Values

This feature is available in Terraform v1.1.0 and later.

The `nullable` argument in a variable block controls whether the module caller may assign the value `null` to the variable.

```
variable "example" {
  type     = string
  nullable = false
}
```

The default value for `nullable` is `true`. When `nullable` is `true`, `null` is a valid value for the variable, and the module configuration must always account for the possibility of the variable value being `null`. Passing a `null` value as a module input argument will override any `default` value.

Setting `nullable` to `false` ensures that the variable value will never be `null` within the module. If `nullable` is `false` and the variable has a `default` value, then Terraform uses the default when a module input argument is `null`.

The `nullable` argument only controls where the direct value of the variable may be `null`. For variables of collection or structural types, such as lists or objects, the caller may still use `null` in nested elements or attributes, as long as the collection or structure itself is not null.

## [](https://developer.hashicorp.com/terraform/language/values/variables#using-input-variable-values)Using Input Variable Values

Within the module that declared a variable, its value can be accessed from within [expressions](https://developer.hashicorp.com/terraform/language/expressions) as `var.<NAME>`, where `<NAME>` matches the label given in the declaration block:

**Note:** Input variables are _created_ by a `variable` block, but you _reference_ them as attributes on an object named `var`.

```
resource "aws_instance" "example" {
  instance_type = "t2.micro"
  ami           = var.image_id
}
```

The value assigned to a variable can only be accessed in expressions within the module where it was declared.

## [](https://developer.hashicorp.com/terraform/language/values/variables#assigning-values-to-root-module-variables)Assigning Values to Root Module Variables

When variables are declared in the root module of your configuration, they can be set in a number of ways:

- [In an HCP Terraform workspace](https://developer.hashicorp.com/terraform/cloud-docs/workspaces/variables).
- Individually, with the `-var` command line option.
- In variable definitions (`.tfvars`) files, either specified on the command line or automatically loaded.
- As environment variables.

The following sections describe these options in more detail. This section does not apply to _child_ modules, where values for input variables are instead assigned in the configuration of their parent module, as described in [_Modules_](https://developer.hashicorp.com/terraform/language/modules).

### [](https://developer.hashicorp.com/terraform/language/values/variables#variables-on-the-command-line)Variables on the Command Line

To specify individual variables on the command line, use the `-var` option when running the `terraform plan` and `terraform apply` commands:

```
terraform apply -var="image_id=ami-abc123"
terraform apply -var='image_id_list=["ami-abc123","ami-def456"]' -var="instance_type=t2.micro"
terraform apply -var='image_id_map={"us-east-1":"ami-abc123","us-east-2":"ami-def456"}'
```

The above examples show appropriate syntax for Unix-style shells, such as on Linux or macOS. For more information on shell quoting, including additional examples for Windows Command Prompt, see [Input Variables on the Command Line](https://developer.hashicorp.com/terraform/cli/commands/plan#input-variables-on-the-command-line).

You can use the `-var` option multiple times in a single command to set several different variables.

[](https://developer.hashicorp.com/terraform/language/values/variables#)

### [](https://developer.hashicorp.com/terraform/language/values/variables#variable-definitions-tfvars-files)Variable Definitions (`.tfvars`) Files

To set lots of variables, it is more convenient to specify their values in a _variable definitions file_ (with a filename ending in either `.tfvars` or `.tfvars.json`) and then specify that file on the command line with `-var-file`:

Linux, Mac OS, and UNIX:

```
terraform apply -var-file="testing.tfvars"
```

PowerShell:

```
terraform apply -var-file='testing.tfvars'
```

Windows `cmd.exe`:

```
terraform apply -var-file="testing.tfvars"
```

**Note:** This is how HCP Terraform passes [workspace variables](https://developer.hashicorp.com/terraform/cloud-docs/workspaces/variables) to Terraform.

A variable definitions file uses the same basic syntax as Terraform language files, but consists only of variable name assignments:

```
image_id = "ami-abc123"
availability_zone_names = [
  "us-east-1a",
  "us-west-1c",
]
```

Terraform also automatically loads a number of variable definitions files if they are present:

- Files named exactly `terraform.tfvars` or `terraform.tfvars.json`.
- Any files with names ending in `.auto.tfvars` or `.auto.tfvars.json`.

Files whose names end with `.json` are parsed instead as JSON objects, with the root object properties corresponding to variable names:

```
{
  "image_id": "ami-abc123",
  "availability_zone_names": ["us-west-1a", "us-west-1c"]
}
```

### [](https://developer.hashicorp.com/terraform/language/values/variables#environment-variables)Environment Variables

As a fallback for the other ways of defining variables, Terraform searches the environment of its own process for environment variables named `TF_VAR_` followed by the name of a declared variable.

This can be useful when running Terraform in automation, or when running a sequence of Terraform commands in succession with the same variables. For example, at a `bash` prompt on a Unix system:

```
$ export TF_VAR_image_id=ami-abc123
$ terraform plan
...
```

On operating systems where environment variable names are case-sensitive, Terraform matches the variable name exactly as given in configuration, and so the required environment variable name will usually have a mix of upper and lower case letters as in the above example.

### [](https://developer.hashicorp.com/terraform/language/values/variables#complex-typed-values)Complex-typed Values

When variable values are provided in a variable definitions file, you can use Terraform's usual syntax for [literal expressions](https://developer.hashicorp.com/terraform/language/expressions/types#literal-expressions) to assign complex-typed values, like lists and maps.

Some special rules apply to the `-var` command line option and to environment variables. For convenience, Terraform defaults to interpreting `-var` and environment variable values as literal strings, which need only shell quoting, and no special quoting for Terraform. For example, in a Unix-style shell:

```
$ export TF_VAR_image_id='ami-abc123'
```

However, if a root module variable uses a [type constraint](https://developer.hashicorp.com/terraform/language/values/variables#type-constraints) to require a complex value (list, set, map, object, or tuple), Terraform will instead attempt to parse its value using the same syntax used within variable definitions files, which requires careful attention to the string escaping rules in your shell:

```
$ export TF_VAR_availability_zone_names='["us-west-1b","us-west-1d"]'
```

For readability, and to avoid the need to worry about shell escaping, we recommend always setting complex variable values via variable definitions files. For more information on quoting and escaping for `-var` arguments, see [Input Variables on the Command Line](https://developer.hashicorp.com/terraform/cli/commands/plan#input-variables-on-the-command-line).

### [](https://developer.hashicorp.com/terraform/language/values/variables#values-for-undeclared-variables)Values for Undeclared Variables

If you have defined a variable value, but not its corresponding `variable {}` definition, you may get an error or warning depending on how you have provided that value.

If you provide values for undeclared variables defined as [environment variables](https://developer.hashicorp.com/terraform/language/values/variables#environment-variables) you will not get an error or warning. This is because environment variables may be declared but not used in all configurations that might be run.

If you provide values for undeclared variables defined [in a file](https://developer.hashicorp.com/terraform/language/values/variables#variable-definitions-tfvars-files) you will get a warning. This is to help in cases where you have provided a variable value _meant_ for a variable declaration, but perhaps there is a mistake in the value definition. For example, the following configuration:

```
variable "moose" {
  type = string
}
```

And the following `.tfvars` file:

```
mosse = "Moose"
```

Will cause Terraform to warn you that there is no variable declared `"mosse"`, which can help you spot this mistake.

If you use `.tfvars` files across multiple configurations and expect to continue to see this warning, you can use the [`-compact-warnings`](https://developer.hashicorp.com/terraform/cli/commands/plan#compact-warnings) option to simplify your output.

If you provide values for undeclared variables on the [command line](https://developer.hashicorp.com/terraform/language/values/variables#variables-on-the-command-line), Terraform will return an error. To avoid this error, either declare a variable block for the value, or remove the variable value from your Terraform call.

### [](https://developer.hashicorp.com/terraform/language/values/variables#variable-definition-precedence)Variable Definition Precedence

The above mechanisms for setting variables can be used together in any combination. If the same variable is assigned multiple values, Terraform uses the _last_ value it finds, overriding any previous values. Note that the same variable cannot be assigned multiple values within a single source.

Terraform loads variables in the following order, with later sources taking precedence over earlier ones:

- Environment variables
- The `terraform.tfvars` file, if present.
- The `terraform.tfvars.json` file, if present.
- Any `*.auto.tfvars` or `*.auto.tfvars.json` files, processed in lexical order of their filenames.
- Any `-var` and `-var-file` options on the command line, in the order they are provided. (This includes variables set by an HCP Terraform workspace.)

**Important:** In Terraform 0.12 and later, variables with map and object values behave the same way as other variables: the last value found overrides the previous values. This is a change from previous versions of Terraform, which would _merge_ map values instead of overriding them.

#### [](https://developer.hashicorp.com/terraform/language/values/variables#variable-precedence-within-terraform-tests)Variable precedence within Terraform tests

Within Terraform test files, you can specify variable values within `variables` blocks, either nested within `run` blocks or defined directly within the file.

Variables defined in this way take precedence over all other mechanisms during test execution, with variables defined within `run` blocks taking precedence over those defined within the file.

# Output Values

Output values make information about your infrastructure available on the command line, and can expose information for other Terraform configurations to use. Output values are similar to return values in programming languages.

> **Hands-on:** Try the [Output Data From Terraform](https://developer.hashicorp.com/terraform/tutorials/configuration-language/outputs) tutorial.

Output values have several uses:

- A child module can use outputs to expose a subset of its resource attributes to a parent module.
- A root module can use outputs to print certain values in the CLI output after running `terraform apply`.
- When using [remote state](https://developer.hashicorp.com/terraform/language/state/remote), root module outputs can be accessed by other configurations via a [`terraform_remote_state` data source](https://developer.hashicorp.com/terraform/language/state/remote-state-data).

Resource instances managed by Terraform each export attributes whose values can be used elsewhere in configuration. Output values are a way to expose some of that information to the user of your module.

**Note:** For brevity, output values are often referred to as just "outputs" when the meaning is clear from context.

## [](https://developer.hashicorp.com/terraform/language/values/outputs#declaring-an-output-value)Declaring an Output Value

Each output value exported by a module must be declared using an `output` block:

```
output "instance_ip_addr" {
  value = aws_instance.server.private_ip
}
```

The label immediately after the `output` keyword is the name, which must be a valid [identifier](https://developer.hashicorp.com/terraform/language/syntax/configuration#identifiers). In a root module, this name is displayed to the user; in a child module, it can be used to access the output's value.

The `value` argument takes an [expression](https://developer.hashicorp.com/terraform/language/expressions) whose result is to be returned to the user. In this example, the expression refers to the `private_ip` attribute exposed by an `aws_instance` resource defined elsewhere in this module (not shown). Any valid expression is allowed as an output value.

**Note:** Outputs are only rendered when Terraform applies your plan. Running `terraform plan` will not render outputs.

## [](https://developer.hashicorp.com/terraform/language/values/outputs#accessing-child-module-outputs)Accessing Child Module Outputs

In a parent module, outputs of child modules are available in expressions as `module.<MODULE NAME>.<OUTPUT NAME>`. For example, if a child module named `web_server` declared an output named `instance_ip_addr`, you could access that value as `module.web_server.instance_ip_addr`.

## [](https://developer.hashicorp.com/terraform/language/values/outputs#custom-condition-checks)Custom Condition Checks

You can use `precondition` blocks to specify guarantees about output data. The following examples creates a precondition that checks whether the EC2 instance has an encrypted root volume.

```
output "api_base_url" {
  value = "https://${aws_instance.example.private_dns}:8433/"

  # The EC2 instance must have an encrypted root volume.
  precondition {
    condition     = data.aws_ebs_volume.example.encrypted
    error_message = "The server's root volume is not encrypted."
  }
}
```

Custom conditions can help capture assumptions, helping future maintainers understand the configuration design and intent. They also return useful information about errors earlier and in context, helping consumers more easily diagnose issues in their configurations.

Refer to [Custom Condition Checks](https://developer.hashicorp.com/terraform/language/expressions/custom-conditions#preconditions-and-postconditions) for more details.

## [](https://developer.hashicorp.com/terraform/language/values/outputs#optional-arguments)Optional Arguments

`output` blocks can optionally include `description`, `sensitive`, `ephemeral`, and `depends_on` arguments, which are described in the following sections.

[](https://developer.hashicorp.com/terraform/language/values/outputs#)

### [](https://developer.hashicorp.com/terraform/language/values/outputs#description-output-value-documentation)`description` — Output Value Documentation

Because the output values of a module are part of its user interface, you can briefly describe the purpose of each value using the optional `description` argument:

```
output "instance_ip_addr" {
  value       = aws_instance.server.private_ip
  description = "The private IP address of the main server instance."
}
```

The description should concisely explain the purpose of the output and what kind of value is expected. This description string might be included in documentation about the module, and so it should be written from the perspective of the user of the module rather than its maintainer. For commentary for module maintainers, use comments.

[](https://developer.hashicorp.com/terraform/language/values/outputs#)

### [](https://developer.hashicorp.com/terraform/language/values/outputs#ephemeral-avoid-storing-values-in-state-or-plan-files)`ephemeral` — Avoid storing values in state or plan files

**Note**: Ephemeral outputs are available in Terraform v1.10 and later.

You can mark `output` values as `ephemeral` in child modules to pass ephemeral values between modules while avoiding persisting those values to state or plan files. This is useful for managing credentials, tokens, or other temporary resources you do not want to store in Terraform state files.

You can mark an `output` in a child module as ephemeral by setting the `ephemeral` attribute to `true`:

```
# modules/db/main.tf

output "secret_id" {
  value       = aws_secretsmanager_secret.secret_id
  description = "Temporary secret ID for accessing database in AWS."
  ephemeral   = true
}
```

Terraform has access to the value of `output` blocks during plan and apply operations. At the end of a plan or apply operation, Terraform does not persist the value of any ephemeral outputs.

You can only reference ephemeral outputs in specific contexts or Terraform throws an error. The following are valid contexts for referencing ephemeral outputs:

- In a [write-only argument](https://developer.hashicorp.com/terraform/language/resources/ephemeral/write-only)
- In another child module's ephemeral `output` block
- In [ephemeral variables](https://developer.hashicorp.com/terraform/language/values/variables#exclude-values-from-state)
- In [ephemeral resources](https://developer.hashicorp.com/terraform/language/resources/ephemeral)

Note that you cannot set an `output` value as `ephemeral` in the root module.

[](https://developer.hashicorp.com/terraform/language/values/outputs#)

### [](https://developer.hashicorp.com/terraform/language/values/outputs#sensitive-suppressing-values-in-cli-output)`sensitive` — Suppressing Values in CLI Output

An output can be marked as containing sensitive material using the optional `sensitive` argument:

```
output "db_password" {
  value       = aws_db_instance.db.password
  description = "The password for logging in to the database."
  sensitive   = true
}
```

Terraform will hide values marked as sensitive in the messages from `terraform plan` and `terraform apply`. In the following scenario, our root module has an output declared as sensitive and a module call with a sensitive output, which we then use in a resource attribute.

```
# main.tf

module "foo" {
  source = "./mod"
}

resource "test_instance" "x" {
  some_attribute = module.foo.a # resource attribute references a sensitive output
}

output "out" {
  value     = "xyz"
  sensitive = true
}

# mod/main.tf, our module containing a sensitive output

output "a" {
  value     = "secret"
  sensitive = true
}
```

When we run a plan or apply, the sensitive value is redacted from output:

```
Terraform will perform the following actions:
 
  # test_instance.x will be created
  + resource "test_instance" "x" {
      + some_attribute    = (sensitive value)
    }
 
Plan: 1 to add, 0 to change, 0 to destroy.
 
Changes to Outputs:
  + out = (sensitive value)
```

Terraform will still record sensitive values in the [state](https://developer.hashicorp.com/terraform/language/state), and so anyone who can access the state data will have access to the sensitive values in cleartext. For more information, see [Sensitive Data in State](https://developer.hashicorp.com/terraform/language/state/sensitive-data).

[](https://developer.hashicorp.com/terraform/language/values/outputs#)

### [](https://developer.hashicorp.com/terraform/language/values/outputs#depends_on-explicit-output-dependencies)`depends_on` — Explicit Output Dependencies

Since output values are just a means for passing data out of a module, it is usually not necessary to worry about their relationships with other nodes in the dependency graph.

However, when a parent module accesses an output value exported by one of its child modules, the dependencies of that output value allow Terraform to correctly determine the dependencies between resources defined in different modules.

Just as with [resource dependencies](https://developer.hashicorp.com/terraform/language/resources/behavior#resource-dependencies), Terraform analyzes the `value` expression for an output value and automatically determines a set of dependencies, but in less-common cases there are dependencies that cannot be recognized implicitly. In these rare cases, the `depends_on` argument can be used to create additional explicit dependencies:

```
output "instance_ip_addr" {
  value       = aws_instance.server.private_ip
  description = "The private IP address of the main server instance."

  depends_on = [
    # Security group rule must be created before this IP address could
    # actually be used, otherwise the services will be unreachable.
    aws_security_group_rule.local_access,
  ]
}
```

The `depends_on` argument should be used only as a last resort. When using it, always include a comment explaining why it is being used, to help future maintainers understand the purpose of the additional dependency.

### 8b       Describe secure secret injection best practice

# Vault Provider

The Vault provider allows Terraform to read from, write to, and configure [HashiCorp Vault](https://developer.hashicorp.com/vault).

Important

Interacting with Vault from Terraform causes any secrets that you read and write to be persisted in both Terraform's state file _and_ in any generated plan files. For any Terraform module that reads or writes Vault secrets, these files should be treated as sensitive and protected accordingly.

This provider serves two pretty-distinct use-cases, which each have their own security trade-offs and caveats that are covered in the sections that follow. Consider these carefully before using this provider within your Terraform configuration.

Note

Visit the [Inject secrets into Terraform using the Vault provider](https://learn.hashicorp.com/tutorials/terraform/secrets-vault?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS) Learn tutorial to learn how to use short-lived credentials from Vault's AWS Secrets Engine to authenticate the AWS provider.

### 8c       Understand the use of collection and structural types

## Complex Types

A _complex_ type is a type that groups multiple values into a single value. Complex types are represented by type constructors, but several of them also have shorthand keyword versions.

There are two categories of complex types: collection types (for grouping similar values), and structural types (for grouping potentially dissimilar values).

### [](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#collection-types)Collection Types

A _collection_ type allows multiple values of _one_ other type to be grouped together as a single value. The type of value _within_ a collection is called its _element type._ All collection types must have an element type, which is provided as the argument to their constructor.

For example, the type `list(string)` means "list of strings", which is a different type than `list(number)`, a list of numbers. All elements of a collection must always be of the same type.

The three kinds of collection type in the Terraform language are:

- [](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#)
    
    [`list(...)`](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#list): a sequence of values identified by consecutive whole numbers starting with zero.
    
    The keyword `list` is a shorthand for `list(any)`, which accepts any element type as long as every element is the same type. This is for compatibility with older configurations; for new code, we recommend using the full form.
    
- [](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#)
    
    [`map(...)`](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#map): a collection of values where each is identified by a string label.
    
    The keyword `map` is a shorthand for `map(any)`, which accepts any element type as long as every element is the same type. This is for compatibility with older configurations; for new code, we recommend using the full form.
    
    You can use the following characters to define maps:
    
    ```
    - `{}` 
    - `:` 
    - `=` 
    ```
    
    For example, `{ "foo": "bar", "bar": "baz" }` and `{ foo = "bar", bar = "baz" }` define the same map. You must place map keys in quotation marks when a key starts with a number, contains spaces, or contains special characters. Otherwise, you can omit them. You must place commas between keys-value pairs in single-line maps. You can place key-value pairs in multi-line maps on new lines.
    
    **Note:** Although colons are valid delimiters between keys and values, `terraform fmt` ignores them. In contrast, `terraform fmt` attempts to vertically align equals signs.
    
- [](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#)
    
    [`set(...)`](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#set): a collection of unique values that do not have any secondary identifiers or ordering.
    

### [](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#structural-types)Structural Types

A _structural_ type allows multiple values of _several distinct types_ to be grouped together as a single value. Structural types require a _schema_ as an argument, to specify which types are allowed for which elements.

The two kinds of structural type in the Terraform language are:

- [](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#)
    
    [`object(...)`](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#object): a collection of named attributes that each have their own type.
    
    The schema for object types is `{ <KEY> = <TYPE>, <KEY> = <TYPE>, ... }` — a pair of curly braces containing a comma-separated series of `<KEY> = <TYPE>` pairs. Values that match the object type must contain _all_ of the specified keys, and the value for each key must match its specified type. (Values with _additional_ keys can still match an object type, but the extra attributes are discarded during type conversion.)
    
- [](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#)
    
    [`tuple(...)`](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#tuple): a sequence of elements identified by consecutive whole numbers starting with zero, where each element has its own type.
    
    The schema for tuple types is `[<TYPE>, <TYPE>, ...]` — a pair of square brackets containing a comma-separated series of types. Values that match the tuple type must have _exactly_ the same number of elements (no more and no fewer), and the value in each position must match the specified type for that position.
    

For example: an object type of `object({ name=string, age=number })` would match a value like the following:

```
{
  name = "John"
  age  = 52
}
```

Also, an object type of `object({ id=string, cidr_block=string })` would match the object produced by a reference to an `aws_vpc` resource, like `aws_vpc.example_vpc`; although the resource has additional attributes, they would be discarded during type conversion.

Finally, a tuple type of `tuple([string, number, bool])` would match a value like the following:

```
["a", 15, true]
```

### [](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#complex-type-literals)Complex Type Literals

The Terraform language has literal expressions for creating tuple and object values, which are described in [Expressions: Literal Expressions](https://developer.hashicorp.com/terraform/language/expressions/types#literal-expressions) as "list/tuple" literals and "map/object" literals, respectively.

Terraform does _not_ provide any way to directly represent lists, maps, or sets. However, due to the automatic conversion of complex types (described below), the difference between similar complex types is almost never relevant to a normal user, and most of the Terraform documentation conflates lists with tuples and maps with objects. The distinctions are only useful when restricting input values for a module or resource.

### [](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#conversion-of-complex-types)Conversion of Complex Types

Similar kinds of complex types (list/tuple/set and map/object) can usually be used interchangeably within the Terraform language, and most of Terraform's documentation glosses over the differences between the kinds of complex type. This is due to two conversion behaviors:

- Whenever possible, Terraform converts values between similar kinds of complex types if the provided value is not the exact type requested. "Similar kinds" is defined as follows:
    - Objects and maps are similar.
        - A map (or a larger object) can be converted to an object if it has _at least_ the keys required by the object schema. Any additional attributes are discarded during conversion, which means map -> object -> map conversions can be lossy.
    - Tuples and lists are similar.
        - A list can only be converted to a tuple if it has _exactly_ the required number of elements.
    - Sets are _almost_ similar to both tuples and lists:
        - When a list or tuple is converted to a set, duplicate values are discarded and the ordering of elements is lost.
        - When a `set` is converted to a list or tuple, the elements will be in an arbitrary order. If the set's elements were strings, they will be in lexicographical order; sets of other element types do not guarantee any particular order of elements.
- Whenever possible, Terraform converts _element values_ within a complex type, either by converting complex-typed elements recursively or as described above in [Conversion of Primitive Types](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#conversion-of-primitive-types).

For example: if a module argument requires a value of type `list(string)` and a user provides the tuple `["a", 15, true]`, Terraform will internally transform the value to `["a", "15", "true"]` by converting the elements to the required `string` element type. Later, if the module uses those elements to set different resource arguments that require a string, a number, and a bool (respectively), Terraform will automatically convert the second and third strings back to the required types at that time, since they contain valid representations of a number and a bool.

On the other hand, automatic conversion will fail if the provided value (including any of its element values) is incompatible with the required type. If an argument requires a type of `map(string)` and a user provides the object `{name = ["Kristy", "Claudia", "Mary Anne", "Stacey"], age = 12}`, Terraform will raise a type mismatch error, since a tuple cannot be converted to a string.

## [](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#dynamic-types-the-any-constraint)Dynamic Types: The "any" Constraint

**Warning:** `any` is very rarely the correct type constraint to use. **Do not use `any` just to avoid specifying a type constraint**. Always write an exact type constraint unless you are truly handling dynamic data.

The keyword `any` is a special construct that serves as a placeholder for a type yet to be decided. `any` is not _itself_ a type: when interpreting a value against a type constraint containing `any`, Terraform will attempt to find a single actual type that could replace the `any` keyword to produce a valid result.

The only situation where it's appropriate to use `any` is if you will pass the given value directly to some other system without directly accessing its contents. For example, it's okay to use a variable of type `any` if you use it only with `jsonencode` to pass the full value directly to a resource, as shown in the following example:

```
variable "settings" {
  type = any
}

resource "aws_s3_object" "example" {
  # ...

  # This is a reasonable use of "any" because this module
  # just writes any given data to S3 as JSON, without
  # inspecting it further or applying any constraints
  # to its type or value.
  content = jsonencode(var.settings)
}
```

If any part of your module accesses elements or attributes of the value, or expects it to be a string or number, or any other non-opaque treatment, it is _incorrect_ to use `any`. Write the exact type that your module is expecting instead.

### [](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#any-with-collection-types)`any` with Collection Types

All of the elements of a collection must have the same type, so if you use `any` as the placeholder for the element type of a collection then Terraform will attempt to find a single exact element type to use for the resulting collection.

For example, given the type constraint `list(any)`, Terraform will examine the given value and try to choose a replacement for the `any` that would make the result valid.

If the given value were `["a", "b", "c"]` -- whose physical type is `tuple([string, string, string])` -- Terraform analyzes this as follows:

- Tuple types and list types are _similar_ per the previous section, so the tuple-to-list conversion rule applies.
- All of the elements in the tuple are strings, so the type constraint `string` would be valid for all of the list elements.
- Therefore in this case the `any` argument is replaced with `string`, and the final concrete value type is `list(string)`.

If the elements of the given tuple are not all of the same type then Terraform will attempt to find a single type that they can all convert to. Terraform will consider various conversion rules as described in earlier sections.

- If the given value were instead `["a", 1, "b"]` then Terraform would still select `list(string)`, because of the primitive type conversion rules, and the resulting value would be `["a", "1", "b"]` due to the string conversion implied by that type constraint.
- If the given value were instead `["a", [], "b"]` then the value cannot conform to the type constraint: there is no single type that both a string and an empty tuple can convert to. Terraform would reject this value, complaining that all elements must have the same type.

Although the above examples use `list(any)`, a similar principle applies to `map(any)` and `set(any)`.

## [](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#optional-object-type-attributes)Optional Object Type Attributes

Terraform typically returns an error when it does not receive a value for specified object attributes. When you mark an attribute as optional, Terraform instead inserts a default value for the missing attribute. This allows the receiving module to describe an appropriate fallback behavior.

To mark attributes as optional, use the `optional` modifier in the object type constraint. The following example creates optional attribute `b` and optional attribute with a default value `c`.

```
variable "with_optional_attribute" {
  type = object({
    a = string                # a required attribute
    b = optional(string)      # an optional attribute
    c = optional(number, 127) # an optional attribute with default value
  })
}
```

The `optional` modifier takes one or two arguments.

- **Type:** (Required) The first argument specifies the type of the attribute.
- **Default:** (Optional) The second argument defines the default value that Terraform should use if the attribute is not present. This must be compatible with the attribute type. If not specified, Terraform uses a `null` value of the appropriate type as the default.

An optional attribute with a non-`null` default value is guaranteed to never have the value `null` within the receiving module. Terraform will substitute the default value both when a caller omits the attribute altogether and when a caller explicitly sets it to `null`, thereby avoiding the need for additional checks to handle a possible null value.

Terraform applies object attribute defaults top-down in nested variable types. This means that Terraform applies the default value you specify in the `optional` modifier first and then later applies any nested default values to that attribute.

### [](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#example-nested-structures-with-optional-attributes-and-defaults)Example: Nested Structures with Optional Attributes and Defaults

The following example defines a variable for storage buckets that host a website. This variable type uses several optional attributes, including `website`, which is itself an optional `object` type that has optional attributes and defaults.

```
variable "buckets" {
  type = list(object({
    name    = string
    enabled = optional(bool, true)
    website = optional(object({
      index_document = optional(string, "index.html")
      error_document = optional(string, "error.html")
      routing_rules  = optional(string)
    }), {})
  }))
}
```

The following example `terraform.tfvars` file specifies three bucket configurations for `var.buckets`.

- [](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#)[`production`](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#production) sets the routing rules to add a redirect
- [](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#)[`archived`](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#archived) uses default configuration, but is disabled
- [](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#)[`docs`](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#docs) overrides the index and error documents to use text files

The `production` bucket does not specify the index and error documents, and the `archived` bucket omits the website configuration entirely. Terraform will use the default values specified in the `bucket` type constraint.

```
buckets = [
  {
    name = "production"
    website = {
      routing_rules = <<-EOT
      [
        {
          "Condition" = { "KeyPrefixEquals": "img/" },
          "Redirect"  = { "ReplaceKeyPrefixWith": "images/" }
        }
      ]
      EOT
    }
  },
  {
    name = "archived"
    enabled = false
  },
  {
    name = "docs"
    website = {
      index_document = "index.txt"
      error_document = "error.txt"
    }
  },
]
```

This configuration produces the following variable values.

- For the `production` and `docs` buckets, Terraform sets `enabled` to `true`. Terraform also supplies default values for `website`, and then the values specified in `docs` override those defaults.
- For the `archived` and `docs` buckets, Terraform sets `routing_rules` to a `null` value. When Terraform does not receive optional attributes and there are no specified defaults, Terraform populates those attributes with a `null` value.
- For the `archived` bucket, Terraform populates the `website` attribute with the default values specified in the `buckets` type constraint.

```
tolist([
  {
    "enabled" = true
    "name" = "production"
    "website" = {
      "error_document" = "error.html"
      "index_document" = "index.html"
      "routing_rules" = <<-EOT
      [
        {
          "Condition" = { "KeyPrefixEquals": "img/" },
          "Redirect"  = { "ReplaceKeyPrefixWith": "images/" }
        }
      ]

      EOT
    }
  },
  {
    "enabled" = false
    "name" = "archived"
    "website" = {
      "error_document" = "error.html"
      "index_document" = "index.html"
      "routing_rules" = tostring(null)
    }
  },
  {
    "enabled" = true
    "name" = "docs"
    "website" = {
      "error_document" = "error.txt"
      "index_document" = "index.txt"
      "routing_rules" = tostring(null)
    }
  },
])
```

### [](https://developer.hashicorp.com/terraform/language/expressions/type-constraints#example-conditionally-setting-an-optional-attribute)Example: Conditionally setting an optional attribute

Sometimes the decision about whether or not to set a value for an optional argument needs to be made dynamically based on some other data. In that case, the calling `module` block can use a conditional expression with `null` as one of its result arms to represent dynamically leaving the argument unset.

With the `variable "buckets"` declaration shown in the previous section, the following example conditionally overrides the `index_document` and `error_document` settings in the `website` object based on a new variable `var.legacy_filenames`:

```
variable "legacy_filenames" {
  type     = bool
  default  = false
  nullable = false
}

module "buckets" {
  source = "./modules/buckets"

  buckets = [
    {
      name = "maybe_legacy"
      website = {
        error_document = var.legacy_filenames ? "ERROR.HTM" : null
        index_document = var.legacy_filenames ? "INDEX.HTM" : null
      }
    },
  ]
}
```

When `var.legacy_filenames` is set to `true`, the call will override the document filenames. When it is `false`, the call will leave the two filenames unspecified, thereby allowing the module to use its specified default values.

### 8d       Create and differentiate resource and data configuration

# Resources

> **Hands-on:** Try the [Terraform: Get Started](https://developer.hashicorp.com/terraform/tutorials/aws-get-started?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS) tutorials.

_Resources_ are the most important element in the Terraform language. Each resource block describes one or more infrastructure objects, such as virtual networks, compute instances, or higher-level components such as DNS records.

- [Resource Blocks](https://developer.hashicorp.com/terraform/language/resources/syntax) documents the syntax for declaring resources.
    
- [Resource Behavior](https://developer.hashicorp.com/terraform/language/resources/behavior) explains in more detail how Terraform handles resource declarations when applying a configuration.
    
- The Meta-Arguments section documents special arguments that can be used with every resource type, including [`depends_on`](https://developer.hashicorp.com/terraform/language/meta-arguments/depends_on), [`count`](https://developer.hashicorp.com/terraform/language/meta-arguments/count), [`for_each`](https://developer.hashicorp.com/terraform/language/meta-arguments/for_each), [`provider`](https://developer.hashicorp.com/terraform/language/meta-arguments/resource-provider), and [`lifecycle`](https://developer.hashicorp.com/terraform/language/meta-arguments/lifecycle).
    
- [Provisioners](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax) documents configuring post-creation actions for a resource using the `provisioner` and `connection` blocks. Since provisioners are non-declarative and potentially unpredictable, we strongly recommend that you treat them as a last resort.

# Data Sources

_Data sources_ allow Terraform to use information defined outside of Terraform, defined by another separate Terraform configuration, or modified by functions.

> **Hands-on:** Try the [Query Data Sources](https://developer.hashicorp.com/terraform/tutorials/configuration-language/data-sources) tutorial.

Each [provider](https://developer.hashicorp.com/terraform/language/providers) may offer data sources alongside its set of [resource](https://developer.hashicorp.com/terraform/language/resources) types.

## [](https://developer.hashicorp.com/terraform/language/data-sources#using-data-sources)Using Data Sources

A data source is accessed via a special kind of resource known as a _data resource_, declared using a `data` block:

```
data "aws_ami" "example" {
  most_recent = true

  owners = ["self"]
  tags = {
    Name   = "app-server"
    Tested = "true"
  }
}
```

A `data` block requests that Terraform read from a given data source ("aws_ami") and export the result under the given local name ("example"). The name is used to refer to this resource from elsewhere in the same Terraform module, but has no significance outside of the scope of a module.

The data source and name together serve as an identifier for a given resource and so must be unique within a module.

Within the block body (between `{` and `}`) are query constraints defined by the data source. Most arguments in this section depend on the data source, and indeed in this example `most_recent`, `owners` and `tags` are all arguments defined specifically for [the `aws_ami` data source](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/ami).

When distinguishing from data resources, the primary kind of resource (as declared by a `resource` block) is known as a _managed resource_. Both kinds of resources take arguments and export attributes for use in configuration, but while managed resources cause Terraform to create, update, and delete infrastructure objects, data resources cause Terraform only to _read_ objects. For brevity, managed resources are often referred to just as "resources" when the meaning is clear from context.

## [](https://developer.hashicorp.com/terraform/language/data-sources#data-source-arguments)Data Source Arguments

Each data resource is associated with a single data source, which determines the kind of object (or objects) it reads and what query constraint arguments are available.

Each data source in turn belongs to a [provider](https://developer.hashicorp.com/terraform/language/providers), which is a plugin for Terraform that offers a collection of resource types and data sources that most often belong to a single cloud or on-premises infrastructure platform.

Most of the items within the body of a `data` block are defined by and specific to the selected data source, and these arguments can make full use of [expressions](https://developer.hashicorp.com/terraform/language/expressions) and other dynamic Terraform language features.

However, there are some "meta-arguments" that are defined by Terraform itself and apply across all data sources. These arguments often have additional restrictions on what language features can be used with them, and are described in more detail in the following sections.

## [](https://developer.hashicorp.com/terraform/language/data-sources#data-resource-behavior)Data Resource Behavior

Terraform reads data resources during the planning phase when possible, but announces in the plan when it must defer reading resources until the apply phase to preserve the order of operations. Terraform defers reading data resources in the following situations:

- At least one of the given arguments is a managed resource attribute or other value that Terraform cannot predict until the apply step.
- The data resource depends directly on a managed resource that itself has planned changes in the current plan.
- The data resource has [custom conditions](https://developer.hashicorp.com/terraform/language/data-sources#custom-condition-checks) and it depends directly or indirectly on a managed resource that itself has planned changes in the current plan.

Refer to [Data Resource Dependencies](https://developer.hashicorp.com/terraform/language/data-sources#data-resource-dependencies) for details on what it means for a data resource to depend on other objects. Any resulting attribute of such a data resource will be unknown during planning, so it cannot be used in situations where values must be fully known.

## [](https://developer.hashicorp.com/terraform/language/data-sources#local-only-data-sources)Local-only Data Sources

While many data sources correspond to an infrastructure object type that is accessed via a remote network API, some specialized data sources operate only within Terraform itself, calculating some results and exposing them for use elsewhere.

For example, local-only data sources exist for [rendering templates](https://registry.terraform.io/providers/hashicorp/template/latest/docs/data-sources/file), [reading local files](https://registry.terraform.io/providers/hashicorp/local/latest/docs/data-sources/file), and [rendering AWS IAM policies](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy_document).

The behavior of local-only data sources is the same as all other data sources, but their result data exists only temporarily during a Terraform operation, and is re-calculated each time a new plan is created.

## [](https://developer.hashicorp.com/terraform/language/data-sources#data-resource-dependencies)Data Resource Dependencies

Data resources have the same dependency resolution behavior [as defined for managed resources](https://developer.hashicorp.com/terraform/language/resources/behavior#resource-dependencies). Setting the `depends_on` meta-argument within `data` blocks defers reading of the data source until after all changes to the dependencies have been applied.

In order to ensure that data sources are accessing the most up to date information possible in a wide variety of use cases, arguments directly referencing managed resources are treated the same as if the resource was listed in `depends_on`. This behavior can be avoided when desired by indirectly referencing the managed resource values through a `local` value, unless the data resource itself has [custom conditions](https://developer.hashicorp.com/terraform/language/data-sources#custom-condition-checks).

**NOTE:** **In Terraform 0.12 and earlier**, due to the data resource behavior of deferring the read until the apply phase when depending on values that are not yet known, using `depends_on` with `data` resources will force the read to always be deferred to the apply phase, and therefore a configuration that uses `depends_on` with a `data` resource can never converge. Due to this behavior, we do not recommend using `depends_on` with data resources.

## [](https://developer.hashicorp.com/terraform/language/data-sources#custom-condition-checks)Custom Condition Checks

You can use `precondition` and `postcondition` blocks to specify assumptions and guarantees about how the data source operates. The following examples creates a postcondition that checks whether the AMI has the correct tags.

```
data "aws_ami" "example" {
  id = var.aws_ami_id

  lifecycle {
    # The AMI ID must refer to an existing AMI that has the tag "nomad-server".
    postcondition {
      condition     = self.tags["Component"] == "nomad-server"
      error_message = "tags[\"Component\"] must be \"nomad-server\"."
    }
  }
}
```

Custom conditions can help capture assumptions, helping future maintainers understand the configuration design and intent. They also return useful information about errors earlier and in context, helping consumers more easily diagnose issues in their configurations.

Refer to [Custom Condition Checks](https://developer.hashicorp.com/terraform/language/expressions/custom-conditions#preconditions-and-postconditions) for more details.

## [](https://developer.hashicorp.com/terraform/language/data-sources#multiple-resource-instances)Multiple Resource Instances

Data resources support [`count`](https://developer.hashicorp.com/terraform/language/meta-arguments/count) and [`for_each`](https://developer.hashicorp.com/terraform/language/meta-arguments/for_each) meta-arguments as defined for managed resources, with the same syntax and behavior.

As with managed resources, when `count` or `for_each` is present it is important to distinguish the resource itself from the multiple resource _instances_ it creates. Each instance will separately read from its data source with its own variant of the constraint arguments, producing an indexed result.

## [](https://developer.hashicorp.com/terraform/language/data-sources#selecting-a-non-default-provider-configuration)Selecting a Non-default Provider Configuration

Data resources support [the `provider` meta-argument](https://developer.hashicorp.com/terraform/language/meta-arguments/resource-provider) as defined for managed resources, with the same syntax and behavior.

## [](https://developer.hashicorp.com/terraform/language/data-sources#lifecycle-customizations)Lifecycle Customizations

Data resources do not have any customization settings available for their lifecycle. Only the `precondition` and `postcondition` blocks are allowed in the data resource `lifecycle` block.

Refer to [Custom Condition Checks](https://developer.hashicorp.com/terraform/language/data-sources#custom-condition-checks) for more details.

## [](https://developer.hashicorp.com/terraform/language/data-sources#example)Example

A data source configuration looks like the following:

```
# Find the latest available AMI that is tagged with Component = web
data "aws_ami" "web" {
  filter {
    name   = "state"
    values = ["available"]
  }

  filter {
    name   = "tag:Component"
    values = ["web"]
  }

  most_recent = true
}
```

## [](https://developer.hashicorp.com/terraform/language/data-sources#description)Description

The `data` block creates a data instance of the given _type_ (first block label) and _name_ (second block label). The combination of the type and name must be unique.

Within the block (the `{ }`) is configuration for the data instance. The configuration is dependent on the type; as with [resources](https://developer.hashicorp.com/terraform/language/resources), each provider on the [Terraform Registry](https://registry.terraform.io/browse/providers) has its own documentation for configuring and using the data types it provides.

Each data instance will export one or more attributes, which can be used in other resources as reference expressions of the form `data.<TYPE>.<NAME>.<ATTRIBUTE>`. For example:

```
resource "aws_instance" "web" {
  ami           = data.aws_ami.web.id
  instance_type = "t1.micro"
}
```

## [](https://developer.hashicorp.com/terraform/language/data-sources#meta-arguments)Meta-Arguments

As data sources are essentially a read only subset of resources, they also support the same [meta-arguments](https://developer.hashicorp.com/terraform/language/resources/syntax#meta-arguments) of resources with the exception of the [`lifecycle` configuration block](https://developer.hashicorp.com/terraform/language/meta-arguments/lifecycle).

### [](https://developer.hashicorp.com/terraform/language/data-sources#non-default-provider-configurations)Non-Default Provider Configurations

Similarly to [resources](https://developer.hashicorp.com/terraform/language/resources), when a module has multiple configurations for the same provider you can specify which configuration to use with the `provider` meta-argument:

```
data "aws_ami" "web" {
  provider = aws.west

  # ...
}
```

See [The Resource `provider` Meta-Argument](https://developer.hashicorp.com/terraform/language/meta-arguments/resource-provider) for more information.

## [](https://developer.hashicorp.com/terraform/language/data-sources#data-source-lifecycle)Data Source Lifecycle

If the arguments of a data instance contain no references to computed values, such as attributes of resources that have not yet been created, then the data instance will be read and its state updated during Terraform's "refresh" phase, which by default runs prior to creating a plan. This ensures that the retrieved data is available for use during planning and the diff will show the real values obtained.

Data instance arguments may refer to computed values, in which case the attributes of the instance itself cannot be resolved until all of its arguments are defined. In this case, refreshing the data instance will be deferred until the "apply" phase, and all interpolations of the data instance attributes will show as "computed" in the plan since the values are not yet known.

### 8e       Use resource addressing and resource parameters to connect resources together

# Resource Address Reference

This topic provides reference information about resource addresses in Terraform.

## [](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#syntax)Syntax

A _resource address_ is a string that identifies zero or more resource instances in your overall configuration.

An address is made up of two parts:

```
[module path][resource spec]
```

In some contexts Terraform might allow for an incomplete resource address that only refers to a module as a whole, or that omits the index for a multi-instance resource. In those cases, the meaning depends on the context, so you'll need to refer to the documentation for the specific feature you are using which parses resource addresses.

## [](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#module-path)Module path

A module path addresses a module within the tree of modules. It takes the form:

```
module.module_name[module index]
```

- [](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#)[`module`](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#module) - Module keyword indicating a child module (non-root). Multiple `module` keywords in a path indicate nesting.
- [](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#)[`module_name`](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#module_name) - User-defined name of the module.
- [](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#)[`[module index]`](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#module-index) - (Optional) [Index](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#index-values-for-modules-and-resources) to select an instance from a module call that has multiple instances, surrounded by square bracket characters (`[` and `]`).

An address without a resource spec, i.e. `module.foo` applies to every resource within the module if a single module, or all instances of a module if a module has multiple instances. To address all resources of a particular module instance, include the module index in the address, such as `module.foo[0]`.

If the module path is omitted, the address applies to the root module.

An example of the `module` keyword delineating between two modules that have multiple instances:

```
module.foo[0].module.bar["a"]
```

Module index only applies to modules in Terraform v0.13 or later. In earlier versions of Terraform, a module could not have multiple instances.

## [](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#resource-spec)Resource spec

A resource spec addresses a specific resource instance in the selected module. It has the following syntax:

```
resource_type.resource_name[instance index]
```

- [](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#)[`resource_type`](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#resource_type) - Type of the resource being addressed.
- [](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#)[`resource_name`](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#resource_name) - User-defined name of the resource.
- [](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#)[`[instance index]`](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#instance-index) - (Optional) [Index](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#index-values-for-modules-and-resources) to select an instance from a resource that has multiple instances, surrounded by square bracket characters (`[` and `]`).

In Terraform v0.12 and later, a resource spec without a module path prefix matches only resources in the root module. In earlier versions, a resource spec without a module path prefix would match resources with the same type and name in any descendant module.

## [](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#index-values-for-modules-and-resources)Index values for Modules and Resources

The following specifications apply to index values on modules and resources with multiple instances:

- [](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#)[`[N]`](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#n) where `N` is a `0`-based numerical index into a resource with multiple instances specified by the `count` meta-argument. Omitting an index when addressing a resource where `count > 1` means that the address references all instances.
- [](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#)[`["INDEX"]`](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#index) where `INDEX` is a alphanumerical key index into a resource with multiple instances specified by the `for_each` meta-argument.

## [](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#examples)Examples

### [](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#count-example)count Example

Given a Terraform config that includes:

```
resource "aws_instance" "web" {
  # ...
  count = 4
}
```

An address like this:

```
aws_instance.web[3]
```

Refers to only the last instance in the config, and an address like this:

```
aws_instance.web
```

Refers to all four "web" instances.

### [](https://developer.hashicorp.com/terraform/cli/state/resource-addressing#for_each-example)for_each Example

Given a Terraform config that includes:

```
resource "aws_instance" "web" {
  # ...
  for_each = tomap({
    "terraform": "value1",
    "resource":  "value2",
    "indexing":  "value3",
    "example":   "value4",
  })
}
```

An address like this:

```
aws_instance.web["example"]
```

Refers to only the "example" instance in the config, and resolves to "value4".



# References to Named Values

> **Hands-on:** Try the [Create Dynamic Expressions](https://developer.hashicorp.com/terraform/tutorials/configuration-language/expressions?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS) tutorial.

Terraform makes several kinds of named values available. Each of these names is an expression that references the associated value. You can use them as standalone expressions, or combine them with other expressions to compute new values.

## [](https://developer.hashicorp.com/terraform/language/expressions/references#types-of-named-values)Types of Named Values

The main kinds of named values available in Terraform are:

- Resources
- Input variables
- Local values
- Child module outputs
- Data sources
- Filesystem and workspace info
- Block-local values

The sections below explain each kind of named value in detail.

Although many of these names use dot-separated paths that resemble [attribute notation](https://developer.hashicorp.com/terraform/language/expressions/types#indices-and-attributes) for elements of object values, they are not implemented as real objects. This means you must use them exactly as written: you cannot use square-bracket notation to replace the dot-separated paths, and you cannot iterate over the "parent object" of a named entity; for example, you cannot use `aws_instance` in a `for` expression to iterate over every AWS instance resource.

### [](https://developer.hashicorp.com/terraform/language/expressions/references#resources)Resources

`<RESOURCE TYPE>.<NAME>` represents a [managed resource](https://developer.hashicorp.com/terraform/language/resources) of the given type and name.

The value of a resource reference can vary, depending on whether the resource uses `count` or `for_each`:

- If the resource doesn't use `count` or `for_each`, the reference's value is an object. The resource's attributes are elements of the object, and you can access them using [dot or square bracket notation](https://developer.hashicorp.com/terraform/language/expressions/types#indices-and-attributes).
- If the resource has the `count` argument set, the reference's value is a _list_ of objects representing its instances.
- If the resource has the `for_each` argument set, the reference's value is a _map_ of objects representing its instances.

Any named value that does not match another pattern listed below will be interpreted by Terraform as a reference to a managed resource.

For more information about how to use resource references, see [references to resource attributes](https://developer.hashicorp.com/terraform/language/expressions/references#references-to-resource-attributes) below.

### [](https://developer.hashicorp.com/terraform/language/expressions/references#input-variables)Input Variables

`var.<NAME>` is the value of the [input variable](https://developer.hashicorp.com/terraform/language/values/variables) of the given name.

If the variable has a type constraint (`type` argument) as part of its declaration, Terraform will automatically convert the caller's given value to conform to the type constraint.

For that reason, you can safely assume that a reference using `var.` will always produce a value that conforms to the type constraint, even if the caller provided a value of a different type that was automatically converted.

In particular, note that if you define a variable as being of an object type with particular attributes then only _those specific attributes_ will be available in expressions elsewhere in the module, even if the caller actually passed in a value with additional attributes. You must define in the type constraint all of the attributes you intend to use elsewhere in your module.

### [](https://developer.hashicorp.com/terraform/language/expressions/references#local-values)Local Values

`local.<NAME>` is the value of the [local value](https://developer.hashicorp.com/terraform/language/values/locals) of the given name.

Local values can refer to other local values, even within the same `locals` block, as long as you don't introduce circular dependencies.

### [](https://developer.hashicorp.com/terraform/language/expressions/references#child-module-outputs)Child Module Outputs

`module.<MODULE NAME>` is an value representing the results of [a `module` block](https://developer.hashicorp.com/terraform/language/modules/syntax).

If the corresponding `module` block does not have either `count` nor `for_each` set then the value will be an object with one attribute for each output value defined in the child module. To access one of the module's [output values](https://developer.hashicorp.com/terraform/language/values/outputs), use `module.<MODULE NAME>.<OUTPUT NAME>`.

If the corresponding `module` uses `for_each` then the value will be a map of objects whose keys correspond with the keys in the `for_each` expression, and whose values are each objects with one attribute for each output value defined in the child module, each representing one module instance.

If the corresponding module uses `count` then the result is similar to for `for_each` except that the value is a _list_ with the requested number of elements, each one representing one module instance.

### [](https://developer.hashicorp.com/terraform/language/expressions/references#data-sources)Data Sources

`data.<DATA TYPE>.<NAME>` is an object representing a [data resource](https://developer.hashicorp.com/terraform/language/data-sources) of the given data source type and name. If the resource has the `count` argument set, the value is a list of objects representing its instances. If the resource has the `for_each` argument set, the value is a map of objects representing its instances.

For more information, see [References to Resource Attributes](https://developer.hashicorp.com/terraform/language/expressions/references#references-to-resource-attributes), which also applies to data resources aside from the addition of the `data.` prefix to mark the reference as for a data resource.

### [](https://developer.hashicorp.com/terraform/language/expressions/references#filesystem-and-workspace-info)Filesystem and Workspace Info

The following values are available:

- [](https://developer.hashicorp.com/terraform/language/expressions/references#)[`path.module`](https://developer.hashicorp.com/terraform/language/expressions/references#path-module) is the filesystem path of the module where the expression is placed. We do not recommend using `path.module` in write operations because it can produce different behavior depending on whether you use remote or local module sources. Multiple invocations of local modules use the same source directory, overwriting the data in `path.module` during each call. This can lead to race conditions and unexpected results.
- [](https://developer.hashicorp.com/terraform/language/expressions/references#)[`path.root`](https://developer.hashicorp.com/terraform/language/expressions/references#path-root) is the filesystem path of the root module of the configuration.
- [](https://developer.hashicorp.com/terraform/language/expressions/references#)[`path.cwd`](https://developer.hashicorp.com/terraform/language/expressions/references#path-cwd) is the filesystem path of the original working directory from where you ran Terraform before applying any `-chdir` argument. This path is an absolute path that includes details about the filesystem structure. It is also useful in some advanced cases where Terraform is run from a directory other than the root module directory. We recommend using `path.root` or `path.module` over `path.cwd` where possible.
- [](https://developer.hashicorp.com/terraform/language/expressions/references#)[`terraform.workspace`](https://developer.hashicorp.com/terraform/language/expressions/references#terraform-workspace) is the name of the currently selected [workspace](https://developer.hashicorp.com/terraform/language/state/workspaces).

Use the values in this section carefully, because they include information about the context in which a configuration is being applied and so may inadvertently hurt the portability or composability of a module.

For example, if you use `path.cwd` directly to populate a path into a resource argument then later applying the same configuration from a different directory or on a different computer with a different directory structure will cause the provider to consider the change of path to be a change to be applied, even if the path still refers to the same file.

Similarly, if you use any of these values as a form of namespacing in a shared module, such as using `terraform.workspace` as a prefix for globally-unique object names, it may not be possible to call your module more than once in the same configuration.

Aside from `path.module`, we recommend using the values in this section only in the root module of your configuration. If you are writing a shared module which needs a prefix to help create unique names, define an input variable for your module and allow the calling module to define the prefix. The calling module can then use `terraform.workspace` to define it if appropriate, or some other value if not:

```
module "example" {
  # ...

  name_prefix = "app-${terraform.workspace}"
}
```

### [](https://developer.hashicorp.com/terraform/language/expressions/references#block-local-values)Block-Local Values

Within the bodies of certain blocks, or in some other specific contexts, there are other named values available beyond the global values listed above. These local names are described in the documentation for the specific contexts where they appear. Some of most common local names are:

- [](https://developer.hashicorp.com/terraform/language/expressions/references#)[`count.index`](https://developer.hashicorp.com/terraform/language/expressions/references#count-index), in resources that use [the `count` meta-argument](https://developer.hashicorp.com/terraform/language/meta-arguments/count).
- [](https://developer.hashicorp.com/terraform/language/expressions/references#)[`each.key`](https://developer.hashicorp.com/terraform/language/expressions/references#each-key) / `each.value`, in resources that use [the `for_each` meta-argument](https://developer.hashicorp.com/terraform/language/meta-arguments/for_each).
- [](https://developer.hashicorp.com/terraform/language/expressions/references#)[`self`](https://developer.hashicorp.com/terraform/language/expressions/references#self), in [provisioner](https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax) and [connection](https://developer.hashicorp.com/terraform/language/resources/provisioners/connection) blocks.

**Note:** Local names are often referred to as _variables_ or _temporary variables_ in their documentation. These are not [input variables](https://developer.hashicorp.com/terraform/language/values/variables); they are just arbitrary names that temporarily represent a value.

The names in this section relate to top-level configuration blocks only. If you use [`dynamic` blocks](https://developer.hashicorp.com/terraform/language/expressions/dynamic-blocks) to dynamically generate resource-type-specific _nested_ blocks within `resource` and `data` blocks then you'll refer to the key and value of each element differently. See the `dynamic` blocks documentation for details.

## [](https://developer.hashicorp.com/terraform/language/expressions/references#named-values-and-dependencies)Named Values and Dependencies

Constructs like resources and module calls often use references to named values in their block bodies, and Terraform analyzes these expressions to automatically infer dependencies between objects. For example, an expression in a resource argument that refers to another managed resource creates an implicit dependency between the two resources.

## [](https://developer.hashicorp.com/terraform/language/expressions/references#references-to-resource-attributes)References to Resource Attributes

The most common reference type is a reference to an attribute of a resource which has been declared either with a `resource` or `data` block. Because the contents of such blocks can be quite complicated themselves, expressions referring to these contents can also be complicated.

Consider the following example resource block:

```
resource "aws_instance" "example" {
  ami           = "ami-abc123"
  instance_type = "t2.micro"

  ebs_block_device {
    device_name = "sda2"
    volume_size = 16
  }
  ebs_block_device {
    device_name = "sda3"
    volume_size = 20
  }
}
```

The documentation for [`aws_instance`](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance) lists all of the arguments and nested blocks supported for this resource type, and also lists a number of attributes that are _exported_ by this resource type. All of these different resource type schema constructs are available for use in references, as follows:

- The `ami` argument set in the configuration can be used elsewhere with the reference expression `aws_instance.example.ami`.
    
- The `id` attribute exported by this resource type can be read using the same syntax, giving `aws_instance.example.id`.
    
- The arguments of the `ebs_block_device` nested blocks can be accessed using a [splat expression](https://developer.hashicorp.com/terraform/language/expressions/splat). For example, to obtain a list of all of the `device_name` values, use `aws_instance.example.ebs_block_device[*].device_name`.
    
- The nested blocks in this particular resource type do not have any exported attributes, but if `ebs_block_device` were to have a documented `id` attribute then a list of them could be accessed similarly as `aws_instance.example.ebs_block_device[*].id`.
    
- Sometimes nested blocks are defined as taking a logical key to identify each block, which serves a similar purpose as the resource's own name by providing a convenient way to refer to that single block in expressions. If `aws_instance` had a hypothetical nested block type `device` that accepted such a key, it would look like this in configuration:
    
    ```
      device "foo" {
        size = 2
      }
      device "bar" {
        size = 4
      }
    ```
    
    Arguments inside blocks with _keys_ can be accessed using index syntax, such as `aws_instance.example.device["foo"].size`.
    
    To obtain a map of values of a particular argument for _labelled_ nested block types, use a [`for` expression](https://developer.hashicorp.com/terraform/language/expressions/for): `{for k, device in aws_instance.example.device : k => device.size}`.
    

When a resource has the [`count`](https://developer.hashicorp.com/terraform/language/meta-arguments/count) argument set, the resource itself becomes a _list_ of instance objects rather than a single object. In that case, access the attributes of the instances using either [splat expressions](https://developer.hashicorp.com/terraform/language/expressions/splat) or index syntax:

- [](https://developer.hashicorp.com/terraform/language/expressions/references#)[`aws_instance.example[*].id`](https://developer.hashicorp.com/terraform/language/expressions/references#aws_instance-example-id) returns a list of all of the ids of each of the instances.
- [](https://developer.hashicorp.com/terraform/language/expressions/references#)[`aws_instance.example[0].id`](https://developer.hashicorp.com/terraform/language/expressions/references#aws_instance-example-0-id) returns just the id of the first instance.

When a resource has the [`for_each`](https://developer.hashicorp.com/terraform/language/meta-arguments/for_each) argument set, the resource itself becomes a _map_ of instance objects rather than a single object, and attributes of instances must be specified by key, or can be accessed using a [`for` expression](https://developer.hashicorp.com/terraform/language/expressions/for).

- [](https://developer.hashicorp.com/terraform/language/expressions/references#)[`aws_instance.example["a"].id`](https://developer.hashicorp.com/terraform/language/expressions/references#aws_instance-example-a-id) returns the id of the "a"-keyed resource.
- [](https://developer.hashicorp.com/terraform/language/expressions/references#)[`[for value in aws_instance.example: value.id]`](https://developer.hashicorp.com/terraform/language/expressions/references#for-value-in-aws_instance-example-value-id) returns a list of all of the ids of each of the instances.

Note that unlike `count`, splat expressions are _not_ directly applicable to resources managed with `for_each`, as splat expressions must act on a list value. However, you can use the `values()` function to extract the instances as a list and use that list value in a splat expression:

- [](https://developer.hashicorp.com/terraform/language/expressions/references#)[`values(aws_instance.example)[*].id`](https://developer.hashicorp.com/terraform/language/expressions/references#values-aws_instance-example-id)

### [](https://developer.hashicorp.com/terraform/language/expressions/references#sensitive-resource-attributes)Sensitive Resource Attributes

When defining the schema for a resource type, a provider developer can mark certain attributes as _sensitive_, in which case Terraform will show a placeholder marker `(sensitive value)` instead of the actual value when rendering a plan involving that attribute.

A provider attribute marked as sensitive behaves similarly to [an input variable declared as sensitive](https://developer.hashicorp.com/terraform/language/values/variables#suppressing-values-in-cli-output), where Terraform will hide the value in the plan and apply messages and will also hide any other values you derive from it as sensitive. However, there are some limitations to that behavior as described in [Cases where Terraform may disclose a sensitive variable](https://developer.hashicorp.com/terraform/language/values/variables#cases-where-terraform-may-disclose-a-sensitive-variable).

If you use a sensitive value from a resource attribute as part of an [output value](https://developer.hashicorp.com/terraform/language/values/outputs) then Terraform will require you to also mark the output value itself as sensitive, to confirm that you intended to export it.

Terraform will still record sensitive values in the [state](https://developer.hashicorp.com/terraform/language/state), and so anyone who can access the state data will have access to the sensitive values in cleartext. For more information, see [_Sensitive Data in State_](https://developer.hashicorp.com/terraform/language/state/sensitive-data).

**Note:** Treating values derived from a sensitive resource attribute as sensitive themselves was introduced in Terraform v0.15. Earlier versions of Terraform will obscure the direct value of a sensitive resource attribute, but will _not_ automatically obscure other values derived from sensitive resource attributes.

### [](https://developer.hashicorp.com/terraform/language/expressions/references#values-not-yet-known)Values Not Yet Known

When Terraform is planning a set of changes that will apply your configuration, some resource attribute values cannot be populated immediately because their values are decided dynamically by the remote system. For example, if a particular remote object type is assigned a generated unique id on creation, Terraform cannot predict the value of this id until the object has been created.

Terraform uses special unknown value placeholders for information that it cannot predict during the plan phase. The Terraform language automatically handles unknown values in expressions. For example, adding a known value to an unknown value automatically produces an unknown value as a result.

However, there are some situations where unknown values _do_ have a significant effect:

- The `count` meta-argument for resources cannot be unknown, since it must be evaluated during the plan phase to determine how many instances are to be created.
    
- If unknown values are used in the configuration of a data resource, that data resource cannot be read during the plan phase and so it will be deferred until the apply phase. In this case, the results of the data resource will _also_ be unknown values.
    
- If an unknown value is assigned to an argument inside a `module` block, any references to the corresponding input variable within the child module will use that unknown value.
    
- If an unknown value is used in the `value` argument of an output value, any references to that output value in the parent module will use that unknown value.
    
- Terraform will attempt to validate that unknown values are of suitable types where possible, but incorrect use of such values may not be detected until the apply phase, causing the apply to fail.
    

Unknown values appear in the `terraform plan` output as `(known after apply)`.
### 8f        Use HCL and Terraform functions to write configuration

# Built-in Functions

> **Hands-on:** Try the [Perform Dynamic Operations with Functions](https://developer.hashicorp.com/terraform/tutorials/configuration-language/functions?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS) tutorial.

The Terraform language includes a number of built-in functions that you can call from within expressions to transform and combine values. The general syntax for function calls is a function name followed by comma-separated arguments in parentheses:

```
max(5, 12, 9)
```

For more details on syntax, see [_Function Calls_](https://developer.hashicorp.com/terraform/language/expressions/function-calls) in the Expressions section.

# Provider-defined Functions

You cannot define your own functions in the Terraform configuration language, but you can develop your own providers that expose functions. Refer to [Provider-defined functions](https://developer.hashicorp.com/terraform/plugin/framework/functions) for information about defining functions in custom providers.

When using a provider-specific function, add the `provider::<local-name>::` where `<local-name>` corresponds with an entry in the `required_providers` block. The following example calls the `encode_tfvars` function in the `terraform` provider:

```
provider::terraform::encode_tfvars({
  example = "Hello!"
})
```

The documentation covers the built-in functions and built-in provider-defined functions only.

Functions defined by external providers are documented by those providers in the [Terraform Registry](https://registry.terraform.io/browse/providers).

# Experimenting with Functions

You can experiment with the behavior of Terraform's built-in functions from the Terraform expression console, by running [the `terraform console` command](https://developer.hashicorp.com/terraform/cli/commands/console):

```
> max(5, 12, 9)
12
```

The examples in the documentation for each function use console output to illustrate the result of calling the function with different parameters.
### 8g       Describe built-in dependency management (order of execution based)

# dynamic Blocks

Within top-level block constructs like resources, expressions can usually be used only when assigning a value to an argument using the `name = expression` form. This covers many uses, but some resource types include repeatable _nested blocks_ in their arguments, which typically represent separate objects that are related to (or embedded within) the containing object:

```
resource "aws_elastic_beanstalk_environment" "tfenvtest" {
  name = "tf-test-name" # can use expressions here

  setting {
    # but the "setting" block is always a literal block
  }
}
```

You can dynamically construct repeatable nested blocks like `setting` using a special `dynamic` block type, which is supported inside `resource`, `data`, `provider`, and `provisioner` blocks:

```
resource "aws_elastic_beanstalk_environment" "tfenvtest" {
  name                = "tf-test-name"
  application         = aws_elastic_beanstalk_application.tftest.name
  solution_stack_name = "64bit Amazon Linux 2018.03 v2.11.4 running Go 1.12.6"

  dynamic "setting" {
    for_each = var.settings
    content {
      namespace = setting.value["namespace"]
      name = setting.value["name"]
      value = setting.value["value"]
    }
  }
}
```

A `dynamic` block acts much like a [`for` expression](https://developer.hashicorp.com/terraform/language/expressions/for), but produces nested blocks instead of a complex typed value. It iterates over a given complex value, and generates a nested block for each element of that complex value.

- The label of the dynamic block (`"setting"` in the example above) specifies what kind of nested block to generate.
- The `for_each` argument provides the complex value to iterate over.
- The `iterator` argument (optional) sets the name of a temporary variable that represents the current element of the complex value. If omitted, the name of the variable defaults to the label of the `dynamic` block (`"setting"` in the example above).
- The `labels` argument (optional) is a list of strings that specifies the block labels, in order, to use for each generated block. You can use the temporary iterator variable in this value.
- The nested `content` block defines the body of each generated block. You can use the temporary iterator variable inside this block.

Since the `for_each` argument accepts any collection or structural value, you can use a `for` expression or splat expression to transform an existing collection.

The iterator object (`setting` in the example above) has two attributes:

- [](https://developer.hashicorp.com/terraform/language/expressions/dynamic-blocks#)[`key`](https://developer.hashicorp.com/terraform/language/expressions/dynamic-blocks#key) is the map key or list element index for the current element. If the `for_each` expression produces a _set_ value then `key` is identical to `value` and should not be used.
- [](https://developer.hashicorp.com/terraform/language/expressions/dynamic-blocks#)[`value`](https://developer.hashicorp.com/terraform/language/expressions/dynamic-blocks#value) is the value of the current element.

A `dynamic` block can only generate arguments that belong to the resource type, data source, provider or provisioner being configured. It is _not_ possible to generate meta-argument blocks such as `lifecycle` and `provisioner` blocks, since Terraform must process these before it is safe to evaluate expressions.

The `for_each` value must be a collection with one element per desired nested block. If you need to declare resource instances based on a nested data structure or combinations of elements from multiple data structures you can use Terraform expressions and functions to derive a suitable value. For some common examples of such situations, see the [`flatten`](https://developer.hashicorp.com/terraform/language/functions/flatten) and [`setproduct`](https://developer.hashicorp.com/terraform/language/functions/setproduct) functions.

## [](https://developer.hashicorp.com/terraform/language/expressions/dynamic-blocks#multi-level-nested-block-structures)Multi-level Nested Block Structures

Some providers define resource types that include multiple levels of blocks nested inside one another. You can generate these nested structures dynamically when necessary by nesting `dynamic` blocks in the `content` portion of other `dynamic` blocks.

For example, a module might accept a complex data structure like the following:

```
variable "load_balancer_origin_groups" {
  type = map(object({
    origins = set(object({
      hostname = string
    }))
  }))
}
```

If you were defining a resource whose type expects a block for each origin group and then nested blocks for each origin within a group, you could ask Terraform to generate that dynamically using the following nested `dynamic` blocks:

```
  dynamic "origin_group" {
    for_each = var.load_balancer_origin_groups
    content {
      name = origin_group.key

      dynamic "origin" {
        for_each = origin_group.value.origins
        content {
          hostname = origin.value.hostname
        }
      }
    }
  }
```

When using nested `dynamic` blocks it's particularly important to pay attention to the iterator symbol for each block. In the above example, `origin_group.value` refers to the current element of the outer block, while `origin.value` refers to the current element of the inner block.

If a particular resource type defines nested blocks that have the same type name as one of their parents, you can use the `iterator` argument in each of `dynamic` blocks to choose a different iterator symbol that makes the two easier to distinguish.

## [](https://developer.hashicorp.com/terraform/language/expressions/dynamic-blocks#best-practices-for-dynamic-blocks)Best Practices for `dynamic` Blocks

Overuse of `dynamic` blocks can make configuration hard to read and maintain, so we recommend using them only when you need to hide details in order to build a clean user interface for a re-usable module. Always write nested blocks out literally where possible.

If you find yourself defining most or all of a `resource` block's arguments and nested blocks using directly-corresponding attributes from an input variable then that might suggest that your module is not creating a useful abstraction. It may be better for the calling module to define the resource itself then pass information about it into your module. For more information on this design tradeoff, see [When to Write a Module](https://developer.hashicorp.com/terraform/language/modules/develop#when-to-write-a-module) and [Module Composition](https://developer.hashicorp.com/terraform/language/modules/develop/composition).

## 9         Understand HCP Terraform capabilities

### 9a       Explain how HCP Terraform helps to manage infrastructure

# HCP Terraform private registry overview

HCP Terraform's private registry works similarly to the [public Terraform Registry](https://developer.hashicorp.com/terraform/registry) and helps you share [Terraform providers](https://developer.hashicorp.com/terraform/language/providers) and [Terraform modules](https://developer.hashicorp.com/terraform/language/modules) across your organization. It includes support for versioning and a searchable list of available providers and modules.

> **Hands-on:** Try the [Add Public Providers and Modules to your Private Registry](https://developer.hashicorp.com/terraform/tutorials/modules/private-registry-add) tutorial and [Share Modules in the Private Registry](https://developer.hashicorp.com/terraform/tutorials/modules/module-private-registry-share) tutorials.

## [](https://developer.hashicorp.com/terraform/cloud-docs/registry#public-providers-and-modules)Public Providers and Modules

[Public modules and providers](https://developer.hashicorp.com/terraform/cloud-docs/registry/add) are hosted on the public Terraform Registry and HCP Terraform can automatically synchronize them to an organization's private registry. This lets you clearly designate which public providers and modules are recommended for the organization and makes their supporting documentation and examples centrally accessible.

For more information about publishing artifacts to the public registry with an HCP Terraform organization, refer to [Namespaces](https://developer.hashicorp.com/terraform/cloud-docs/public-namespace).

**Note:** Your Terraform Enterprise instance must allow access to `registry.terraform.io`, `https://yy0ffni7mf-dsn.algolia.net/` and `github.com`.

## [](https://developer.hashicorp.com/terraform/cloud-docs/registry#private-providers-and-modules)Private Providers and Modules

[Private providers](https://developer.hashicorp.com/terraform/cloud-docs/registry/publish-providers) and [private modules](https://developer.hashicorp.com/terraform/cloud-docs/registry/publish-modules) are hosted on an organization's private registry and are only available to members of that organization. In Terraform Enterprise, private providers and modules are also available to other organizations that are [configured to share](https://developer.hashicorp.com/terraform/enterprise/admin/application/registry-sharing) with that organization.

## [](https://developer.hashicorp.com/terraform/cloud-docs/registry#managing-usage)Managing Usage

You can create [Sentinel policies](https://developer.hashicorp.com/terraform/cloud-docs/policy-enforcement) to manage how members of your organization can use modules from the private registry. For example, you can mandate that all non-root modules in Terraform configurations must be private or public modules from your own private registry. You can also apply a policy that requires all modules to use recent versions. Refer to our [example policy on GitHub](https://github.com/hashicorp/terraform-sentinel-policies/blob/main/cloud-agnostic/http-examples/use-recent-versions-from-pmr.sentinel).

### 9b       Describe how HCP Terraform enables collaboration and governance

# Workspaces

This topic provides an overview of the workspaces resource in HCP Terraform and Terraform Enterprise. A workspace is a group of infrastructure resources managed by Terraform.

## [](https://developer.hashicorp.com/terraform/cloud-docs/workspaces#introduction)Introduction

Working with Terraform involves managing collections of infrastructure resources, and most organizations manage many different collections.

When run locally, Terraform manages each collection of infrastructure with a persistent working directory, which contains a configuration, state data, and variables. Since Terraform CLI uses content from the directory it runs in, you can organize infrastructure resources into meaningful groups by keeping their configurations in separate directories.

HCP Terraform manages infrastructure collections with workspaces instead of directories. A workspace contains everything Terraform needs to manage a given collection of infrastructure, and separate workspaces function like completely separate working directories.

> **Hands-on:** Try the [Create a Workspace](https://developer.hashicorp.com/terraform/tutorials/cloud-get-started/cloud-workspace-create) tutorial.

## [](https://developer.hashicorp.com/terraform/cloud-docs/workspaces#workspace-contents)Workspace Contents

HCP Terraform workspaces and local working directories serve the same purpose, but they store their data differently:

|Component|Local Terraform|HCP Terraform|
|---|---|---|
|Terraform configuration|On disk|In linked version control repository, or periodically uploaded via API/CLI|
|Variable values|As `.tfvars` files, as CLI arguments, or in shell environment|In workspace|
|State|On disk or in remote backend|In workspace|
|Credentials and secrets|In shell environment or entered at prompts|In workspace, stored as sensitive variables|

In addition to the basic Terraform content, HCP Terraform keeps some additional data for each workspace:

- **State versions:** Each workspace retains backups of its previous state files. Although only the current state is necessary for managing resources, the state history can be useful for tracking changes over time or recovering from problems. Refer to [Terraform State in HCP Terraform](https://developer.hashicorp.com/terraform/cloud-docs/workspaces/state) for more details.
    
- **Run history:** When HCP Terraform manages a workspace's Terraform runs, it retains a record of all run activity, including summaries, logs, a reference to the changes that caused the run, and user comments. Refer to [Viewing and Managing Runs](https://developer.hashicorp.com/terraform/cloud-docs/run/manage) for more details.
    

The top of each workspace shows a resource count, which reflects the number of resources recorded in the workspace’s state file. This includes both managed [resources](https://developer.hashicorp.com/terraform/language/resources/syntax) and [data sources](https://developer.hashicorp.com/terraform/language/data-sources).

## [](https://developer.hashicorp.com/terraform/cloud-docs/workspaces#terraform-runs)Terraform Runs

For workspaces with remote operations enabled (the default), HCP Terraform performs Terraform runs on its own disposable virtual machines, using that workspace's configuration, variables, and state.

Refer to [Terraform Runs and Remote Operations](https://developer.hashicorp.com/terraform/cloud-docs/run/remote-operations) for more details.

## [](https://developer.hashicorp.com/terraform/cloud-docs/workspaces#hcp-terraform-vs-terraform-cli-workspaces)HCP Terraform vs. Terraform CLI Workspaces

Both HCP Terraform and Terraform CLI have features called workspaces, but they function differently.

- HCP Terraform workspaces are required. They represent all of the collections of infrastructure in an organization. They are also a major component of role-based access in HCP Terraform. You can grant individual users and user groups permissions for one or more workspaces that dictate whether they can manage variables, perform runs, etc. You cannot manage resources in HCP Terraform without creating at least one workspace.
    
- Terraform CLI workspaces are associated with a specific working directory and isolate multiple state files in the same working directory, letting you manage multiple groups of resources with a single configuration. The Terraform CLI does not require you to create CLI workspaces. Refer to [Workspaces](https://developer.hashicorp.com/terraform/language/state/workspaces) in the Terraform Language documentation for more details.
    

## [](https://developer.hashicorp.com/terraform/cloud-docs/workspaces#planning-and-organizing-workspaces)Planning and Organizing Workspaces

We recommend that organizations break down large monolithic Terraform configurations into smaller ones, then assign each one to its own workspace and delegate permissions and responsibilities for them. HCP Terraform can manage monolithic configurations just fine, but managing infrastructure as smaller components is the best way to take full advantage of HCP Terraform's governance and delegation features.

For example, the code that manages your production environment's infrastructure could be split into a networking configuration, the main application's configuration, and a monitoring configuration. After splitting the code, you would create "networking-prod", "app1-prod", "monitoring-prod" workspaces, and assign separate teams to manage them.

Much like splitting monolithic applications into smaller microservices, this enables teams to make changes in parallel. In addition, it makes it easier to re-use configurations to manage other environments of infrastructure ("app1-dev," etc.).

In Terraform Enterprise, administrators can use [Admin Settings](https://developer.hashicorp.com/terraform/enterprise/api-docs/admin/settings) to set the maximum number of workspaces for any single organization. You can also set a workspaces limit with the [tfe-terraform-provider](https://registry.terraform.io/providers/hashicorp/tfe/latest/docs/resources/organization#workspace_limit).

## [](https://developer.hashicorp.com/terraform/cloud-docs/workspaces#organize-workspaces-with-projects)Organize Workspaces with Projects

Projects let you organize your workspaces into groups.

**Note:** On HCP Terraform **Standard**, **Plus**, and **Premium** editions, you can assign project permissions to scope access to collections of workspaces based on business units and responsibilities. Refer to [HCP Terraform pricing](https://www.hashicorp.com/products/terraform/pricing) for details.

Refer to [Organize Workspaces with Projects](https://developer.hashicorp.com/terraform/cloud-docs/projects/manage) for more details.

## [](https://developer.hashicorp.com/terraform/cloud-docs/workspaces#creating-workspaces)Creating Workspaces

You can create workspaces through the [HCP Terraform UI](https://developer.hashicorp.com/terraform/cloud-docs/workspaces/create), the [Workspaces API](https://developer.hashicorp.com/terraform/cloud-docs/api-docs/workspaces), or the [HCP Terraform CLI integration](https://developer.hashicorp.com/terraform/cli/cloud).

## [](https://developer.hashicorp.com/terraform/cloud-docs/workspaces#workspace-health)Workspace Health

**Note:** Health assessments are available in HCP Terraform **Plus** and **Premium** editions. Refer to [HCP Terraform pricing](https://www.hashicorp.com/products/terraform/pricing) for details.

HCP Terraform can perform automatic health assessments in a workspace to assess whether its real infrastructure matches the requirements defined in its Terraform configuration. Health assessments include the following types of evaluations:

- Drift detection determines whether your real-world infrastructure matches your Terraform configuration.
- Continuous validation determines whether custom conditions in the workspace’s configuration continue to pass after Terraform provisions the infrastructure.

You can enforce health assessments for all eligible workspaces or let each workspace opt in to health assessments through workspace settings. Refer to [Health](https://developer.hashicorp.com/terraform/cloud-docs/workspaces/health) in the workspaces documentation for more details.

# UI and VCS-driven run workflow

HCP Terraform has three workflows for managing Terraform runs.

- The UI/VCS-driven run workflow described below, which is the primary mode of operation.
- The [API-driven run workflow](https://developer.hashicorp.com/terraform/cloud-docs/run/api), which is more flexible but requires you to create some tooling.
- The [CLI-driven run workflow](https://developer.hashicorp.com/terraform/cloud-docs/run/cli), which uses Terraform's standard CLI tools to execute runs in HCP Terraform.

## [](https://developer.hashicorp.com/terraform/cloud-docs/run/ui#summary)Summary

In the UI and VCS workflow, every workspace is associated with a specific branch of a VCS repo of Terraform configurations. HCP Terraform registers webhooks with your VCS provider when you create a workspace, then automatically queues a Terraform run whenever new commits are merged to that branch of workspace's linked repository.

HCP Terraform also performs a [speculative plan](https://developer.hashicorp.com/terraform/cloud-docs/run/remote-operations#speculative-plans) when a pull request is opened against that branch. HCP Terraform posts a link to the plan in the pull request, and re-runs the plan if the pull request is updated.

The Terraform code for a normal run always comes from version control, and is always associated with a specific commit.

## [](https://developer.hashicorp.com/terraform/cloud-docs/run/ui#automatically-starting-runs)Automatically Starting Runs

In a workspace linked to a VCS repository, runs start automatically when you merge or commit changes to version control.

If you use GitHub as your VCS provider and merge a PR changing 300 or more files, HCP Terraform automatically triggers runs for every workspace connected to that repository. The GitHub API has a limit of 300 reported changed files for a PR merge. To address this, HCP Terraform initiates workspace runs proactively, preventing oversight of file changes beyond this limit.

A workspace is linked to one branch of a VCS repository and ignores changes to other branches. You can specify which files and directories within your repository trigger runs. HCP Terraform can also automatically trigger runs when you create Git tags. Refer to [Automatic Run Triggering](https://developer.hashicorp.com/terraform/cloud-docs/workspaces/settings/vcs#automatic-run-triggering) for details.

**Note:** A workspace with no runs will not accept new runs via VCS webhook. At least one run must be manually queued to confirm that the workspace is ready for further runs.

A workspace will not process a webhook if the workspace previously processed a webhook with the same commit SHA and created a run. To trigger a run, create a new commit. If a workspace receives a webhook with a previously processed commit, HCP Terraform will add a new event to the [VCS Events](https://developer.hashicorp.com/terraform/cloud-docs/vcs#viewing-events) page documenting the received webhook.

## [](https://developer.hashicorp.com/terraform/cloud-docs/run/ui#manually-starting-runs)Manually Starting Runs

You can manually trigger a run using the UI. Manual runs let you apply configuration changes when you update variable values but the configuration in version control is unchanged. You must manually trigger an initial run in any new VCS-driven workspace.

**Note:** When you trigger a manual run, HCP Terraform does not fetch the latest commit from your VCS repository, and instead uses the current [configuration version](https://developer.hashicorp.com/terraform/cloud-docs/workspaces/configurations) associated with the workspace. HCP Terraform uses [VCS Webhooks](https://developer.hashicorp.com/terraform/cloud-docs/vcs#webhooks) to monitor changes in your VCS repository and update your configuration version.

To start a run:

1. Sign in to [HCP Terraform](https://app.terraform.io/) or Terraform Enterprise and navigate to the workspace you want to start a run in.
2. Click **+ New run**, opening the **Start a new run** dialog.
3. Select the run mode and provide an optional message.

Review the [run modes documentation](https://developer.hashicorp.com/terraform/cloud-docs/run/modes-and-options) for more detail on supported options.

Run modes that have a plan phase support debugging mode. This is equivalent to setting the `TF_LOG` environment variable to `TRACE` for this run only. To enable debugging, click **Additional planning options** under the run mode and click **Enable debugging mode**. See [Debugging Terraform](https://developer.hashicorp.com/terraform/internals/debugging) for more information.

To [replace](https://developer.hashicorp.com/terraform/cloud-docs/run/modes-and-options#replacing-selected-resources) specific resources as part of a standard plan and apply run, expand the **Additional planning options** section and select the resources to replace.

Manually starting a run requires permission to queue plans for the workspace. ([More about permissions.](https://developer.hashicorp.com/terraform/cloud-docs/users-teams-organizations/permissions))

If the workspace has a plan that is still in the [plan stage](https://developer.hashicorp.com/terraform/cloud-docs/run/states#the-plan-stage) when a new plan is queued, you can either wait for it to complete, or visit the **Current Run** page and click **Run this plan now**. Be aware that this action terminates the current plan and unlocks the workspace, which can lead to anomalies in behavior, but can be useful if the plans are long-running and the current plan does not have all the desired changes.

## [](https://developer.hashicorp.com/terraform/cloud-docs/run/ui#automatically-cancel-plan-only-runs-triggered-by-outdated-commits)Automatically cancel plan-only runs triggered by outdated commits

Refer to [Automatically cancel plan-only runs triggered by outdated commits](https://developer.hashicorp.com/terraform/cloud-docs/users-teams-organizations/organizations/vcs-speculative-plan-management) for additional information.

## [](https://developer.hashicorp.com/terraform/cloud-docs/run/ui#confirming-or-discarding-plans)Confirming or Discarding Plans

By default, run plans require confirmation before HCP Terraform will apply them. Users with permission to apply runs for the workspace can navigate to a run that has finished planning and click the "Confirm & Apply" or "Discard Plan" button to finish or cancel a run. ([More about permissions.](https://developer.hashicorp.com/terraform/cloud-docs/users-teams-organizations/permissions)) If necessary, use the "View Plan" button for more details about what the run will change.

![confirm button](https://web-unified-docs-hashicorp.vercel.app/api/assets/terraform-docs-common/latest/img/docs/runs-confirm.png)

Users can also leave comments if there's something unusual involved in a run.

Note that once the plan stage is completed, until you apply or discard a plan, HCP Terraform can't start another run in that workspace.

### [](https://developer.hashicorp.com/terraform/cloud-docs/run/ui#auto-apply)Auto apply

If you would rather automatically apply plans that don't have errors, you can [enable auto apply](https://developer.hashicorp.com/terraform/cloud-docs/workspaces/settings#auto-apply-and-manual-apply) on the workspace's "General Settings" page. Some plans can't be auto-applied, like plans queued by [run triggers](https://developer.hashicorp.com/terraform/cloud-docs/workspaces/settings/run-triggers) or by users without permission to apply runs. ([More about permissions.](https://developer.hashicorp.com/terraform/cloud-docs/users-teams-organizations/permissions))

## [](https://developer.hashicorp.com/terraform/cloud-docs/run/ui#speculative-plans-on-pull-requests)Speculative Plans on Pull Requests

To help you review proposed changes, HCP Terraform can automatically run [speculative plans](https://developer.hashicorp.com/terraform/cloud-docs/run/remote-operations#speculative-plans) for pull requests or merge requests.

### [](https://developer.hashicorp.com/terraform/cloud-docs/run/ui#viewing-pull-request-plans)Viewing Pull Request Plans

You can view speculative plans in a workspace's list of normal runs. Additionally, HCP Terraform adds a link to the run in the pull request itself, along with an indicator of the run's status.

A single pull request can include links to multiple plans, depending on how many workspaces connect to the destination branch. If you update a pull request, HCP Terraform performs new speculative plans and update the links.

Although any contributor to the repository can see the status indicators for pull request plans, only members of your HCP Terraform organization with permission to read runs for the affected workspaces can click through and view the complete plan output. ([More about permissions.](https://developer.hashicorp.com/terraform/cloud-docs/users-teams-organizations/permissions))

### [](https://developer.hashicorp.com/terraform/cloud-docs/run/ui#rules-for-triggering-pull-request-plans)Rules for Triggering Pull Request Plans

Whenever a pull request is _created or updated,_ HCP Terraform checks whether it should run speculative plans in workspaces connected to that repository, based on the following rules:

- Only pull requests that originate from within the same repository can trigger speculative plans.
    
    To avoid executing malicious code or exposing sensitive information, HCP Terraform doesn't run speculative plans for pull requests that originate from forks of a repository.
    
    **Note:** On Terraform Enterprise, administrators can choose to allow speculative plans on pull requests that originate from forks. To learn more about this setting, refer to the [general settings documentation](https://developer.hashicorp.com/terraform/enterprise/admin/application/general#allow-speculative-plans-on-pull-requests-from-forks)
    
- Pull requests can only trigger runs in workspaces where automatic speculative plans are allowed. You can [disable automatic speculative plans](https://developer.hashicorp.com/terraform/cloud-docs/workspaces/settings/vcs#automatic-speculative-plans) in a workspace's VCS settings.
    
- A pull request will only trigger speculative plans in workspaces that are connected to that pull request's destination branch.
    
    The destination branch is the branch that a pull request proposes to make changes to; this is often the repository's main branch, but not always.
    
- If a workspace is configured to only treat certain directories in a repository as relevant, pull requests that don't affect those directories won't trigger speculative plans in that workspace. For more information, see [VCS settings: automatic run triggering](https://developer.hashicorp.com/terraform/cloud-docs/workspaces/settings/vcs#automatic-run-triggering).
    
    **Note:** If HCP Terraform skips a plan because the changes weren't relevant, it will still post a passing commit status to the pull request.
    
- HCP Terraform does not update the status checks on a pull request with the status of an associated apply. This means that a commit with a successful plan but an errored apply will still show the passing commit status from the plan.
    

### [](https://developer.hashicorp.com/terraform/cloud-docs/run/ui#contents-of-pull-request-plans)Contents of Pull Request Plans

Speculative plans for pull requests use the contents of the head branch (the branch that the PR proposes to merge into the destination branch), and they compare against the workspace's current state at the time of the plan. This means that if the destination branch changes significantly after the head branch is created, the speculative plan might not accurately show the results of accepting the PR. To get a more accurate view, you can rebase the head branch onto a more recent commit, or merge the destination branch into the head branch.

## [](https://developer.hashicorp.com/terraform/cloud-docs/run/ui#testing-terraform-upgrades-with-speculative-plans)Testing Terraform Upgrades with Speculative Plans

You can start a new [speculative plan](https://developer.hashicorp.com/terraform/cloud-docs/run/remote-operations#speculative-plans) in the UI with the workspace's current configuration version and any Terraform version available to the organization.

1. Sign in to [HCP Terraform](https://app.terraform.io/) or Terraform Enterprise and navigate to the workspace you want to try a new Terraform version in.
2. Click **+ New run**.
3. Select **Plan only** as the run type.
4. Select a version from the **Choose Terraform version** menu. The speculative plan will use this version without changing the workspace's settings.
5. Click **Start run**.

If the run is successful, you can change the workspace's Terraform version and [upgrade the state](https://developer.hashicorp.com/terraform/cloud-docs/workspaces/state#upgrading-state).

## [](https://developer.hashicorp.com/terraform/cloud-docs/run/ui#speculative-plans-during-development)Speculative Plans During Development

You can also use the CLI to run speculative plans on demand before making a pull request. Refer to the [CLI-driven run workflow](https://developer.hashicorp.com/terraform/cloud-docs/run/cli#remote-speculative-plans) for more details.

### Extras

## Shell Tab-completion

If you use either `bash` or `zsh` as your command shell, Terraform can provide tab-completion support for all command names and some command arguments.

To add the necessary commands to your shell profile, run the following command:

```
terraform -install-autocomplete
```

After installation, it is necessary to restart your shell or to re-read its profile script before completion will be activated.

To uninstall the completion hook, assuming that it has not been modified manually in the shell profile, run the following command:

```
terraform -uninstall-autocomplete
```


## `alias`: Multiple Provider Configurations

You can optionally define multiple configurations for the same provider, and select which one to use on a per-resource or per-module basis. The primary reason for this is to support multiple regions for a cloud platform; other examples include targeting multiple Docker hosts, multiple Consul hosts, etc.

To create multiple configurations for a given provider, include multiple `provider` blocks with the same provider name. For each additional non-default configuration, use the `alias` meta-argument to provide an extra name segment. For example:

```
# The default provider configuration; resources that begin with `aws_` will use
# it as the default, and it can be referenced as `aws`.
provider "aws" {
  region = "us-east-1"
}

# Additional provider configuration for west coast region; resources can
# reference this as `aws.west`.
provider "aws" {
  alias  = "west"
  region = "us-west-2"
}
```

To declare a configuration alias within a module in order to receive an alternate provider configuration from the parent module, add the `configuration_aliases` argument to that provider's `required_providers` entry. The following example declares both the `mycloud` and `mycloud.alternate` provider configuration names within the containing module:

```
terraform {
  required_providers {
    mycloud = {
      source  = "mycorp/mycloud"
      version = "~> 1.0"
      configuration_aliases = [ mycloud.alternate ]
    }
  }
}
```