|                     |                                                                                   |     |
| ------------------- | --------------------------------------------------------------------------------- | --- |
| **Assessment Type** | Multiple choice                                                                   |     |
| **Format**          | Online proctored                                                                  |     |
| **Duration**        | 1 hour                                                                            |     |
| **Price**           | $70.50 USD, plus locally applicable taxes and fees. Free retake **not included**. |     |
| **Language**        | English                                                                           |     |
| **Expiration**      | 2 years                                                                           |     |

## Inhaltsverzeichnis

1         Understand Infrastructure as Code (IaC) concepts
- [1         Understand Infrastructure as Code (IaC) concepts](#1---------understand-infrastructure-as-code-iac-concepts)
    - [1a       Explain what IaC is](#1a-------explain-what-iac-is)
    - [1b       Describe advantages of IaC patterns](#1b------describe-advantages-of-iac-patterns)

2         Understand the purpose of Terraform (vs other IaC)
------------------------------------------------------------
- [2         Understand the purpose of Terraform (vs other IaC)](#2---------understand-the-purpose-of-terraform-vs-other-iac)
    - [2a       Explain multi-cloud and provider-agnostic benefits](#2a-------explain-multi-cloud-and-provider-agnostic-benefits)
    - [2b       Explain the benefits of state](#2b-------explain-the-benefits-of-state)

3         Understand Terraform basics
-------------------------------------
- [3         Understand Terraform basics](#3---------understand-terraform-basics)
    - [3a       Install and version Terraform providers](#3a-------install-and-version-terraform-providers)
    - [3c       Write Terraform configuration using multiple providers](#3c-------write-terraform-configuration-using-multiple-providers)
    - [3d       Describe how Terraform finds and fetches providers](#3d-------describe-how-terraform-finds-and-fetches-providers)

4         Use Terraform outside the core workflow
-------------------------------------------------
- [4         Use Terraform outside the core workflow](#4---------use-terraform-outside-the-core-workflow)
    - [4a       Describe when to use terraform import to import existing infrastructure into your Terraform state](#4a-------describe-when-to-use-terraform-import-to-import-existing-infrastructure-into-your-terraform-state)
    - [4b       Use terraform state to view Terraform state](#4b-------use-terraform-state-to-view-terraform-state)
    - [4c       Describe when to enable verbose logging and what the outcome/value is](#4c-------describe-when-to-enable-verbose-logging-and-what-the-outcomevalue-is)

5         Interact with Terraform modules
-----------------------------------------
- [5         Interact with Terraform modules](#5---------interact-with-terraform-modules)
    - [5a       Contrast and use different module source options including the public Terraform Module Registry](#5a-------contrast-and-use-different-module-source-options-including-the-public-terraform-module-registry)
    - [5b       Interact with module inputs and outputs](#5b-------interact-with-module-inputs-and-outputs)
    - [5c       Describe variable scope within modules/child modules](#5c-------describe-variable-scope-within-moduleschild-modules)
    - [5d       Set module version](#5d-------set-module-version)

6         Use the core Terraform workflow
-----------------------------------------
- [6         Use the core Terraform workflow](#6---------use-the-core-terraform-workflow)
    - [6a       Describe Terraform workflow ( Write -> Plan -> Create )](#6a-------describe-terraform-workflow--write---plan---create-)
    - [6b       Initialize a Terraform working directory (terraform init)](#6b-------initialize-a-terraform-working-directory-terraform-init)
    - [6c       Validate a Terraform configuration (terraform validate)](#6c-------validate-a-terraform-configuration-terraform-validate)
    - [6d       Generate and review an execution plan for Terraform (terraform plan)](#6d-------generate-and-review-an-execution-plan-for-terraform-terraform-plan)
    - [6e       Execute changes to infrastructure with Terraform (terraform apply)](#6e-------execute-changes-to-infrastructure-with-terraform-terraform-apply)
    - [6f        Destroy Terraform managed infrastructure (terraform destroy)](#6f--------destroy-terraform-managed-infrastructure-terraform-destroy)
    - [6g       Apply formatting and style adjustments to a configuration (terraform fmt)](#6g-------apply-formatting-and-style-adjustments-to-a-configuration-terraform-fmt)

7         Implement and maintain state
--------------------------------------
- [7         Implement and maintain state](#7---------implement-and-maintain-state)
    - [7a       Describe default local backend](#7a-------describe-default-local-backend)
    - [7b       Describe state locking](#7b-------describe-state-locking)
    - [7c       Handle backend and cloud integration authentication methods](#7c-------handle-backend-and-cloud-integration-authentication-methods)
    - [7d       Differentiate remote state back end options](#7d-------differentiate-remote-state-back-end-options)
    - [7e       Manage resource drift and Terraform state](#7e-------manage-resource-drift-and-terraform-state)
    - [7f        Describe backend block and cloud integration in configuration](#7f--------describe-backend-block-and-cloud-integration-in-configuration)
    - [7g       Understand secret management in state files](#7g-------understand-secret-management-in-state-files)

8         Read, generate, and modify configuration
--------------------------------------------------
- [8         Read, generate, and modify configuration](#8---------read-generate-and-modify-configuration)
    - [8a       Demonstrate use of variables and outputs](#8a-------demonstrate-use-of-variables-and-outputs)
    - [8b       Describe secure secret injection best practice](#8b-------describe-secure-secret-injection-best-practice)
    - [8c       Understand the use of collection and structural types](#8c-------understand-the-use-of-collection-and-structural-types)
    - [8d       Create and differentiate resource and data configuration](#8d-------create-and-differentiate-resource-and-data-configuration)
    - [8e       Use resource addressing and resource parameters to connect resources together](#8e-------use-resource-addressing-and-resource-parameters-to-connect-resources-together)
    - [8f        Use HCL and Terraform functions to write configuration](#8f--------use-hcl-and-terraform-functions-to-write-configuration)
    - [8g       Describe built-in dependency management (order of execution based)](#8g-------describe-built-in-dependency-management-order-of-execution-based)

9         Understand HCP Terraform capabilities
-----------------------------------------------
- [9         Understand HCP Terraform capabilities](#9---------understand-hcp-terraform-capabilities)
    - [9a       Explain how HCP Terraform helps to manage infrastructure](#9a-------explain-how-hcp-terraform-helps-to-manage-infrastructure)
    - [9b��      Describe how HCP Terraform enables collaboration and governance](#9b-------describe-how-hcp-terraform-enables-collaboration-and-governance)

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

## 4         Use Terraform outside the core workflow

### 4a       Describe when to use terraform import to import existing infrastructure into your Terraform state

### 4b       Use terraform state to view Terraform state

### 4c       Describe when to enable verbose logging and what the outcome/value is

## 5         Interact with Terraform modules

### 5a       Contrast and use different module source options including the public Terraform Module Registry

### 5b       Interact with module inputs and outputs

### 5c       Describe variable scope within modules/child modules

### 5d       Set module version

## 6         Use the core Terraform workflow

### 6a       Describe Terraform workflow ( Write -> Plan -> Create )

### 6b       Initialize a Terraform working directory (terraform init)

### 6c       Validate a Terraform configuration (terraform validate)

### 6d       Generate and review an execution plan for Terraform (terraform plan)

### 6e       Execute changes to infrastructure with Terraform (terraform apply)

### 6f        Destroy Terraform managed infrastructure (terraform destroy)

### 6g       Apply formatting and style adjustments to a configuration (terraform fmt)

## 7         Implement and maintain state

### 7a       Describe default local backend

### 7b       Describe state locking

### 7c       Handle backend and cloud integration authentication methods

### 7d       Differentiate remote state back end options

### 7e       Manage resource drift and Terraform state

### 7f        Describe backend block and cloud integration in configuration

### 7g       Understand secret management in state files

## 8         Read, generate, and modify configuration

### 8a       Demonstrate use of variables and outputs

### 8b       Describe secure secret injection best practice

### 8c       Understand the use of collection and structural types

### 8d       Create and differentiate resource and data configuration

### 8e       Use resource addressing and resource parameters to connect resources together

### 8f        Use HCL and Terraform functions to write configuration

### 8g       Describe built-in dependency management (order of execution based)

## 9         Understand HCP Terraform capabilities

### 9a       Explain how HCP Terraform helps to manage infrastructure

### 9b       Describe how HCP Terraform enables collaboration and governance