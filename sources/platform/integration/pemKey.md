page_main_title: PEM Keys
main_section: Platform
sub_section: Configuration
sub_sub_section: Integrations
page_title: PEM integration
page_description: How to create and use an PEM Key Integration that is used to connect Shippable DevOps Assembly Lines platform to VMs that allow PEM based auth

# PEM Key Integration

The PEM Key Integration is used to connect Shippable DevOps Assembly Lines platform to VMs that allow PEM based auth. This is typically used to SSH in and then run activities on the machine. Tools like Terraform and Ansible use this to execute scripts on a machine.

## Creating an Integration

You can add this integration by following steps on the [Adding an integration](/platform/tutorial/integration/subscription-integrations/) page.

Here is the information you need to create this integration:

* **Integration type** -- **PEM key**
* **Name** -- choose a friendly name for the integration
* **Key** -- Encrypted Key in PEM format

**Note:** The PEM Key must be generated without passphrase.

## Usage in CI

* [Using PEM/SSH keys in your CI workflow](/ci/ssh-keys/)

## Usage in Assembly Lines

The PEM key integration can be used in the following [resources](/platform/workflow/resource/overview/):

* [integration](/platform/workflow/resource/integration)

### Default Environment Variables
When you create a resource with this integration, and use it as an `IN` or `OUT` for a `runSh` or `runCI` job, a set of environment variables is automatically made available that you can use in your scripts.

`<NAME>` is the the friendly name of the resource with all letters capitalized and all characters that are not letters, numbers or underscores removed. Any numbers at the beginning of the name are also removed to create a valid variable. For example, `my-key-1` will be converted to `MYKEY1`, and `my_key_1` will be converted to `MY_KEY_1`.

| Environment variable						| Description                         |
| ------------- 								|------------------------------------ |
| `<NAME>`\_NAME   			| Name supplied in the integration |
| `<NAME>`\_INTEGRATION\_KEY				| PEM Key supplied in the integration |
| `<NAME>`\_KEYPATH				| The path of a file with the PEM Key supplied in the integration |

### Shippable Utility Functions
The platform also provides a command line utility called [`shipctl`](/platform/tutorial/workflow/using-shipctl/) that can be used to retrieve the values of these environment variables.

The specific function that can be used in the jobs yml is: `shipctl get_integration_resource_field <resource name> <field name>`.

Here is a table that provides the mapping from the environment variable to the field name.

| Environment variable						| Field Name        |
| ------			 							|----------------- |
| `<NAME>`\_INTEGRATION\_KEY				|  |
| `<NAME>`\_KEYPATH				|  |

More information on other utility functions is [documented here](/platform/tutorial/workflow/using-shipctl).

## Further Reading
* [Quick Start to CI](/getting-started/ci-sample)
* [RunSh Job](/platform/workflow/job/runsh)
* [Jobs](/platform/workflow/job/overview)
* [Resources](/platform/workflow/resource/overview)
