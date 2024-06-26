<!-- BEGIN_TF_DOCS -->
## Requirements

No requirements.

## Providers

| Name | Version |
|------|---------|
| <a name="provider_oci"></a> [oci](#provider\_oci) | n/a |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [oci_core_default_security_list.these](https://registry.terraform.io/providers/oracle/oci/latest/docs/resources/core_default_security_list) | resource |
| [oci_core_drg_attachment.these](https://registry.terraform.io/providers/oracle/oci/latest/docs/resources/core_drg_attachment) | resource |
| [oci_core_internet_gateway.these](https://registry.terraform.io/providers/oracle/oci/latest/docs/resources/core_internet_gateway) | resource |
| [oci_core_nat_gateway.these](https://registry.terraform.io/providers/oracle/oci/latest/docs/resources/core_nat_gateway) | resource |
| [oci_core_security_list.these](https://registry.terraform.io/providers/oracle/oci/latest/docs/resources/core_security_list) | resource |
| [oci_core_service_gateway.these](https://registry.terraform.io/providers/oracle/oci/latest/docs/resources/core_service_gateway) | resource |
| [oci_core_subnet.these](https://registry.terraform.io/providers/oracle/oci/latest/docs/resources/core_subnet) | resource |
| [oci_core_vcn.these](https://registry.terraform.io/providers/oracle/oci/latest/docs/resources/core_vcn) | resource |
| [oci_core_services.all_services](https://registry.terraform.io/providers/oracle/oci/latest/docs/data-sources/core_services) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_compartment_id"></a> [compartment\_id](#input\_compartment\_id) | Compartment's OCID where VCN will be created. | `string` | n/a | yes |
| <a name="input_drg_id"></a> [drg\_id](#input\_drg\_id) | DRG to be attached | `string` | `null` | no |
| <a name="input_service_gateway_cidr"></a> [service\_gateway\_cidr](#input\_service\_gateway\_cidr) | The OSN service cidr accessible through Service Gateway | `string` | n/a | yes |
| <a name="input_service_label"></a> [service\_label](#input\_service\_label) | A service label to be used as part of resource names. | `string` | n/a | yes |
| <a name="input_vcns"></a> [vcns](#input\_vcns) | The VCNs. | <pre>map(object({<br>    compartment_id    = string,<br>    cidr              = string,<br>    dns_label         = string,<br>    is_create_igw     = bool,<br>    is_attach_drg     = bool,<br>    block_nat_traffic = bool,<br>    defined_tags      = map(string),<br>    freeform_tags     = map(string),<br>    subnets = map(object({<br>      compartment_id  = string,<br>      name            = string,<br>      cidr            = string,<br>      dns_label       = string,<br>      private         = bool,<br>      dhcp_options_id = string,<br>      defined_tags    = map(string),<br>      freeform_tags   = map(string),<br>      security_lists = map(object({<br>        is_create      = bool,<br>        compartment_id = string,<br>        defined_tags   = map(string),<br>        freeform_tags  = map(string),<br>        ingress_rules = list(object({<br>          is_create    = bool,<br>          stateless    = bool,<br>          protocol     = string,<br>          description  = string,<br>          src          = string,<br>          src_type     = string,<br>          src_port_min = number,<br>          src_port_max = number,<br>          dst_port_min = number,<br>          dst_port_max = number,<br>          icmp_type    = number,<br>          icmp_code    = number<br>        })),<br>        egress_rules = list(object({<br>          is_create    = bool,<br>          stateless    = bool,<br>          protocol     = string,<br>          description  = string,<br>          dst          = string,<br>          dst_type     = string,<br>          src_port_min = number,<br>          src_port_max = number,<br>          dst_port_min = number,<br>          dst_port_max = number,<br>          icmp_type    = number,<br>          icmp_code    = number<br>        }))<br>      }))<br>    }))<br>  }))</pre> | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_all_services"></a> [all\_services](#output\_all\_services) | All services |
| <a name="output_internet_gateways"></a> [internet\_gateways](#output\_internet\_gateways) | The Internet gateways, indexed by display\_name. |
| <a name="output_nat_gateways"></a> [nat\_gateways](#output\_nat\_gateways) | The NAT gateways, indexed by display\_name. |
| <a name="output_security_lists"></a> [security\_lists](#output\_security\_lists) | All Network Security Lists |
| <a name="output_service_gateways"></a> [service\_gateways](#output\_service\_gateways) | The Service gateways, indexed by display\_name. |
| <a name="output_subnets"></a> [subnets](#output\_subnets) | The subnets, indexed by display\_name. |
| <a name="output_vcns"></a> [vcns](#output\_vcns) | The VCNs, indexed by display\_name. |
<!-- END_TF_DOCS -->