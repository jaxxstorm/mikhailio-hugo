---
title: Prerequisites
subtitle: Getting your environment ready
nextstep: 2-newfile
nofeed: true
weight: 1
---

By following this hands-on lab, you will learn the basics of Terraform and its AzureRM provider by deploying real cloud resources. Therefore, several tools are required to go forward.

#### Azure Subscription

You need an active Azure subscription to deploy the components of the application. The total cost of all the resources that you are going to create should be very close to $0. You can use your developer subscription, or create a free Azure subscription [here](https://azure.microsoft.com/free/).

Be sure to clean up the resources after you complete the workshop, as described at the last step.

#### Azure CLI

We will use the command-line interface (CLI) tool to log in to an Azure subscription and run some queries. You can install the CLI tool, as [described here](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest).

The tool is cross-platform: it should work on Windows, macOS, or Linux (including WSL).

After you complete the installation, open a command prompt and type `az`. You should see the welcome message:

```
$ az
     /\
    /  \    _____   _ _  ___ _
   / /\ \  |_  / | | | \'__/ _\
  / ____ \  / /| |_| | | |  __/
 /_/    \_\/___|\__,_|_|  \___|


Welcome to the cool new Azure CLI!
```

Now, login to your Azure account by typing `az login` and providing your credentials in the browser window. When this is done, type `az account show`:

```
$ az account show
{
  "environmentName": "AzureCloud",
  "id": "12345678-9abc-def0-1234-56789abcdef0",
  "isDefault": true,
  "name": "My Subscription Name",
  "state": "Enabled",
  "tenantId": "eeeeeee-eeee-eeee-eeee-eeeeeeeeeeee",
  "user": {
    "name": "name@example.com",
    "type": "user"
  }
}
```

If you have multiple subscriptions and the wrong one is shown, [change the active subscription](https://docs.microsoft.com/en-us/cli/azure/manage-azure-subscriptions-azure-cli?view=azure-cli-latest#change-the-active-subscription).

#### Terraform CLI

Terraform is a CLI tool that drives cloud deployments from the machine where it runs. It is cross-platform and requires no installation, just a copy of the executable file accessible on the system's `PATH`.

Download the executable file from [Download Page](https://www.terraform.io/downloads.html) and either put it in one of the system's `PATH` folders or in the current directory where your workshop files are going to reside.

Alternatively, you can install Terraform [with Brew](https://brewinstall.org/install-terraform-on-mac-with-brew/): `brew install terraform` or [with Chocolatey](https://chocolatey.org/packages/terraform): `choco install terraform`.

Run `terraform version`, and you should get a response back:

```
$ terraform version
Terraform v0.12.8
```

#### Text editor

Any text editor will do, but I recommend Visual Studio Code.

You may want to install [Terraform extension](https://marketplace.visualstudio.com/items?itemName=mauve.terraform) to get syntax highlighting, code completion, and validation while editing Terraform files.

The lab uses HCL 2.0 language features introduced in Terraform 0.12. To enable these features, run the command `Terraform: Enable/Disable Language Server`. Note that the features are experimental and several people reported them not working properly yet. Regardless, feel free to proceed with the lab and be prepared to some red squiggles.

#### Note: Azure Cloud Shell

If you don't want to install any software on your workstation, you can complete the entire lab in [Azure Cloud Shell](https://azure.microsoft.com/en-us/features/cloud-shell/). It's a command-line tool available within your Azure portal, right in the browser.

Azure CLI, Terraform CLI, and Visual Studio Code are pre-installed in Cloud Shell. Just type `az`, `terraform`, or `code .` to run them.

Traditional out-of-browser tools are still likely to provide a better development experience.

## Checkpoint

You are good to go if

- You can type `az account show` and see the details of your target subscription.
- You can type `terraform version` and see a version number `0.12.x` or above
