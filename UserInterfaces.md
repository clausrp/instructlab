Depending on your role, you can use various user interfaces to manage, administer, and use Cloud Pak for Data System.

The system web console that was available in pre-1.0.7.8 versions is no longer available in this release.

## Command line interface apcli

As a platform administrator, you can use the system command line interface `apcli` for managing the system. You can use the `ap` commands to manage and monitor hardware, software, or system alerts. The system commands are described in detail in [System command line](https://www.ibm.com/docs/en/SS5FPD_1.0.x.x/com.ibm.icpds.doc/admin/apcmds.html "You can use the apcli command line to manage the system software, hardware, and modify some configuration settings.").

## Netezza web console

In 1.0.7.8, the NPS web console is no longer hosted in the OpenShift virtual machine. Instead, it is running on a bare-metal control node in a stand-alone container. The container images are installed on all control nodes for high availability. NPS web console is reinstalled during the upgrade, but you can also install it manually on a separate Linux machine. For more information, see [Netezza web console](https://www.ibm.com/docs/en/netezza?topic=server-web-console "(Opens in a new tab or window)").

## Netezza command line interface

As a database administrator or a database user, you can also access the Netezza CLI as described in [Netezza administration interfaces](https://www.ibm.com/docs/en/netezza?topic=npsda-administration-interfaces-1 "(Opens in a new tab or window)").