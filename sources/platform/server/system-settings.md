page_main_title: Shippable Server | System settings
main_section: Shippable Server
sub_section: Configuration
page_title: System settings | Shippable Server
page_description: System settings for Shippable Server
page_keywords: docker, microservices, Continuous Integration, Continuous Deployment, CI/CD, testing, automation,

# System settings

The System Settings section of the Admiral UI lets you set some system wide parameters.

<img src="/images/platform/server/admiral-system-settings.png" alt="admiral-system-settings">

The **Run mode** controls the level of logging and other configuration that is very internal to how Shippable Server is implemented. The default mode is `production`. You should **not** change this without guidance from the Shippable team.

The **API retry interval** is the interval between API retries when other Shippable microservices try to call APIs.

The **Account sync frequency** is the interval at which every user account is synced with their source control provider account. This keeps repository lists, permissions, etc., in sync with your source control. The default is **4 hours** and there is no reason to change this unless recommended by the Shippable team.

**Ignore TLS Errors** allows you to configure your Shippable Server to ignore all TLS errors. Do **not** enable this unless you need to work with [self-signed SSL certificates](/platform/server/selfsigned-certificates/) in a trusted network.

**Automatically synchronize SCM** allows you to control whether Shippable will automatically synchronize reposistory lists and permissions from the configured SCM providers. This automatic synchronization may not be desirable if your SCM has a very large number of repositories. If you turn this off, each Shippable user can manually add the repositories they would like to see on Shippable through their Account Profile page.

**Manage System Superusers** allows you to configure the user accounts that will have superuser privileges. Follow [these steps](/platform/server/superuser/) to configure superusers.