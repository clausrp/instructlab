Cloud Pak for Data System version 1.0.8 is the next version after 1.0.7.8 and is intended for Netezza Performance Server customers only. It removes the components, which are going out of support soon, and are not needed for NPS to work, such as Red Hat OpenShift 3.11, Cloud Pak for Data 3.5, and Portworx. It removes the existing VMs, upgrades the firmware and introduces Python 3.6.8.

## Upgrading

Important: If you currently use or intend to use encrypted SED drives, do not upgrade to Cloud Pak for Data System version 1.0.8. Upgrade to version 1.0.8.2, which addresses upgrade and configuration issues in version 1.0.8.

The upgrade procedure is performed by IBM Support.

Your system must be on version 1.0.7.6 or 1.0.7.7 at minimum to upgrade.

Do not upgrade to 1.0.8 if you are using Cloud Pak for Data. The upgrade path for system with Cloud Pak for Data is 1.0.7.6 > 2.0.x. For more information, see [https://www.ibm.com/docs/en/cloud-paks/cloudpak-data-system/2.0?topic=system-advanced-upgrade-from-versions-10x](https://www.ibm.com/docs/en/cloud-paks/cloudpak-data-system/2.0?topic=system-advanced-upgrade-from-versions-10x "(Opens in a new tab or window)").

As a result of this upgrade, Cloud Pak for Data and Portworx are removed and the virtual machines are removed. Follow the upgrade instructions in [Upgrading to version 1.0.8](https://www.ibm.com/docs/en/SS5FPD_1.0.x.x/com.ibm.icpds.doc/admin/icpds_upgrade_108.html "Upgrade to version 1.0.8 is performed by IBM Support.").

Note: This release includes firmware upgrade, which is required for the system to work as designed. Do not use the `--skip-firmware` option when running the `apupgrade` command.

## What's new

Cloud Pak for Data System 1.0.8 is based on 1.0.7.8 version. For more information on the details of 1.0.7.8 release, see [Version 1.0.7.8 release notes](https://www.ibm.com/docs/en/SS5FPD_1.0.x.x/com.ibm.icpds.doc/relnotes_1078.html "Cloud Pak for Data System version 1.0.7.8 is intended for NPS customers only. It removes the components which are going out of support soon, and are not needed for NPS to work, such as Red Hat OpenShift 3.11, Cloud Pak for Data 3.5, and Portworx. It also deactivates the existing VMs, and upgrades the firmware.").

## Software components

Support for [Netezza Performance Server 11.2.1.5](https://www.ibm.com/docs/en/netezza?topic=notes-netezza-performance-server-11215-release "(Opens in a new tab or window)") at minimum.

## Known issues

1.0.8 upgrade on Dell systems does not remove `WORKER` personality.

This issue happens after upgrading to 1.0.8 when the `worker vm` is gone from `e4n1`, but the node still has the `WORKER` personality set. You can see the following output after you run virsh list --all:

```plaintext
[root@e4n1 ~]# virsh list --all Id Name State ---------------------------------------------------- [root@nz5-node1 ~]# ap node -d +------------------+---------+---------------+-----------+-----------+--------+---------------+---------------+ | Node | State | Personality | Monitored | Is Master | Is HUB | Is VDB Master | Is NRS Master | +------------------+---------+---------------+-----------+-----------+--------+---------------+---------------+ | enclosure1.node1 | ENABLED | CONTROL,UNSET | YES | YES | YES | NO | NO | | enclosure2.node1 | ENABLED | CONTROL,UNSET | YES | NO | NO | NO | NO | | enclosure3.node1 | ENABLED | CONTROL,UNSET | YES | NO | NO | NO | NO | | enclosure4.node1 | ENABLED | WORKER,UNSET | YES | NO | NO | NO | NO | +------------------+---------+---------------+-----------+-----------+--------+---------------+---------------+
```

You can also see the following error in the tracelog:

```plaintext
2022-12-09 14:58:30 INFO: Checking for UNSET node(s) LOGGING FROM: yosemite_bundle_upgrade.py:get_unset_worker_node_names:544 2022-12-09 14:58:30 TRACE: Running command [ap node | grep UNSET | cut -f2 -d '|']. LOGGING FROM: yosemite_bundle_upgrade.py:get_unset_worker_node_names:544 2022-12-09 14:58:30 TRACE: RC: 0. STDOUT: [ enclosure1.node1 enclosure2.node1 enclosure3.node1 enclosure4.node1 ] STDERR: [] LOGGING FROM: yosemite_bundle_upgrade.py:get_unset_worker_node_names:544 2022-12-09 14:58:30 TRACE: Running command [ap node set_personality UNSET --magneto_only -f]. LOGGING FROM: yosemite_bundle_upgrade.py:unset_worker_node_personalities:530 2022-12-09 14:58:31 TRACE: RC: 1. STDOUT: [ Generated: 2022-12-09 14:58:31 ] STDERR: ['UNSET' is not a valid node location ] LOGGING FROM: yosemite_bundle_upgrade.py:unset_worker_node_personalities:530 2022-12-09 14:58:31 ERROR: Error running command [ap node set_personality UNSET --magneto_only -f].
```

Workaround:

-   Set the node personalities after 1.0.8 upgrade is complete. Depending on the existing node personality, run:
    -   For `CONTROL,WORKER` run:
        
        ```plaintext
        ap node set_personality <node> CONTROL,UNSET --magneto_only -f
        ```
        
    -   For `WORKER,WORKER` run:
        
        ```plaintext
        ap node set_personality <node> UNSET,UNSET --magneto_only -f
        ```
        
    -   For `WORKER,UNSET` run:
        
        ```plaintext
        ap node set_personality <node> UNSET,UNSET --magneto_only -f
        ```
        
        For example:
        
        ```plaintext
        [root@gt25-node1 upgrade]# ap node +------------------+---------+----------------+-----------+-----------+ | Node | State | Personality | Monitored | Is Master | +------------------+---------+----------------+-----------+-----------+ | enclosure1.node1 | ENABLED | CONTROL,WORKER | YES | YES | | enclosure2.node1 | ENABLED | CONTROL,WORKER | YES | NO | | enclosure3.node1 | ENABLED | CONTROL,WORKER | YES | NO | | enclosure4.node1 | ENABLED | UNSET,UNSET | YES | NO | | enclosure5.node1 | ENABLED | UNSET,UNSET | YES | NO | | enclosure6.node1 | ENABLED | UNSET,UNSET | YES | NO | +------------------+---------+----------------+-----------+-----------+ [root@gt25-node1 upgrade]# ap node set_personality enclosure1.node1 CONTROL,UNSET --magneto_only -f Node role change request sent successfully Generated: 2022-12-13 11:08:07 [root@gt25-node1 upgrade]# ap node +------------------+---------+----------------+-----------+-----------+ | Node | State | Personality | Monitored | Is Master | +------------------+---------+----------------+-----------+-----------+ | enclosure1.node1 | ENABLED | CONTROL,UNSET | YES | YES | | enclosure2.node1 | ENABLED | CONTROL,WORKER | YES | NO | | enclosure3.node1 | ENABLED | CONTROL,WORKER | YES | NO | | enclosure4.node1 | ENABLED | UNSET,UNSET | YES | NO | | enclosure5.node1 | ENABLED | UNSET,UNSET | YES | NO | | enclosure6.node1 | ENABLED | UNSET,UNSET | YES | NO | +------------------+---------+----------------+-----------+-----------+
        ```
        

Alerts SW Component is not ready opened after upgrade.

If any of the following alerts related to Red Hat OpenShift, Cloud Pak for Data, web console, or Portworx are opened after upgrading to 1.0.8, they must be closed manually with `ap issues --close alert_id`:

```plaintext
| 439 | SW_NEEDS_ATTENTION | SW | Openshift node is not ready | YES | | 440 | SW_NEEDS_ATTENTION | SW | Openshift service is not ready | YES | | 446 | SW_NEEDS_ATTENTION | SW | ICP4D service is not ready | YES | | 451 | SW_NEEDS_ATTENTION | SW | Webconsole service is not ready | YES | | 460 | SW_NEEDS_ATTENTION | SW | Portworx component is not healthy
```

Lenovo SD530 data collection for enclosures fails to collect enclosure Fast Failure Data Collection (FFDC) from the System Management Module (SMM).

To avoid that issue, use `sys_hw_util`. Depending on your requirements, you can:

-   Collect one SMM FFDC from one enclosure, for example `enclosure2` by running:
    
    ```plaintext
    /opt/ibm/appliance/platform/hpi/sys_hw_util ffdc -t e2n1 --smm
    ```
    
-   Collect multiple SMM FFDC from all enclosures in a BASE+2 (four enclosures) system by running:
    
    ```plaintext
    /opt/ibm/appliance/platform/hpi/sys_hw_util ffdc -t e{1..4}n1 --smm
    ```
    
    After you run this command on the console, you get the file location of the collected data. For example:
    
    ```plaintext
    After you run this command on the console, you get the file location of the collected data. For example: Comp | FFDC Log Location | ---------+-----------------------------------------------+ e2smm | /var/log/appliance/platform/hpi/FFDC_e2smm/ |
    ```
    

Call Home service configuration utility does not verify CallHome container is actually RUNNING.

When you are running the `callhome_config.py` utility to configure or enable Call Home service, there are several options, which require CallHome container to be RUNNING. You can confirm that Call Home is running by using `ap apps` command. For more information, see [ap commands](https://www.ibm.com/docs/en/SS5FPD_1.0.x.x/com.ibm.icpds.doc/admin/ap.html "The ap command and its subcommands display information about the system and send management requests."). You can also use the following curl command:

```plaintext
curl -X POST -H "Content-Type: application/json" -k https://localhost:8993/status/
```

After curl command runs, you can expect just a timestamp if Call Home is running.

Some BMC/SMM configurations settings on CPDS can change unexpectedly.

Several Cloud Pak for Data System issues were seen recently whose root cause was related to one or more BMC configuration settings having been changed from their expected values. You can see a number of symptoms, depending on which settings were changed. One of the cases observed recently on several different systems resulted in one or more NPS SPUs not being able to PXE boot. This might result in Netezza Performance Server going into a `DOWN` state, depending on how many SPUs are affected.

To determine whether there are BMC settings that were modified from those values that are expected on Cloud Pak for Data System platform, run:

```plaintext
/opt/ibm/appliance/platform/hpi/sys_hw_check node
```

If any nodes have any of these BMC settings that are incorrectly configured, the screen output from `sys_hw_check` indicates that checks for that nodes failed. The report from `sys_hw_check` itemizes exactly which settings generated an `ERROR`

Note: Some values of these settings, when corrected automatically reboot the corrected nodes in order for the changes to take effect. These specific settings which cannot be changed without requiring a reboot are:

-   `DevicesandIOPorts.OnboardLANPort1 and 2`
-   `EnableDisableAdapterOptionROMSupport.OnboardLANPort1 and 2`
-   `MellanoxNetworkAdapter--Slot6 PhysicalPort1 LogicalPort1.NetworkLinkType and PhysicalPort2` (Connector Node only)
-   `DevicesandIOPorts.Device_Slot2 and 4` (Connector Node only)

Before you run `sys_hw_config` to correct any of these (or other) BMC settings, check the report log from `sys_hw_check` If any of the mentioned four BMC settings are flagged as incorrect, then resetting the expected values requires nodes to be rebooted. If this is the case, ensure that these nodes reboots are acceptable before proceeding.

Workaround:

1.  Run:
    
    ```plaintext
    /opt/ibm/appliance/platform/hpi/sys_hw_config node
    ```
    
    to fix all of the incorrectly configured settings.
2.  Rerun:to verify settings are correct.
3.  If NPS went down due to this problem, perform the following actions:
    1.  Run:
        
        ```plaintext
        docker exec -it ipshost1 bash -c "su - nz -c 'nzstate'"
        ```
        
        to query the state of NPS.
    2.  Run:
        
        ```plaintext
        docker exec -it ipshost1 bash -c "su - nz -c 'nzstop'"
        ```
        
        to cleanly stop NPS.
    3.  Run:
        
        ```plaintext
        docker exec -it ipshost1 bash -c "su - nz -c 'nzstart'"
        ```
        
        to start NPS.

Kernel fails to install on connector nodes

Kernel might fail to install on connector nodes with the following error while upgrading:

```plaintext
2023-04-08 17:40:25 TRACE: run_shell_cmd_in_parallel_or_raise(): running cmd uname -r on nodes ['e11n1', 'e12n1', 'e1n1', 'e1n2', 'e1n3', 'e1n4', 'e2n1', 'e2n2', 'e2n3', 'e2n4'] LOGGING FROM: node_os_installer.py:install_resume:308 2023-04-08 17:40:26 TRACE: ['e11n1', 'e1n1', 'e1n2', 'e1n3', 'e1n4', 'e2n1', 'e2n2', 'e2n3', 'e2n4'] RC: 0 STDOUT: [3.10.0-1160.80.1.el7.x86_64 ] STDERR: [] ['e12n1'] RC: 0 STDOUT: [3.10.0-1160.53.1.el7.x86_64 ] STDERR: [] LOGGING FROM: node_os_installer.py:install_resume:308 2023-04-08 17:40:26 TRACE: All nodes are not at the same kernel level LOGGING FROM: node_os_installer.py:install_resume:310 2023-04-08 17:40:26 INFO: nodeos:Failed. Failed to finish Node OS component upgrade. LOGGING FROM: NodeosUpgrader.py:install_resume:143 2023-04-08 17:40:26 FATAL ERROR: Component nodeos did not successfully complete upgrade after multiple reboot cycles
```

Workaround

1.  Delete old kernel rpms from /install/apupgrade\_os\_upgrade on the failed node.
    
    ```plaintext
    ssh <failed node> cd /install/apupgrade_os_upgrade ls | grep kernel* rm -rf kernel*53
    ```
    
2.  Manually install the latest kernel rpms on the failed node by using:
    
    ```plaintext
    yum --nogpgcheck --disablerepo=* -y localinstall /install/apupgrade_os_upgrade/*.rpm --exclude ibm-ca-os-network-pvm,ibm-ca-hosts-pvm,mod_ssl,ibm-ca-os-gpfs-config.
    ```
    
3.  Mark `nodeos=started` in the status file.
    
    ```plaintext
    cd /var/log/appliance/apupgrade/1.0.8.0_release_status vi e1n1_1.0.8.0_release_status
    ```
    
4.  Restart the upgrade by using:
    
    ```plaintext
    apupgrade --upgrade --use-version 1.0.8.0_release --upgrade-directory /localrepo --bundle system
    ```
    

Upgrade might fail due to missing wheel (Python 3) package

For the systems with security patch 7.9.23.02.SP20 applied, upgrading to version 1.0.8 and later might fail due to missing wheel (Python 3) package.

Example of tracelog:

```plaintext
2024-02-10 09:58:54 INFO: nodeos:Starting Node OS component post-install steps... LOGGING FROM: NodeosUpgrader.py:postinstall:166 2024-02-10 09:58:54 INFO: NodeosUpgrader.postinstall:Running nodeOS postinstall script for post upgrade configuration LOGGING FROM: node_os_yosemite_postinstaller.py:run_nodeos_postinstall_script:30 2024-02-10 09:58:54 TRACE: Running command [/opt/ibm/appliance/platform/xcat/scripts/xcat/nodeos_post_actions.py]. LOGGING FROM: node_os_yosemite_postinstaller.py:run_nodeos_postinstall_script:31 2024-02-10 10:01:31 TRACE: RC: 1. STDOUT: [] STDERR: [ERROR: Command ['pip3', 'install', '/tmp/python3_packages/wheel-*.whl', '-f', '/tmp/python3_packages/', '--no-index', '--prefix', '/usr'] failed with error: WARNING: Requirement '/tmp/python3_packages/wheel-*.whl' looks like a filename, but the file does not exist ERROR: wheel-*.whl is not a valid wheel filename. More Info: See /var/log/appliance/platform/xcat/nodeos_post_action.log for details. ] LOGGING FROM: node_os_yosemite_postinstaller.py:run_nodeos_postinstall_script:31 2024-02-10 10:01:31 ERROR: NodeosUpgrader.postinstall:Issue encountered while running nodeOS postinstall script for configuration. LOGGING FROM: node_os_yosemite_postinstaller.py:run_nodeos_postinstall_script:33 2024-02-10 10:01:31 ERROR: LOGGING FROM: node_os_yosemite_postinstaller.py:run_nodeos_postinstall_script:33 2024-02-10 10:01:31 ERROR: ERROR: Command ['pip3', 'install', '/tmp/python3_packages/wheel-*.whl', '-f', '/tmp/python3_packages/', '--no-index', '--prefix', '/usr'] failed with error: LOGGING FROM: node_os_yosemite_postinstaller.py:run_nodeos_postinstall_script:33 2024-02-10 10:01:31 ERROR: WARNING: Requirement '/tmp/python3_packages/wheel-*.whl' looks like a filename, but the file does not exist LOGGING FROM: node_os_yosemite_postinstaller.py:run_nodeos_postinstall_script:33 2024-02-10 10:01:31 ERROR: ERROR: wheel-*.whl is not a valid wheel filename. LOGGING FROM: node_os_yosemite_postinstaller.py:run_nodeos_postinstall_script:33 2024-02-10 10:01:31 ERROR: More Info: See /var/log/appliance/platform/xcat/nodeos_post_action.log for details. LOGGING FROM: node_os_yosemite_postinstaller.py:run_nodeos_postinstall_script:33 2024-02-10 10:01:31 ERROR: LOGGING FROM: node_os_yosemite_postinstaller.py:run_nodeos_postinstall_script:33 2024-02-10 10:01:31 TRACE: In method logger.py:log_error:142 from parent method node_os_yosemite_postinstaller.py:run_nodeos_postinstall_script:33 with args msg = NodeosUpgrader.postinstall:Issue encountered while running nodeOS postinstall script for configuration. ERROR: Command ['pip3', 'install', '/tmp/python3_packages/wheel-*.whl', '-f', '/tmp/python3_packages/', '--no-index', '--prefix', '/usr'] failed with error: WARNING: Requirement '/tmp/python3_packages/wheel-*.whl' looks like a filename, but the file does not exist ERROR: wheel-*.whl is not a valid wheel filename. More Info: See /var/log/appliance/platform/xcat/nodeos_post_action.log for details.
```

Workaround

1.  Download the release bundle:
    
    ```plaintext
    cp -r /localrepo/1.0.8.x_release/EXTRACT/system/bundle/app_img/python3_dependencies /install/app_img/
    ```
    
2.  Copy the Python 3 dependencies from the bundle to /install/app\_img/ on node `e1n1`.
3.  Restart the upgrade.