# Tamr AWS S3 Module
This terraform module creates a server-side encrypted S3 bucket with a bucket policy enforcing encryption policies.

# Examples
## Basic
```
module "encrypted-s3-eg" {
  source        = "git::https://github.com/Datatamer/terraform-aws-s3.git//modules/encrypted-bucket?ref=1.0.0"
  bucket_name   = "mybucket"
}
```
## Minimal
Smallest complete fully working example. This example might require extra resources to run the example.
- [Minimal](https://github.com/Datatamer/terraform-aws-s3/tree/master/examples/minimal)

# Resources Created
This modules creates:
* a server-side encrypted S3 bucket
* an attached bucket policy enforcing AES256 encryption

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| terraform | >= 0.12 |
| aws | >= 2.45.0 |

## Providers

| Name | Version |
|------|---------|
| aws | >= 2.45.0 |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| bucket\_name | Name of S3 bucket to create. | `string` | n/a | yes |
| additional\_tags | Additional tags to be attached to the S3 bucket. | `map(string)` | `{}` | no |
| arn\_partition | The partition in which the resource is located. A partition is a group of AWS Regions.<br>  Each AWS account is scoped to one partition.<br>  The following are the supported partitions:<br>    aws -AWS Regions<br>    aws-cn - China Regions<br>    aws-us-gov - AWS GovCloud (US) Regions | `string` | `"aws"` | no |
| force\_destroy | A boolean that indicates all objects (including any locked objects) should be deleted from the<br>  bucket so that the bucket can be destroyed without error. These objects are not recoverable. | `bool` | `true` | no |

## Outputs

| Name | Description |
|------|-------------|
| bucket\_name | Name of S3 bucket that was created. |

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->

# References
This repo is based on:
* [terraform standard module structure](https://www.terraform.io/docs/modules/index.html#standard-module-structure)
* [templated terraform module](https://github.com/tmknom/template-terraform-module)

# License
Apache 2 Licensed. See LICENSE for full details.
