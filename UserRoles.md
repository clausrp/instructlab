## User roles

Last Updated: 2024-03-06

Depending on your role, you can get access to different user interfaces in the system to complete your tasks.

The users of Cloud Pak for Data System can be classified into three broad categories:

Application users

The administrators and users of the Netezza application who might be assigned different roles, and are managed in the NPS web console as described in [Netezza documentation for user management](https://www.ibm.com/docs/en/netezza?topic=administration-user-management "(Opens in a new tab or window)").

Platform users

These users have access to the hardware platform and they can manage or monitor the hardware and software in the system. Two roles are available:

-   Platform administrator with default user `apadmin`
-   Platform users with default permissions. They cannot run any commands with root privileges.

They monitor the platform and perform various administrative tasks when required. Platform administrators will typically use the Cloud Pak for Data System `apcli` command line for monitoring and system management, as described in [System command line](https://www.ibm.com/docs/en/SS5FPD_1.0.x.x/com.ibm.icpds.doc/admin/apcmds.html "You can use the apcli command line to manage the system software, hardware, and modify some configuration settings.").

Internal users

Users who are strictly used only internally by the platform, and whose accounts are managed internally in a secure way by the platform itself, without any external involvement. These users are not exposed and should not be used to access the system. Modifying the attributes of internal users can leave the system in a non-working state. Examples:

`root` user of the platform nodes

With a strong focus on security and ease of operation, it is by design that customer local Linux users are not given unrestricted access to the host operating system.

At installation, the customer is provided with `root` user password to use on control nodes and NPS container if required. It is absolutely critical to security that the customer changes the default password for the `root` user on all control nodes and NPS container using the `passwd` command as soon as possible.

All tasks which require escalated privileges should be completed as `apadmin` Linux user, or as users added to the `ibmapadmin` Linux group. This group has sufficient access to administer the platform, and automate maintenance tasks. If the user requires `root` privileges they must be added to the `ibmapadmin` group by the system administrator and access root commands through `sudo`.

Users in hardware components

For example, `admin` user in the network switch

`platadmin` and `platuser` in platform nodes

By default, platform users such as `apadmin` and other external LDAP/AD users can only login to the Cloud Pak for Data System control nodes. If you want to login to the worker nodes, perform the following steps:

1.  Log in to the control nodes.
2.  su as either `platadmin` or `platuser`.
3.  ssh to the worker nodes.
    
    Internal ssh access for `platadmin` and `platuser` is configured as passwordless access.