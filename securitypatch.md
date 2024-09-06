Review the release notes for security patches for Cloud Pak for Data System.

Security patches are tied to the version of Red Hat Linux that is installed on Cloud Pak for Data System. The patches for a specific Red Hat release are cumulative. For example, if your system is on 7.9, you need to install only the latest patch that applies to 7.9, there is no need to install all of them one by one.

Verify that which patch can be installed on your system. **Do not apply the patch if the Red Hat Linux version on your system does not match.**

For installation, see [Applying security patches](https://www.ibm.com/docs/en/cloud-paks/cloudpak-data-system/1.0.x.x?topic=system-applying-security-patches "(Opens in a new tab or window)"). Downtime is required when installing the security patch.

For STIG compliance, see [STIG compliance](https://www.ibm.com/docs/en/SS5FPD_1.0.x.x/com.ibm.icpds.doc/admin/STIG_compliance.html "Review the list of DISA STIG compliance exceptions for Cloud Pak for Data System.").

## 7.9.24.08.SP32

The expected release date of the security patch 7.9.24.08.SP32 is 11 September 2024.

The security patch 7.9.24.08.SP32 is based on RHEL 7.9.

Important: If you are using version 1.0.8.2 or earlier, you must upgrade to 1.0.8.3 or 1.0.8.4 first to apply 7.9.24.08.SP32.

Note: If you update to 7.9.24.08.SP32 and then proceed to upgrade to 1.0.8.4, the `ipmitool rpm version` will get downgraded after the upgrade to 1.0.8.4, which is expected.

Note: If after applying the security patch 7.9.24.08.SP32 or greater, you try to upgrade to 1.0.8.4, the upgrade might fail with the following error:

```plaintext
ATTENTION : Errors encountered during upgrade operation ======================================================== Logfile: /var/log/appliance/apupgrade/20231201/apupgrade20231201104707.log Upgrade Command: apupgrade --upgrade --use-version 1.0.8.4_release --upgrade-directory /localrepo --bundle system 1. HpiUpgrader.install Upgrade Detail: Component install for hpi Caller Info:The call was made from 'HpiInstaller.install' on line 54 with file located at '/localrepo/1.0.8.4_release/EXTRACT/system/upgrade/bundle_upgraders/../hpi/hpi_installer.py' Message: Unable to start IPS, System state is Stopped
```

Workaround

1.  Run the following commands:
    1.  On node `e1n1`:
        
        ```plaintext
        ps -ef | grep tftp kill <tftp process ID> docker exec -it <nps container name> bash
        ```
        
    2.  In NPS container as root user:
    3.  In NPS container:
    4.  Once system is started, check the NPS status:
    5.  If the NPS status is online, restart the upgrade.

The list of Red Hat CVEs, which are expected to be patched in this release:

```plaintext
CVE-2023-4727 (RHSA-2024:4222) Important/Sec. pki-base-10.5.18-32.el7_9.noarch CVE-2023-4727 (RHSA-2024:4222) Important/Sec. pki-base-java-10.5.18-32.el7_9.noarch CVE-2023-4727 (RHSA-2024:4222) Important/Sec. pki-ca-10.5.18-32.el7_9.noarch CVE-2023-4727 (RHSA-2024:4222) Important/Sec. pki-core-debuginfo-10.5.18-32.el7_9.x86_64 CVE-2023-4727 (RHSA-2024:4222) Important/Sec. pki-javadoc-10.5.18-32.el7_9.noarch CVE-2023-4727 (RHSA-2024:4222) Important/Sec. pki-kra-10.5.18-32.el7_9.noarch CVE-2023-4727 (RHSA-2024:4222) Important/Sec. pki-server-10.5.18-32.el7_9.noarch CVE-2023-4727 (RHSA-2024:4222) Important/Sec. pki-symkey-10.5.18-32.el7_9.x86_64 CVE-2023-4727 (RHSA-2024:4222) Important/Sec. pki-tools-10.5.18-32.el7_9.x86_64
```

## 7.9.24.07.SP31

The release date of the security patch 7.9.24.07.SP31 is 24 July 2024. The estimated run time is around 80 minutes.

The security patch 7.9.24.07.SP31 is based on RHEL 7.9.

Important: If you are using version 1.0.8.2 or earlier, you must upgrade to 1.0.8.3 or 1.0.8.4 first to apply 7.9.24.07.SP31.

Note: If you update to 7.9.24.07.SP31 and then proceed to upgrade to 1.0.8.4, the `ipmitool rpm version` will get downgraded after the upgrade to 1.0.8.4, which is expected.

Note: If after applying the security patch 7.9.24.07.SP31 or greater, you try to upgrade to 1.0.8.4, the upgrade might fail with the following error:

```plaintext
ATTENTION : Errors encountered during upgrade operation ======================================================== Logfile: /var/log/appliance/apupgrade/20231201/apupgrade20231201104707.log Upgrade Command: apupgrade --upgrade --use-version 1.0.8.4_release --upgrade-directory /localrepo --bundle system 1. HpiUpgrader.install Upgrade Detail: Component install for hpi Caller Info:The call was made from 'HpiInstaller.install' on line 54 with file located at '/localrepo/1.0.8.4_release/EXTRACT/system/upgrade/bundle_upgraders/../hpi/hpi_installer.py' Message: Unable to start IPS, System state is Stopped
```

Workaround

1.  Run the following commands:
    1.  On node `e1n1`:
        
        ```plaintext
        ps -ef | grep tftp kill <tftp process ID> docker exec -it <nps container name> bash
        ```
        
    2.  In NPS container as root user:
    3.  In NPS container:
    4.  Once system is started, check the NPS status:
    5.  If the NPS status is online, restart the upgrade.

The list of Red Hat CVEs, which are patched in this release:

```plaintext
CVE-2023-4408 (RHSA-2024:3741) Important/Sec. bind-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-50387 (RHSA-2024:3741) Important/Sec. bind-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-50868 (RHSA-2024:3741) Important/Sec. bind-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-4408 (RHSA-2024:3741) Important/Sec. bind-dyndb-ldap-11.1-7.el7_9.1.x86_64 CVE-2023-50387 (RHSA-2024:3741) Important/Sec. bind-dyndb-ldap-11.1-7.el7_9.1.x86_64 CVE-2023-50868 (RHSA-2024:3741) Important/Sec. bind-dyndb-ldap-11.1-7.el7_9.1.x86_64 CVE-2023-4408 (RHSA-2024:3741) Important/Sec. bind-export-libs-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-50387 (RHSA-2024:3741) Important/Sec. bind-export-libs-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-50868 (RHSA-2024:3741) Important/Sec. bind-export-libs-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-4408 (RHSA-2024:3741) Important/Sec. bind-libs-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-50387 (RHSA-2024:3741) Important/Sec. bind-libs-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-50868 (RHSA-2024:3741) Important/Sec. bind-libs-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-4408 (RHSA-2024:3741) Important/Sec. bind-libs-lite-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-50387 (RHSA-2024:3741) Important/Sec. bind-libs-lite-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-50868 (RHSA-2024:3741) Important/Sec. bind-libs-lite-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-4408 (RHSA-2024:3741) Important/Sec. bind-license-32:9.11.4-26.P2.el7_9.16.noarch CVE-2023-50387 (RHSA-2024:3741) Important/Sec. bind-license-32:9.11.4-26.P2.el7_9.16.noarch CVE-2023-50868 (RHSA-2024:3741) Important/Sec. bind-license-32:9.11.4-26.P2.el7_9.16.noarch CVE-2023-4408 (RHSA-2024:3741) Important/Sec. bind-pkcs11-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-50387 (RHSA-2024:3741) Important/Sec. bind-pkcs11-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-50868 (RHSA-2024:3741) Important/Sec. bind-pkcs11-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-4408 (RHSA-2024:3741) Important/Sec. bind-pkcs11-libs-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-50387 (RHSA-2024:3741) Important/Sec. bind-pkcs11-libs-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-50868 (RHSA-2024:3741) Important/Sec. bind-pkcs11-libs-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-4408 (RHSA-2024:3741) Important/Sec. bind-pkcs11-utils-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-50387 (RHSA-2024:3741) Important/Sec. bind-pkcs11-utils-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-50868 (RHSA-2024:3741) Important/Sec. bind-pkcs11-utils-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-4408 (RHSA-2024:3741) Important/Sec. bind-utils-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-50387 (RHSA-2024:3741) Important/Sec. bind-utils-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-50868 (RHSA-2024:3741) Important/Sec. bind-utils-32:9.11.4-26.P2.el7_9.16.x86_64 CVE-2023-4408 (RHSA-2024:3741) Important/Sec. dhclient-12:4.2.5-83.el7_9.2.x86_64 CVE-2023-50387 (RHSA-2024:3741) Important/Sec. dhclient-12:4.2.5-83.el7_9.2.x86_64 CVE-2023-50868 (RHSA-2024:3741) Important/Sec. dhclient-12:4.2.5-83.el7_9.2.x86_64 CVE-2023-4408 (RHSA-2024:3741) Important/Sec. dhcp-12:4.2.5-83.el7_9.2.x86_64 CVE-2023-50387 (RHSA-2024:3741) Important/Sec. dhcp-12:4.2.5-83.el7_9.2.x86_64 CVE-2023-50868 (RHSA-2024:3741) Important/Sec. dhcp-12:4.2.5-83.el7_9.2.x86_64 CVE-2023-4408 (RHSA-2024:3741) Important/Sec. dhcp-common-12:4.2.5-83.el7_9.2.x86_64 CVE-2023-50387 (RHSA-2024:3741) Important/Sec. dhcp-common-12:4.2.5-83.el7_9.2.x86_64 CVE-2023-50868 (RHSA-2024:3741) Important/Sec. dhcp-common-12:4.2.5-83.el7_9.2.x86_64 CVE-2023-4408 (RHSA-2024:3741) Important/Sec. dhcp-libs-12:4.2.5-83.el7_9.2.x86_64 CVE-2023-50387 (RHSA-2024:3741) Important/Sec. dhcp-libs-12:4.2.5-83.el7_9.2.x86_64 CVE-2023-50868 (RHSA-2024:3741) Important/Sec. dhcp-libs-12:4.2.5-83.el7_9.2.x86_64 CVE-2024-3183 (RHSA-2024:3760) Important/Sec. ipa-client-4.6.8-5.el7_9.17.x86_64 CVE-2024-3183 (RHSA-2024:3760) Important/Sec. ipa-client-common-4.6.8-5.el7_9.17.noarch CVE-2024-3183 (RHSA-2024:3760) Important/Sec. ipa-common-4.6.8-5.el7_9.17.noarch CVE-2024-3183 (RHSA-2024:3760) Important/Sec. ipa-debuginfo-4.6.8-5.el7_9.17.x86_64 CVE-2024-3183 (RHSA-2024:3760) Important/Sec. ipa-python-compat-4.6.8-5.el7_9.17.noarch CVE-2024-3183 (RHSA-2024:3760) Important/Sec. ipa-server-4.6.8-5.el7_9.17.x86_64 CVE-2024-3183 (RHSA-2024:3760) Important/Sec. ipa-server-common-4.6.8-5.el7_9.17.noarch CVE-2024-3183 (RHSA-2024:3760) Important/Sec. ipa-server-dns-4.6.8-5.el7_9.17.noarch CVE-2024-3183 (RHSA-2024:3760) Important/Sec. ipa-server-trust-ad-4.6.8-5.el7_9.17.x86_64 CVE-2022-27635 (RHSA-2024:3939) Important/Sec. iwl100-firmware-39.31.5.1-83.el7_9.noarch CVE-2022-36351 (RHSA-2024:3939) Important/Sec. iwl100-firmware-39.31.5.1-83.el7_9.noarch CVE-2022-38076 (RHSA-2024:3939) Important/Sec. iwl100-firmware-39.31.5.1-83.el7_9.noarch CVE-2022-40964 (RHSA-2024:3939) Important/Sec. iwl100-firmware-39.31.5.1-83.el7_9.noarch CVE-2022-46329 (RHSA-2024:3939) Important/Sec. iwl100-firmware-39.31.5.1-83.el7_9.noarch CVE-2022-27635 (RHSA-2024:3939) Important/Sec. iwl1000-firmware-1:39.31.5.1-83.el7_9.noarch CVE-2022-36351 (RHSA-2024:3939) Important/Sec. iwl1000-firmware-1:39.31.5.1-83.el7_9.noarch CVE-2022-38076 (RHSA-2024:3939) Important/Sec. iwl1000-firmware-1:39.31.5.1-83.el7_9.noarch CVE-2022-40964 (RHSA-2024:3939) Important/Sec. iwl1000-firmware-1:39.31.5.1-83.el7_9.noarch CVE-2022-46329 (RHSA-2024:3939) Important/Sec. iwl1000-firmware-1:39.31.5.1-83.el7_9.noarch CVE-2022-27635 (RHSA-2024:3939) Important/Sec. iwl105-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-36351 (RHSA-2024:3939) Important/Sec. iwl105-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-38076 (RHSA-2024:3939) Important/Sec. iwl105-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-40964 (RHSA-2024:3939) Important/Sec. iwl105-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-46329 (RHSA-2024:3939) Important/Sec. iwl105-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-27635 (RHSA-2024:3939) Important/Sec. iwl135-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-36351 (RHSA-2024:3939) Important/Sec. iwl135-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-38076 (RHSA-2024:3939) Important/Sec. iwl135-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-40964 (RHSA-2024:3939) Important/Sec. iwl135-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-46329 (RHSA-2024:3939) Important/Sec. iwl135-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-27635 (RHSA-2024:3939) Important/Sec. iwl2000-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-36351 (RHSA-2024:3939) Important/Sec. iwl2000-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-38076 (RHSA-2024:3939) Important/Sec. iwl2000-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-40964 (RHSA-2024:3939) Important/Sec. iwl2000-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-46329 (RHSA-2024:3939) Important/Sec. iwl2000-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-27635 (RHSA-2024:3939) Important/Sec. iwl2030-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-36351 (RHSA-2024:3939) Important/Sec. iwl2030-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-38076 (RHSA-2024:3939) Important/Sec. iwl2030-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-40964 (RHSA-2024:3939) Important/Sec. iwl2030-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-46329 (RHSA-2024:3939) Important/Sec. iwl2030-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-27635 (RHSA-2024:3939) Important/Sec. iwl3160-firmware-25.30.13.0-83.el7_9.noarch CVE-2022-36351 (RHSA-2024:3939) Important/Sec. iwl3160-firmware-25.30.13.0-83.el7_9.noarch CVE-2022-38076 (RHSA-2024:3939) Important/Sec. iwl3160-firmware-25.30.13.0-83.el7_9.noarch CVE-2022-40964 (RHSA-2024:3939) Important/Sec. iwl3160-firmware-25.30.13.0-83.el7_9.noarch CVE-2022-46329 (RHSA-2024:3939) Important/Sec. iwl3160-firmware-25.30.13.0-83.el7_9.noarch CVE-2022-27635 (RHSA-2024:3939) Important/Sec. iwl3945-firmware-15.32.2.9-83.el7_9.noarch CVE-2022-36351 (RHSA-2024:3939) Important/Sec. iwl3945-firmware-15.32.2.9-83.el7_9.noarch CVE-2022-38076 (RHSA-2024:3939) Important/Sec. iwl3945-firmware-15.32.2.9-83.el7_9.noarch CVE-2022-40964 (RHSA-2024:3939) Important/Sec. iwl3945-firmware-15.32.2.9-83.el7_9.noarch CVE-2022-46329 (RHSA-2024:3939) Important/Sec. iwl3945-firmware-15.32.2.9-83.el7_9.noarch CVE-2022-27635 (RHSA-2024:3939) Important/Sec. iwl4965-firmware-228.61.2.24-83.el7_9.noarch CVE-2022-36351 (RHSA-2024:3939) Important/Sec. iwl4965-firmware-228.61.2.24-83.el7_9.noarch CVE-2022-38076 (RHSA-2024:3939) Important/Sec. iwl4965-firmware-228.61.2.24-83.el7_9.noarch CVE-2022-40964 (RHSA-2024:3939) Important/Sec. iwl4965-firmware-228.61.2.24-83.el7_9.noarch CVE-2022-46329 (RHSA-2024:3939) Important/Sec. iwl4965-firmware-228.61.2.24-83.el7_9.noarch CVE-2022-27635 (RHSA-2024:3939) Important/Sec. iwl5000-firmware-8.83.5.1_1-83.el7_9.noarch CVE-2022-36351 (RHSA-2024:3939) Important/Sec. iwl5000-firmware-8.83.5.1_1-83.el7_9.noarch CVE-2022-38076 (RHSA-2024:3939) Important/Sec. iwl5000-firmware-8.83.5.1_1-83.el7_9.noarch CVE-2022-40964 (RHSA-2024:3939) Important/Sec. iwl5000-firmware-8.83.5.1_1-83.el7_9.noarch CVE-2022-46329 (RHSA-2024:3939) Important/Sec. iwl5000-firmware-8.83.5.1_1-83.el7_9.noarch CVE-2022-27635 (RHSA-2024:3939) Important/Sec. iwl5150-firmware-8.24.2.2-83.el7_9.noarch CVE-2022-36351 (RHSA-2024:3939) Important/Sec. iwl5150-firmware-8.24.2.2-83.el7_9.noarch CVE-2022-38076 (RHSA-2024:3939) Important/Sec. iwl5150-firmware-8.24.2.2-83.el7_9.noarch CVE-2022-40964 (RHSA-2024:3939) Important/Sec. iwl5150-firmware-8.24.2.2-83.el7_9.noarch CVE-2022-46329 (RHSA-2024:3939) Important/Sec. iwl5150-firmware-8.24.2.2-83.el7_9.noarch CVE-2022-27635 (RHSA-2024:3939) Important/Sec. iwl6000-firmware-9.221.4.1-83.el7_9.noarch CVE-2022-36351 (RHSA-2024:3939) Important/Sec. iwl6000-firmware-9.221.4.1-83.el7_9.noarch CVE-2022-38076 (RHSA-2024:3939) Important/Sec. iwl6000-firmware-9.221.4.1-83.el7_9.noarch CVE-2022-40964 (RHSA-2024:3939) Important/Sec. iwl6000-firmware-9.221.4.1-83.el7_9.noarch CVE-2022-46329 (RHSA-2024:3939) Important/Sec. iwl6000-firmware-9.221.4.1-83.el7_9.noarch CVE-2022-27635 (RHSA-2024:3939) Important/Sec. iwl6000g2a-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-36351 (RHSA-2024:3939) Important/Sec. iwl6000g2a-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-38076 (RHSA-2024:3939) Important/Sec. iwl6000g2a-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-40964 (RHSA-2024:3939) Important/Sec. iwl6000g2a-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-46329 (RHSA-2024:3939) Important/Sec. iwl6000g2a-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-27635 (RHSA-2024:3939) Important/Sec. iwl6000g2b-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-36351 (RHSA-2024:3939) Important/Sec. iwl6000g2b-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-38076 (RHSA-2024:3939) Important/Sec. iwl6000g2b-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-40964 (RHSA-2024:3939) Important/Sec. iwl6000g2b-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-46329 (RHSA-2024:3939) Important/Sec. iwl6000g2b-firmware-18.168.6.1-83.el7_9.noarch CVE-2022-27635 (RHSA-2024:3939) Important/Sec. iwl6050-firmware-41.28.5.1-83.el7_9.noarch CVE-2022-36351 (RHSA-2024:3939) Important/Sec. iwl6050-firmware-41.28.5.1-83.el7_9.noarch CVE-2022-38076 (RHSA-2024:3939) Important/Sec. iwl6050-firmware-41.28.5.1-83.el7_9.noarch CVE-2022-40964 (RHSA-2024:3939) Important/Sec. iwl6050-firmware-41.28.5.1-83.el7_9.noarch CVE-2022-46329 (RHSA-2024:3939) Important/Sec. iwl6050-firmware-41.28.5.1-83.el7_9.noarch CVE-2022-27635 (RHSA-2024:3939) Important/Sec. iwl7260-firmware-25.30.13.0-83.el7_9.noarch CVE-2022-36351 (RHSA-2024:3939) Important/Sec. iwl7260-firmware-25.30.13.0-83.el7_9.noarch CVE-2022-38076 (RHSA-2024:3939) Important/Sec. iwl7260-firmware-25.30.13.0-83.el7_9.noarch CVE-2022-40964 (RHSA-2024:3939) Important/Sec. iwl7260-firmware-25.30.13.0-83.el7_9.noarch CVE-2022-46329 (RHSA-2024:3939) Important/Sec. iwl7260-firmware-25.30.13.0-83.el7_9.noarch CVE-2022-27635 (RHSA-2024:3939) Important/Sec. linux-firmware-20200421-83.git78c0348.el7_9.noarch CVE-2022-36351 (RHSA-2024:3939) Important/Sec. linux-firmware-20200421-83.git78c0348.el7_9.noarch CVE-2022-38076 (RHSA-2024:3939) Important/Sec. linux-firmware-20200421-83.git78c0348.el7_9.noarch CVE-2022-40964 (RHSA-2024:3939) Important/Sec. linux-firmware-20200421-83.git78c0348.el7_9.noarch CVE-2022-46329 (RHSA-2024:3939) Important/Sec. linux-firmware-20200421-83.git78c0348.el7_9.noarch CVE-2024-3183 (RHSA-2024:3760) Important/Sec. python2-ipaclient-4.6.8-5.el7_9.17.noarch CVE-2024-3183 (RHSA-2024:3760) Important/Sec. python2-ipalib-4.6.8-5.el7_9.17.noarch CVE-2024-3183 (RHSA-2024:3760) Important/Sec. python2-ipaserver-4.6.8-5.el7_9.17.noarch
```

## 7.9.24.06.SP30

The release date of the security patch 7.9.24.06.SP30 is 17 June 2024. The estimated run time is around 80 minutes.

The security patch 7.9.24.06.SP30 is based on RHEL 7.9.

Important: If you are using version 1.0.8.2 or earlier, you must upgrade to 1.0.8.3 or 1.0.8.4 first to apply 7.9.24.06.SP30.

Note: If you update to 7.9.24.06.SP30 and then proceed to upgrade to 1.0.8.4, the `ipmitool rpm version` will get downgraded after the upgrade to 1.0.8.4, which is expected.

Note: If after applying the security patch 7.9.24.06.SP30 or greater, you try to upgrade to 1.0.8.4, the upgrade might fail with the following error:

```plaintext
ATTENTION : Errors encountered during upgrade operation ======================================================== Logfile: /var/log/appliance/apupgrade/20231201/apupgrade20231201104707.log Upgrade Command: apupgrade --upgrade --use-version 1.0.8.4_release --upgrade-directory /localrepo --bundle system 1. HpiUpgrader.install Upgrade Detail: Component install for hpi Caller Info:The call was made from 'HpiInstaller.install' on line 54 with file located at '/localrepo/1.0.8.4_release/EXTRACT/system/upgrade/bundle_upgraders/../hpi/hpi_installer.py' Message: Unable to start IPS, System state is Stopped
```

Workaround

1.  Run the following commands:
    1.  On node `e1n1`:
        
        ```plaintext
        ps -ef | grep tftp kill <tftp process ID> docker exec -it <nps container name> bash
        ```
        
    2.  In NPS container as root user:
    3.  In NPS container:
    4.  Once system is started, check the NPS status:
    5.  If the NPS status is online, restart the upgrade.

The list of Red Hat CVEs, which are patched in this release:

```plaintext
CVE-2024-2199 (RHSA-2024:3591) Important/Sec. 389-ds-base-1.3.11.1-5.el7_9.x86_64 CVE-2024-3657 (RHSA-2024:3591) Important/Sec. 389-ds-base-1.3.11.1-5.el7_9.x86_64 CVE-2024-2199 (RHSA-2024:3591) Important/Sec. 389-ds-base-libs-1.3.11.1-5.el7_9.x86_64 CVE-2024-3657 (RHSA-2024:3591) Important/Sec. 389-ds-base-libs-1.3.11.1-5.el7_9.x86_64 CVE-2024-2961 (RHSA-2024:3588) Important/Sec. glibc-2.17-326.el7_9.3.x86_64 CVE-2024-33599 (RHSA-2024:3588) Important/Sec. glibc-2.17-326.el7_9.3.x86_64 CVE-2024-33600 (RHSA-2024:3588) Important/Sec. glibc-2.17-326.el7_9.3.x86_64 CVE-2024-33601 (RHSA-2024:3588) Important/Sec. glibc-2.17-326.el7_9.3.x86_64 CVE-2024-33602 (RHSA-2024:3588) Important/Sec. glibc-2.17-326.el7_9.3.x86_64 CVE-2024-2961 (RHSA-2024:3588) Important/Sec. glibc-common-2.17-326.el7_9.3.x86_64 CVE-2024-33599 (RHSA-2024:3588) Important/Sec. glibc-common-2.17-326.el7_9.3.x86_64 CVE-2024-33600 (RHSA-2024:3588) Important/Sec. glibc-common-2.17-326.el7_9.3.x86_64 CVE-2024-33601 (RHSA-2024:3588) Important/Sec. glibc-common-2.17-326.el7_9.3.x86_64 CVE-2024-33602 (RHSA-2024:3588) Important/Sec. glibc-common-2.17-326.el7_9.3.x86_64 CVE-2024-2961 (RHSA-2024:3588) Important/Sec. glibc-devel-2.17-326.el7_9.3.x86_64 CVE-2024-33599 (RHSA-2024:3588) Important/Sec. glibc-devel-2.17-326.el7_9.3.x86_64 CVE-2024-33600 (RHSA-2024:3588) Important/Sec. glibc-devel-2.17-326.el7_9.3.x86_64 CVE-2024-33601 (RHSA-2024:3588) Important/Sec. glibc-devel-2.17-326.el7_9.3.x86_64 CVE-2024-33602 (RHSA-2024:3588) Important/Sec. glibc-devel-2.17-326.el7_9.3.x86_64 CVE-2024-2961 (RHSA-2024:3588) Important/Sec. glibc-headers-2.17-326.el7_9.3.x86_64 CVE-2024-33599 (RHSA-2024:3588) Important/Sec. glibc-headers-2.17-326.el7_9.3.x86_64 CVE-2024-33600 (RHSA-2024:3588) Important/Sec. glibc-headers-2.17-326.el7_9.3.x86_64 CVE-2024-33601 (RHSA-2024:3588) Important/Sec. glibc-headers-2.17-326.el7_9.3.x86_64 CVE-2024-33602 (RHSA-2024:3588) Important/Sec. glibc-headers-2.17-326.el7_9.3.x86_64 CVE-2024-32487 (RHSA-2024:3669) Important/Sec. less-458-10.el7_9.x86_64 CVE-2024-2961 (RHSA-2024:3588) Important/Sec. nscd-2.17-326.el7_9.3.x86_64 CVE-2024-33599 (RHSA-2024:3588) Important/Sec. nscd-2.17-326.el7_9.3.x86_64 CVE-2024-33600 (RHSA-2024:3588) Important/Sec. nscd-2.17-326.el7_9.3.x86_64 CVE-2024-33601 (RHSA-2024:3588) Important/Sec. nscd-2.17-326.el7_9.3.x86_64 CVE-2024-33602 (RHSA-2024:3588) Important/Sec. nscd-2.17-326.el7_9.3.x86_64
```

## 7.9.24.05.SP29

The release date of the security patch 7.9.24.05.SP29 is 6 June 2024. The estimated run time is around 80 minutes.

The security patch 7.9.24.05.SP29 is based on RHEL 7.9.

Important: If you are using version 1.0.8.2 or earlier, you must upgrade to 1.0.8.3 or 1.0.8.4 first to apply 7.9.24.05.SP29.

Note: If you update to 7.9.24.05.SP29 and then proceed to upgrade to 1.0.8.4, the `ipmitool rpm version` will get downgraded after the upgrade to 1.0.8.4, which is expected.

Note: If after applying the security patch 7.9.24.05.SP29 or greater, you try to upgrade to 1.0.8.4, the upgrade might fail with the following error:

```plaintext
ATTENTION : Errors encountered during upgrade operation ======================================================== Logfile: /var/log/appliance/apupgrade/20231201/apupgrade20231201104707.log Upgrade Command: apupgrade --upgrade --use-version 1.0.8.4_release --upgrade-directory /localrepo --bundle system 1. HpiUpgrader.install Upgrade Detail: Component install for hpi Caller Info:The call was made from 'HpiInstaller.install' on line 54 with file located at '/localrepo/1.0.8.4_release/EXTRACT/system/upgrade/bundle_upgraders/../hpi/hpi_installer.py' Message: Unable to start IPS, System state is Stopped
```

Workaround

1.  Run the following commands:
    1.  On node `e1n1`:
        
        ```plaintext
        ps -ef | grep tftp kill <tftp process ID> docker exec -it <nps container name> bash
        ```
        
    2.  In NPS container as root user:
    3.  In NPS container:
    4.  Once system is started, check the NPS status:
    5.  If the NPS status is online, restart the upgrade.

The list of Red Hat CVEs, which are patched in this release:

```plaintext
CVE-2022-2601 (RHSA-2024:2002) Moderate/Sec. grub2-1:2.02-0.87.el7_9.14.x86_64 CVE-2022-2601 (RHSA-2024:2002) Moderate/Sec. grub2-common-1:2.02-0.87.el7_9.14.noarch CVE-2022-2601 (RHSA-2024:2002) Moderate/Sec. grub2-pc-1:2.02-0.87.el7_9.14.x86_64 CVE-2022-2601 (RHSA-2024:2002) Moderate/Sec. grub2-pc-modules-1:2.02-0.87.el7_9.14.noarch CVE-2022-2601 (RHSA-2024:2002) Moderate/Sec. grub2-tools-1:2.02-0.87.el7_9.14.x86_64 CVE-2022-2601 (RHSA-2024:2002) Moderate/Sec. grub2-tools-extra-1:2.02-0.87.el7_9.14.x86_64 CVE-2022-2601 (RHSA-2024:2002) Moderate/Sec. grub2-tools-minimal-1:2.02-0.87.el7_9.14.x86_64 CVE-2024-21011 (RHSA-2024:1819) Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.412.b08-1.el7_9.x86_64 CVE-2024-21068 (RHSA-2024:1819) Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.412.b08-1.el7_9.x86_64 CVE-2024-21085 (RHSA-2024:1819) Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.412.b08-1.el7_9.x86_64 CVE-2024-21094 (RHSA-2024:1819) Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.412.b08-1.el7_9.x86_64 CVE-2024-21011 (RHSA-2024:1819) Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.412.b08-1.el7_9.x86_64 CVE-2024-21068 (RHSA-2024:1819) Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.412.b08-1.el7_9.x86_64 CVE-2024-21085 (RHSA-2024:1819) Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.412.b08-1.el7_9.x86_64 CVE-2024-21094 (RHSA-2024:1819) Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.412.b08-1.el7_9.x86_64 CVE-2020-36558 (RHSA-2024:2003) Important/Sec. kernel-3.10.0-1160.118.1.el7.x86_64 CVE-2023-2002 (RHSA-2024:2003) Important/Sec. kernel-3.10.0-1160.118.1.el7.x86_64 CVE-2023-4622 (RHSA-2024:2003) Important/Sec. kernel-3.10.0-1160.118.1.el7.x86_64 CVE-2023-4623 (RHSA-2024:2003) Important/Sec. kernel-3.10.0-1160.118.1.el7.x86_64 CVE-2023-25775 (RHSA-2024:2003) Important/Sec. kernel-3.10.0-1160.118.1.el7.x86_64 CVE-2020-36558 (RHSA-2024:2003) Important/Sec. kernel-debuginfo-3.10.0-1160.118.1.el7.x86_64 CVE-2023-2002 (RHSA-2024:2003) Important/Sec. kernel-debuginfo-3.10.0-1160.118.1.el7.x86_64 CVE-2023-4622 (RHSA-2024:2003) Important/Sec. kernel-debuginfo-3.10.0-1160.118.1.el7.x86_64 CVE-2023-4623 (RHSA-2024:2003) Important/Sec. kernel-debuginfo-3.10.0-1160.118.1.el7.x86_64 CVE-2023-25775 (RHSA-2024:2003) Important/Sec. kernel-debuginfo-3.10.0-1160.118.1.el7.x86_64 CVE-2020-36558 (RHSA-2024:2003) Important/Sec. kernel-debuginfo-3.10.0-1160.118.1.el7.x86_64 CVE-2023-2002 (RHSA-2024:2003) Important/Sec. kernel-debuginfo-3.10.0-1160.118.1.el7.x86_64 CVE-2023-4622 (RHSA-2024:2003) Important/Sec. kernel-debuginfo-3.10.0-1160.118.1.el7.x86_64 CVE-2023-4623 (RHSA-2024:2003) Important/Sec. kernel-debuginfo-3.10.0-1160.118.1.el7.x86_64 CVE-2023-25775 (RHSA-2024:2003) Important/Sec. kernel-debuginfo-3.10.0-1160.118.1.el7.x86_64 CVE-2020-36558 (RHSA-2024:2003) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.118.1.el7.x86_64 CVE-2023-2002 (RHSA-2024:2003) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.118.1.el7.x86_64 CVE-2023-4622 (RHSA-2024:2003) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.118.1.el7.x86_64 CVE-2023-4623 (RHSA-2024:2003) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.118.1.el7.x86_64 CVE-2023-25775 (RHSA-2024:2003) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.118.1.el7.x86_64 CVE-2020-36558 (RHSA-2024:2003) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.118.1.el7.x86_64 CVE-2023-2002 (RHSA-2024:2003) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.118.1.el7.x86_64 CVE-2023-4622 (RHSA-2024:2003) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.118.1.el7.x86_64 CVE-2023-4623 (RHSA-2024:2003) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.118.1.el7.x86_64 CVE-2023-25775 (RHSA-2024:2003) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.118.1.el7.x86_64 CVE-2020-36558 (RHSA-2024:2003) Important/Sec. kernel-devel-3.10.0-1160.118.1.el7.x86_64 CVE-2023-2002 (RHSA-2024:2003) Important/Sec. kernel-devel-3.10.0-1160.118.1.el7.x86_64 CVE-2023-4622 (RHSA-2024:2003) Important/Sec. kernel-devel-3.10.0-1160.118.1.el7.x86_64 CVE-2023-4623 (RHSA-2024:2003) Important/Sec. kernel-devel-3.10.0-1160.118.1.el7.x86_64 CVE-2023-25775 (RHSA-2024:2003) Important/Sec. kernel-devel-3.10.0-1160.118.1.el7.x86_64 CVE-2020-36558 (RHSA-2024:2003) Important/Sec. kernel-headers-3.10.0-1160.118.1.el7.x86_64 CVE-2023-2002 (RHSA-2024:2003) Important/Sec. kernel-headers-3.10.0-1160.118.1.el7.x86_64 CVE-2023-4622 (RHSA-2024:2003) Important/Sec. kernel-headers-3.10.0-1160.118.1.el7.x86_64 CVE-2023-4623 (RHSA-2024:2003) Important/Sec. kernel-headers-3.10.0-1160.118.1.el7.x86_64 CVE-2023-25775 (RHSA-2024:2003) Important/Sec. kernel-headers-3.10.0-1160.118.1.el7.x86_64 CVE-2020-36558 (RHSA-2024:2003) Important/Sec. kernel-tools-3.10.0-1160.118.1.el7.x86_64 CVE-2023-2002 (RHSA-2024:2003) Important/Sec. kernel-tools-3.10.0-1160.118.1.el7.x86_64 CVE-2023-4622 (RHSA-2024:2003) Important/Sec. kernel-tools-3.10.0-1160.118.1.el7.x86_64 CVE-2023-4623 (RHSA-2024:2003) Important/Sec. kernel-tools-3.10.0-1160.118.1.el7.x86_64 CVE-2023-25775 (RHSA-2024:2003) Important/Sec. kernel-tools-3.10.0-1160.118.1.el7.x86_64 CVE-2020-36558 (RHSA-2024:2003) Important/Sec. kernel-tools-libs-3.10.0-1160.118.1.el7.x86_64 CVE-2023-2002 (RHSA-2024:2003) Important/Sec. kernel-tools-libs-3.10.0-1160.118.1.el7.x86_64 CVE-2023-4622 (RHSA-2024:2003) Important/Sec. kernel-tools-libs-3.10.0-1160.118.1.el7.x86_64 CVE-2023-4623 (RHSA-2024:2003) Important/Sec. kernel-tools-libs-3.10.0-1160.118.1.el7.x86_64 CVE-2023-25775 (RHSA-2024:2003) Important/Sec. kernel-tools-libs-3.10.0-1160.118.1.el7.x86_64 CVE-2023-40546 (RHSA-2024:1959) Important/Sec. mokutil-15.8-1.el7.x86_64 CVE-2023-40547 (RHSA-2024:1959) Important/Sec. mokutil-15.8-1.el7.x86_64 CVE-2023-40548 (RHSA-2024:1959) Important/Sec. mokutil-15.8-1.el7.x86_64 CVE-2023-40549 (RHSA-2024:1959) Important/Sec. mokutil-15.8-1.el7.x86_64 CVE-2023-40550 (RHSA-2024:1959) Important/Sec. mokutil-15.8-1.el7.x86_64 CVE-2023-40551 (RHSA-2024:1959) Important/Sec. mokutil-15.8-1.el7.x86_64 CVE-2020-36558 (RHSA-2024:2003) Important/Sec. perf-3.10.0-1160.118.1.el7.x86_64 CVE-2023-2002 (RHSA-2024:2003) Important/Sec. perf-3.10.0-1160.118.1.el7.x86_64 CVE-2023-4622 (RHSA-2024:2003) Important/Sec. perf-3.10.0-1160.118.1.el7.x86_64 CVE-2023-4623 (RHSA-2024:2003) Important/Sec. perf-3.10.0-1160.118.1.el7.x86_64 CVE-2023-25775 (RHSA-2024:2003) Important/Sec. perf-3.10.0-1160.118.1.el7.x86_64 CVE-2020-36558 (RHSA-2024:2003) Important/Sec. python-perf-3.10.0-1160.118.1.el7.x86_64 CVE-2023-2002 (RHSA-2024:2003) Important/Sec. python-perf-3.10.0-1160.118.1.el7.x86_64 CVE-2023-4622 (RHSA-2024:2003) Important/Sec. python-perf-3.10.0-1160.118.1.el7.x86_64 CVE-2023-4623 (RHSA-2024:2003) Important/Sec. python-perf-3.10.0-1160.118.1.el7.x86_64 CVE-2023-25775 (RHSA-2024:2003) Important/Sec. python-perf-3.10.0-1160.118.1.el7.x86_64
```

## 7.9.24.04.SP28

The release date of the security patch 7.9.24.04.SP28 is 25 April 2024. The estimated run time is around 80 minutes.

The security patch 7.9.24.04.SP28 is based on RHEL 7.9.

Important: If you are using version 1.0.8.2 or earlier, you must upgrade to 1.0.8.3 or 1.0.8.4 first to apply 7.9.24.04.SP28.

Note: If you update to 7.9.24.04.SP28 and then proceed to upgrade to 1.0.8.4, the `ipmitool rpm version` will get downgraded after the upgrade to 1.0.8.4, which is expected.

Note: If the `apusermgmt` commands do not work after applying the security patch 7.9.24.04.SP28, contact IBM support or apply 7.9.24.05.SP29 or later.

Note: If after applying the security patch 7.9.24.03.SP28 or greater, you try to upgrade to 1.0.8.4, the upgrade might fail with the following error:

```plaintext
ATTENTION : Errors encountered during upgrade operation ======================================================== Logfile: /var/log/appliance/apupgrade/20231201/apupgrade20231201104707.log Upgrade Command: apupgrade --upgrade --use-version 1.0.8.4_release --upgrade-directory /localrepo --bundle system 1. HpiUpgrader.install Upgrade Detail: Component install for hpi Caller Info:The call was made from 'HpiInstaller.install' on line 54 with file located at '/localrepo/1.0.8.4_release/EXTRACT/system/upgrade/bundle_upgraders/../hpi/hpi_installer.py' Message: Unable to start IPS, System state is Stopped
```

Workaround

1.  Run the following commands:
    1.  On node `e1n1`:
        
        ```plaintext
        ps -ef | grep tftp kill <tftp process ID> docker exec -it <nps container name> bash
        ```
        
    2.  In NPS container as root user:
    3.  In NPS container:
    4.  Once system is started, check the NPS status:
    5.  If the NPS status is online, restart the upgrade.

Note: If the parameter /boot value exceeds 100% capacity after applying the security patch 7.9.24.04.SP28, the following alerts might be displayed:

```plaintext
[root@NPS-SAND-02-e1n1: ~]$ df -h /boot Filesystem Size Used Avail Use% Mounted on /dev/sda1 190M 177M 0 100% /boot | 3644 | 2024-03-25 20:37:29 | STORAGE_UTILIZATION | 901: Storage utilization above threshold | sw://fs.sda1/enclosure1.node1 | CRITICAL | N/A | | 3645 | 2024-03-25 20:37:45 | STORAGE_UTILIZATION | 901: Storage utilization above threshold | sw://fs.sda1/enclosure1.node4 | CRITICAL | N/A | | 3646 | 2024-03-25 20:37:45 | STORAGE_UTILIZATION | 901: Storage utilization above threshold | sw://fs.sda1/enclosure1.node3 | CRITICAL | N/A | | 3647 | 2024-03-25 20:37:45 | STORAGE_UTILIZATION | 901: Storage utilization above threshold | sw://fs.sda1/enclosure1.node2 | CRITICAL | N/A |
```

Workaround:

1.  Run the following command from all non SPU nodes to check the /boot parameter value:
    
    Example:
    
    ```plaintext
    df -h /boot Filesystem Size Used Avail Use% Mounted on /dev/sda1 190M 177M 0 100% /boot
    ```
    
2.  If the /boot parameter shows use of 95% or greater value, run the following commands on all non SPU nodes to free up storage in /boot.
    1.  Run the following command to check which kernel versions are present in each non SPU node:
        
        ```plaintext
        awk -F\' /^menuentry/{print\$2} /etc/grub2.cfg
        ```
        
        Example:
        
        ```plaintext
        Eg - # awk -F\' /^menuentry/{print\$2} /etc/grub2.cfg Red Hat Enterprise Linux Server, with Linux 3.10.0-123.el7.x86_64 <=== Entry 0 Red Hat Enterprise Linux Server, with Linux 3.10.0-123.9.2.el7.x86_64 <=== Entry 1 Red Hat Enterprise Linux Server, with Linux 3.10.0-123.6.3.el7.x86_64 <=== Entry 2 Red Hat Enterprise Linux Server, with Linux 0-rescue-b03fd2e1e769493994c88 b8da4257178 <=== Entry 3
        ```
        
    2.  Run the following command to find the default kernel version set:
        
        ```plaintext
        cat /boot/grub2/grubenv |grep saved
        ```
        
        Example:
        
        ```plaintext
        Eg - cat /boot/grub2/grubenv |grep saved saved_entry=Red Hat Enterprise Linux Server, with Linux 3.10.0-123.9.2.el7.x86_64
        ```
        
    3.  If the kernel version is the latest, proceed to step 3. If not, perform steps 2.d to 2.j to change the default kernel and uninstall the older version.
    4.  Check the current kernel installed, as in step 2.a.
        
        ```plaintext
        # awk -F\' /^menuentry/{print\$2} /etc/grub2.cfg Red Hat Enterprise Linux Server, with Linux 3.10.0-123.el7.x86_64 <=== Entry 0 Red Hat Enterprise Linux Server, with Linux 3.10.0-123.9.2.el7.x86_64 <=== Entry 1 Red Hat Enterprise Linux Server, with Linux 3.10.0-123.6.3.el7.x86_64 <=== Entry 2 Red Hat Enterprise Linux Server, with Linux 0-rescue-b03fd2e1e769493994c88 b8da4257178 <=== Entry 3
        ```
        
    5.  Set the default kernel based on the numbers in the previous steps:
    6.  Check that the default kernel is correctly set:
        
        ```plaintext
        # cat /boot/grub2/grubenv |grep saved saved_entry=1
        ```
        
    7.  Run the following commands to reboot the node:
        
        Alternatively, via `ipmitool`:
        
        -   For Dell system
            
            ```plaintext
            ipmitool -I lanplus -H <node>bmc -U root -P calvin power on ipmitool -I lanplus -H <node>bmc -U root -P calvin power off
            ```
            
        -   For Lenovo system
            
            ```plaintext
            ipmitool -H <node>bmc -U USERID -P PASSW0RD -I lanplus power on ipmitool -H <node>bmcbmc -U USERID -P PASSW0RD -I lanplus power off
            ```
            
        
    8.  After the reboot, run the following command to check the current kernel:
        
        ```plaintext
        #[root@sail81-t07-n3 ~]# uname -r 3.10.0-1160.102.1.el7.ppc64le
        ```
        
    9.  Run the following command to remove the old kernel:
        
        ```plaintext
        # sudo package-cleanup --oldkernels --count=1
        ```
        
    10.  Run the following command to check the default kernel and the list of currently installed kernels:
        
        ```plaintext
        #cat /boot/grub2/grubenv |grep saved saved_entry=1
        ```
        
        Note: This saved entry value should point to the kernel that is currently running. This needs to be verified because the list of kernels provided by the following command will be shuffled after the removal of the old kernel:
        
        ```plaintext
        awk -F\' /^menuentry/{print\$2} /etc/grub2.cfg
        ```
        
        If not, after the next reboot, the operating kernel has to be changed to the default kernel. If the current kernel and the default-saved item do not match, run the following command with the correct value from the list of kernels:
        
        ```plaintext
        commandgrub2-set-default 1
        ```
        
        Skip the step 3.
        
3.  Run the following command from all non SPU nodes:
    
    ```plaintext
    package-cleanup --oldkernels --count=1
    ```
    
    Note: When the older kernel is removed, the `grub2.cfg` list (In Step 2.a) will get shuffled. Make sure that the `grubenv` (Step 2.b) points to the available current version.
    
    If this error was encountered during the security patch upgrade, then follow the procedures above and continue the upgrade.
    

The list of Red Hat CVEs, which are patched in this release:

```plaintext
CVE-2023-5455 (RHSA-2024:0145) Moderate/Sec. ipa-debuginfo-4.6.8-5.el7_9.16.x86_64 CVE-2022-42896 (RHSA-2024:1249) Important/Sec. kernel-3.10.0-1160.114.2.el7.x86_64 CVE-2023-4921 (RHSA-2024:1249) Important/Sec. kernel-3.10.0-1160.114.2.el7.x86_64 CVE-2023-38409 (RHSA-2024:1249) Important/Sec. kernel-3.10.0-1160.114.2.el7.x86_64 CVE-2023-45871 (RHSA-2024:1249) Important/Sec. kernel-3.10.0-1160.114.2.el7.x86_64 CVE-2024-1086 (RHSA-2024:1249) Important/Sec. kernel-3.10.0-1160.114.2.el7.x86_64 CVE-2024-26602 (RHSA-2024:1249) Important/Sec. kernel-3.10.0-1160.114.2.el7.x86_64 CVE-2022-42896 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-3.10.0-1160.114.2.el7.x86_64 CVE-2023-4921 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-3.10.0-1160.114.2.el7.x86_64 CVE-2023-38409 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-3.10.0-1160.114.2.el7.x86_64 CVE-2023-45871 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-3.10.0-1160.114.2.el7.x86_64 CVE-2024-1086 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-3.10.0-1160.114.2.el7.x86_64 CVE-2024-26602 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-3.10.0-1160.114.2.el7.x86_64 CVE-2022-42896 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-3.10.0-1160.114.2.el7.x86_64 CVE-2023-4921 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-3.10.0-1160.114.2.el7.x86_64 CVE-2023-38409 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-3.10.0-1160.114.2.el7.x86_64 CVE-2023-45871 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-3.10.0-1160.114.2.el7.x86_64 CVE-2024-1086 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-3.10.0-1160.114.2.el7.x86_64 CVE-2024-26602 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-3.10.0-1160.114.2.el7.x86_64 CVE-2022-42896 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.114.2.el7.x86_64 CVE-2023-4921 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.114.2.el7.x86_64 CVE-2023-38409 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.114.2.el7.x86_64 CVE-2023-45871 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.114.2.el7.x86_64 CVE-2024-1086 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.114.2.el7.x86_64 CVE-2024-26602 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.114.2.el7.x86_64 CVE-2022-42896 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.114.2.el7.x86_64 CVE-2023-4921 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.114.2.el7.x86_64 CVE-2023-38409 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.114.2.el7.x86_64 CVE-2023-45871 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.114.2.el7.x86_64 CVE-2024-1086 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.114.2.el7.x86_64 CVE-2024-26602 (RHSA-2024:1249) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.114.2.el7.x86_64 CVE-2022-42896 (RHSA-2024:1249) Important/Sec. kernel-devel-3.10.0-1160.114.2.el7.x86_64 CVE-2023-4921 (RHSA-2024:1249) Important/Sec. kernel-devel-3.10.0-1160.114.2.el7.x86_64 CVE-2023-38409 (RHSA-2024:1249) Important/Sec. kernel-devel-3.10.0-1160.114.2.el7.x86_64 CVE-2023-45871 (RHSA-2024:1249) Important/Sec. kernel-devel-3.10.0-1160.114.2.el7.x86_64 CVE-2024-1086 (RHSA-2024:1249) Important/Sec. kernel-devel-3.10.0-1160.114.2.el7.x86_64
```

## 7.9.24.03.SP27

The release date of the security patch 7.9.24.03.SP27 is 9 April 2024. The estimated run time is around 80 minutes.

The security patch 7.9.24.03.SP27 is based on RHEL 7.9.

Important: If you are using version 1.0.8.2 or earlier, you must upgrade to 1.0.8.3 or 1.0.8.4 first to apply 7.9.24.03.SP27.

Note: If you update to 7.9.24.03.SP27 and then proceeds to upgrade to 1.0.8.4, the `ipmitool rpm version` will get downgraded after the upgrade to 1.0.8.4, which is expected.

Note: If the `apusermgmt` commands do not work after applying the security patch 7.9.24.03.SP27, contact IBM support or apply 7.9.24.05.SP29 or later.

Note: If after applying the security patch 7.9.24.03.SP27 or greater, you try to upgrade to 1.0.8.4, the upgrade might fail with the following error:

```plaintext
ATTENTION : Errors encountered during upgrade operation ======================================================== Logfile: /var/log/appliance/apupgrade/20231201/apupgrade20231201104707.log Upgrade Command: apupgrade --upgrade --use-version 1.0.8.4_release --upgrade-directory /localrepo --bundle system 1. HpiUpgrader.install Upgrade Detail: Component install for hpi Caller Info:The call was made from 'HpiInstaller.install' on line 54 with file located at '/localrepo/1.0.8.4_release/EXTRACT/system/upgrade/bundle_upgraders/../hpi/hpi_installer.py' Message: Unable to start IPS, System state is Stopped
```

Workaround

1.  Run the following commands:
    1.  On node `e1n1`:
        
        ```plaintext
        ps -ef | grep tftp kill <tftp process ID> docker exec -it <nps container name> bash
        ```
        
    2.  In NPS container as root user:
    3.  In NPS container:
    4.  Once system is started, check the NPS status:
    5.  If the NPS status is online, restart the upgrade.

Note: If the parameter /boot value exceeds 100% capacity after applying the security patch 7.9.24.03.SP27, the following alerts might be displayed:

```plaintext
[root@NPS-SAND-02-e1n1: ~]$ df -h /boot Filesystem Size Used Avail Use% Mounted on /dev/sda1 190M 177M 0 100% /boot | 3644 | 2024-03-25 20:37:29 | STORAGE_UTILIZATION | 901: Storage utilization above threshold | sw://fs.sda1/enclosure1.node1 | CRITICAL | N/A | | 3645 | 2024-03-25 20:37:45 | STORAGE_UTILIZATION | 901: Storage utilization above threshold | sw://fs.sda1/enclosure1.node4 | CRITICAL | N/A | | 3646 | 2024-03-25 20:37:45 | STORAGE_UTILIZATION | 901: Storage utilization above threshold | sw://fs.sda1/enclosure1.node3 | CRITICAL | N/A | | 3647 | 2024-03-25 20:37:45 | STORAGE_UTILIZATION | 901: Storage utilization above threshold | sw://fs.sda1/enclosure1.node2 | CRITICAL | N/A |
```

Workaround:

1.  Run the following command from all non SPU nodes to check the /boot parameter value:
    
    Example:
    
    ```plaintext
    df -h /boot Filesystem Size Used Avail Use% Mounted on /dev/sda1 190M 177M 0 100% /boot
    ```
    
2.  If the /boot parameter shows use of 95% or greater value, run the following commands on all non SPU nodes to free up storage in /boot.
    1.  Run the following command to check which kernel versions are present in each non SPU node:
        
        ```plaintext
        awk -F\' /^menuentry/{print\$2} /etc/grub2.cfg
        ```
        
        Example:
        
        ```plaintext
        Eg - # awk -F\' /^menuentry/{print\$2} /etc/grub2.cfg Red Hat Enterprise Linux Server, with Linux 3.10.0-123.el7.x86_64 <=== Entry 0 Red Hat Enterprise Linux Server, with Linux 3.10.0-123.9.2.el7.x86_64 <=== Entry 1 Red Hat Enterprise Linux Server, with Linux 3.10.0-123.6.3.el7.x86_64 <=== Entry 2 Red Hat Enterprise Linux Server, with Linux 0-rescue-b03fd2e1e769493994c88 b8da4257178 <=== Entry 3
        ```
        
    2.  Run the following command to find the default kernel version set:
        
        ```plaintext
        cat /boot/grub2/grubenv |grep saved
        ```
        
        Example:
        
        ```plaintext
        Eg - cat /boot/grub2/grubenv |grep saved saved_entry=Red Hat Enterprise Linux Server, with Linux 3.10.0-123.9.2.el7.x86_64
        ```
        
    3.  If the kernel version is the latest, proceed to step 3. If not, perform steps 2.d to 2.j to change the default kernel and uninstall the older version.
    4.  Check the current kernel installed, as in step 2.a.
        
        ```plaintext
        # awk -F\' /^menuentry/{print\$2} /etc/grub2.cfg Red Hat Enterprise Linux Server, with Linux 3.10.0-123.el7.x86_64 <=== Entry 0 Red Hat Enterprise Linux Server, with Linux 3.10.0-123.9.2.el7.x86_64 <=== Entry 1 Red Hat Enterprise Linux Server, with Linux 3.10.0-123.6.3.el7.x86_64 <=== Entry 2 Red Hat Enterprise Linux Server, with Linux 0-rescue-b03fd2e1e769493994c88 b8da4257178 <=== Entry 3
        ```
        
    5.  Set the default kernel based on the numbers in the previous steps:
    6.  Check that the default kernel is correctly set:
        
        ```plaintext
        # cat /boot/grub2/grubenv |grep saved saved_entry=1
        ```
        
    7.  Run the following commands to reboot the node:
        
        Alternatively, via `ipmitool`:
        
        -   For Dell system
            
            ```plaintext
            ipmitool -I lanplus -H <node>bmc -U root -P calvin power on ipmitool -I lanplus -H <node>bmc -U root -P calvin power off
            ```
            
        -   For Lenovo system
            
            ```plaintext
            ipmitool -H <node>bmc -U USERID -P PASSW0RD -I lanplus power on ipmitool -H <node>bmcbmc -U USERID -P PASSW0RD -I lanplus power off
            ```
            
        
    8.  After the reboot, run the following command to check the current kernel:
        
        ```plaintext
        #[root@sail81-t07-n3 ~]# uname -r 3.10.0-1160.102.1.el7.ppc64le
        ```
        
    9.  Run the following command to remove the old kernel:
        
        ```plaintext
        # sudo package-cleanup --oldkernels --count=1
        ```
        
    10.  Run the following command to check the default kernel and the list of currently installed kernels:
        
        ```plaintext
        #cat /boot/grub2/grubenv |grep saved saved_entry=1
        ```
        
        Note: This saved entry value should point to the kernel that is currently running. This needs to be verified because the list of kernels provided by the following command will be shuffled after the removal of the old kernel:
        
        ```plaintext
        awk -F\' /^menuentry/{print\$2} /etc/grub2.cfg
        ```
        
        If not, after the next reboot, the operating kernel has to be changed to the default kernel. If the current kernel and the default-saved item do not match, run the following command with the correct value from the list of kernels:
        
        ```plaintext
        commandgrub2-set-default 1
        ```
        
        Skip the step 3.
        
3.  Run the following command from all non SPU nodes:
    
    ```plaintext
    package-cleanup --oldkernels --count=1
    ```
    
    Note: When the older kernel is removed, the `grub2.cfg` list (In Step 2.a) will get shuffled. Make sure that the `grubenv` (Step 2.b) points to the available current version.
    
    If this error was encountered during the security patch upgrade, then follow the procedures above and continue the upgrade.
    

The list of Red Hat CVEs, which are patched in this release:

```plaintext
CVE-2023-5455 (RHSA-2024:0145) Moderate/Sec. ipa-client-4.6.8-5.el7_9.16.x86_64 CVE-2023-5455 (RHSA-2024:0145) Moderate/Sec. ipa-client-common-4.6.8-5.el7_9.16.noarch CVE-2023-5455 (RHSA-2024:0145) Moderate/Sec. ipa-common-4.6.8-5.el7_9.16.noarch CVE-2023-5455 (RHSA-2024:0145) Moderate/Sec. ipa-python-compat-4.6.8-5.el7_9.16.noarch CVE-2023-5455 (RHSA-2024:0145) Moderate/Sec. ipa-server-4.6.8-5.el7_9.16.x86_64 CVE-2023-5455 (RHSA-2024:0145) Moderate/Sec. ipa-server-common-4.6.8-5.el7_9.16.noarch CVE-2023-5455 (RHSA-2024:0145) Moderate/Sec. ipa-server-dns-4.6.8-5.el7_9.16.noarch CVE-2023-5455 (RHSA-2024:0145) Moderate/Sec. ipa-server-trust-ad-4.6.8-5.el7_9.16.x86_64 CVE-2023-20592 (RHSA-2024:0753) Moderate/Sec. iwl100-firmware-39.31.5.1-82.el7_9.noarch CVE-2023-20592 (RHSA-2024:0753) Moderate/Sec. iwl1000-firmware-1:39.31.5.1-82.el7_9.noarch CVE-2023-20592 (RHSA-2024:0753) Moderate/Sec. iwl105-firmware-18.168.6.1-82.el7_9.noarch CVE-2023-20592 (RHSA-2024:0753) Moderate/Sec. iwl135-firmware-18.168.6.1-82.el7_9.noarch CVE-2023-20592 (RHSA-2024:0753) Moderate/Sec. iwl2000-firmware-18.168.6.1-82.el7_9.noarch CVE-2023-20592 (RHSA-2024:0753) Moderate/Sec. iwl2030-firmware-18.168.6.1-82.el7_9.noarch CVE-2023-20592 (RHSA-2024:0753) Moderate/Sec. iwl3160-firmware-25.30.13.0-82.el7_9.noarch CVE-2023-20592 (RHSA-2024:0753) Moderate/Sec. iwl3945-firmware-15.32.2.9-82.el7_9.noarch CVE-2023-20592 (RHSA-2024:0753) Moderate/Sec. iwl4965-firmware-228.61.2.24-82.el7_9.noarch CVE-2023-20592 (RHSA-2024:0753) Moderate/Sec. iwl5000-firmware-8.83.5.1_1-82.el7_9.noarch CVE-2023-20592 (RHSA-2024:0753) Moderate/Sec. iwl5150-firmware-8.24.2.2-82.el7_9.noarch CVE-2023-20592 (RHSA-2024:0753) Moderate/Sec. iwl6000-firmware-9.221.4.1-82.el7_9.noarch CVE-2023-20592 (RHSA-2024:0753) Moderate/Sec. iwl6000g2a-firmware-18.168.6.1-82.el7_9.noarch CVE-2023-20592 (RHSA-2024:0753) Moderate/Sec. iwl6000g2b-firmware-18.168.6.1-82.el7_9.noarch CVE-2023-20592 (RHSA-2024:0753) Moderate/Sec. iwl6050-firmware-41.28.5.1-82.el7_9.noarch CVE-2023-20592 (RHSA-2024:0753) Moderate/Sec. iwl7260-firmware-25.30.13.0-82.el7_9.noarch CVE-2024-20918 (RHSA-2024:0223) Important/Sec. java-1.8.0-openjdk-1:1.8.0.402.b06-1.el7_9.x86_64 CVE-2024-20919 (RHSA-2024:0223) Important/Sec. java-1.8.0-openjdk-1:1.8.0.402.b06-1.el7_9.x86_64 CVE-2024-20921 (RHSA-2024:0223) Important/Sec. java-1.8.0-openjdk-1:1.8.0.402.b06-1.el7_9.x86_64 CVE-2024-20926 (RHSA-2024:0223) Important/Sec. java-1.8.0-openjdk-1:1.8.0.402.b06-1.el7_9.x86_64 CVE-2024-20945 (RHSA-2024:0223) Important/Sec. java-1.8.0-openjdk-1:1.8.0.402.b06-1.el7_9.x86_64 CVE-2024-20952 (RHSA-2024:0223) Important/Sec. java-1.8.0-openjdk-1:1.8.0.402.b06-1.el7_9.x86_64 CVE-2024-20918 (RHSA-2024:0223) Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.402.b06-1.el7_9.x86_64 CVE-2024-20919 (RHSA-2024:0223) Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.402.b06-1.el7_9.x86_64 CVE-2024-20921 (RHSA-2024:0223) Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.402.b06-1.el7_9.x86_64 CVE-2024-20926 (RHSA-2024:0223) Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.402.b06-1.el7_9.x86_64 CVE-2024-20945 (RHSA-2024:0223) Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.402.b06-1.el7_9.x86_64 CVE-2024-20952 (RHSA-2024:0223) Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.402.b06-1.el7_9.x86_64 CVE-2023-42753 (RHSA-2024:0346) Important/Sec. kernel-3.10.0-1160.108.1.el7.x86_64 CVE-2023-42753 (RHSA-2024:0346) Important/Sec. kernel-debuginfo-3.10.0-1160.108.1.el7.x86_64 CVE-2023-42753 (RHSA-2024:0346) Important/Sec. kernel-debuginfo-3.10.0-1160.108.1.el7.x86_64 CVE-2023-42753 (RHSA-2024:0346) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.108.1.el7.x86_64 CVE-2023-42753 (RHSA-2024:0346) Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.108.1.el7.x86_64 CVE-2023-42753 (RHSA-2024:0346) Important/Sec. kernel-devel-3.10.0-1160.108.1.el7.x86_64 CVE-2023-42753 (RHSA-2024:0346) Important/Sec. kernel-headers-3.10.0-1160.108.1.el7.x86_64 CVE-2023-42753 (RHSA-2024:0346) Important/Sec. kernel-tools-3.10.0-1160.108.1.el7.x86_64 CVE-2023-42753 (RHSA-2024:0346) Important/Sec. kernel-tools-libs-3.10.0-1160.108.1.el7.x86_64 CVE-2023-20592 (RHSA-2024:0753) Moderate/Sec. linux-firmware-20200421-82.git78c0348.el7_9.noarch CVE-2023-42753 (RHSA-2024:0346) Important/Sec. perf-3.10.0-1160.108.1.el7.x86_64 CVE-2023-42753 (RHSA-2024:0346) Important/Sec. python-perf-3.10.0-1160.108.1.el7.x86_64 CVE-2023-44271 (RHSA-2024:0345) Moderate/Sec. python-pillow-2.0.0-24.gitd1c6db8.el7_9.x86_64 CVE-2023-5455 (RHSA-2024:0145) Moderate/Sec. python2-ipaclient-4.6.8-5.el7_9.16.noarch CVE-2023-5455 (RHSA-2024:0145) Moderate/Sec. python2-ipalib-4.6.8-5.el7_9.16.noarch CVE-2023-5455 (RHSA-2024:0145) Moderate/Sec. python2-ipaserver-4.6.8-5.el7_9.16.noarch CVE-2023-50447 (RHSA-2024:0857) Important/Sec. python-pillow-2.0.0-25.gitd1c6db8.el7_9.x86_64
```

## 7.9.24.01.SP26

The release date of the security patch 7.9.24.01.SP26 is 13 February 2024. The estimated run time is around 80 minutes.

The 7.9.24.01.SP26 patch is based on RHEL 7.9, and it can only be installed on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x and 1.0.8.x.

Important: If you are using version 1.0.8, you must upgrade to 1.0.8.0 IF2 first to apply 7.9.24.01.SP26.

Restriction: After applying 7.9.24.01.SP26, you can upgrade Cloud Pak for Data System to version 1.0.8.4 or later versions only.

Note: The ap version -s might not show all of the docker upgrade component versions after applying 7.9.24.01.SP26 on Cloud Pak for Data System 1.0.7.8 or 1.0.7.8 IF2. This happens if Python 2 is installed.

Workaround

Run the ap version -d command.

Note: If the parameter /boot value exceeds 100% capacity after applying the security patch 7.9.24.01.SP26, the following alerts might be displayed:

```plaintext
[root@NPS-SAND-02-e1n1: ~]$ df -h /boot Filesystem Size Used Avail Use% Mounted on /dev/sda1 190M 177M 0 100% /boot | 3644 | 2024-03-25 20:37:29 | STORAGE_UTILIZATION | 901: Storage utilization above threshold | sw://fs.sda1/enclosure1.node1 | CRITICAL | N/A | | 3645 | 2024-03-25 20:37:45 | STORAGE_UTILIZATION | 901: Storage utilization above threshold | sw://fs.sda1/enclosure1.node4 | CRITICAL | N/A | | 3646 | 2024-03-25 20:37:45 | STORAGE_UTILIZATION | 901: Storage utilization above threshold | sw://fs.sda1/enclosure1.node3 | CRITICAL | N/A | | 3647 | 2024-03-25 20:37:45 | STORAGE_UTILIZATION | 901: Storage utilization above threshold | sw://fs.sda1/enclosure1.node2 | CRITICAL | N/A |
```

Workaround:

1.  Run the following command from all non SPU nodes to check the /boot parameter value:
    
    Example:
    
    ```plaintext
    df -h /boot Filesystem Size Used Avail Use% Mounted on /dev/sda1 190M 177M 0 100% /boot
    ```
    
2.  If the /boot parameter shows use of 95% or greater value, run the following commands on all non SPU nodes to free up storage in /boot.
    1.  Run the following command to check which kernel versions are present in each non SPU node:
        
        ```plaintext
        awk -F\' /^menuentry/{print\$2} /etc/grub2.cfg
        ```
        
        Example:
        
        ```plaintext
        Eg - # awk -F\' /^menuentry/{print\$2} /etc/grub2.cfg Red Hat Enterprise Linux Server, with Linux 3.10.0-123.el7.x86_64 <=== Entry 0 Red Hat Enterprise Linux Server, with Linux 3.10.0-123.9.2.el7.x86_64 <=== Entry 1 Red Hat Enterprise Linux Server, with Linux 3.10.0-123.6.3.el7.x86_64 <=== Entry 2 Red Hat Enterprise Linux Server, with Linux 0-rescue-b03fd2e1e769493994c88 b8da4257178 <=== Entry 3
        ```
        
    2.  Run the following command to find the default kernel version set:
        
        ```plaintext
        cat /boot/grub2/grubenv |grep saved
        ```
        
        Example:
        
        ```plaintext
        Eg - cat /boot/grub2/grubenv |grep saved saved_entry=Red Hat Enterprise Linux Server, with Linux 3.10.0-123.9.2.el7.x86_64
        ```
        
    3.  If the kernel version is the latest, proceed to step 3. If not, perform steps 2.d to 2.j to change the default kernel and uninstall the older version.
    4.  Check the current kernel installed, as in step 2.a.
        
        ```plaintext
        # awk -F\' /^menuentry/{print\$2} /etc/grub2.cfg Red Hat Enterprise Linux Server, with Linux 3.10.0-123.el7.x86_64 <=== Entry 0 Red Hat Enterprise Linux Server, with Linux 3.10.0-123.9.2.el7.x86_64 <=== Entry 1 Red Hat Enterprise Linux Server, with Linux 3.10.0-123.6.3.el7.x86_64 <=== Entry 2 Red Hat Enterprise Linux Server, with Linux 0-rescue-b03fd2e1e769493994c88 b8da4257178 <=== Entry 3
        ```
        
    5.  Set the default kernel based on the numbers in the previous steps:
    6.  Check that the default kernel is correctly set:
        
        ```plaintext
        # cat /boot/grub2/grubenv |grep saved saved_entry=1
        ```
        
    7.  Run the following commands to reboot the node:
        
        Alternatively, via `ipmitool`:
        
        -   For Dell system
            
            ```plaintext
            ipmitool -I lanplus -H <node>bmc -U root -P calvin power on ipmitool -I lanplus -H <node>bmc -U root -P calvin power off
            ```
            
        -   For Lenovo system
            
            ```plaintext
            ipmitool -H <node>bmc -U USERID -P PASSW0RD -I lanplus power on ipmitool -H <node>bmcbmc -U USERID -P PASSW0RD -I lanplus power off
            ```
            
        
    8.  After the reboot, run the following command to check the current kernel:
        
        ```plaintext
        #[root@sail81-t07-n3 ~]# uname -r 3.10.0-1160.102.1.el7.ppc64le
        ```
        
    9.  Run the following command to remove the old kernel:
        
        ```plaintext
        # sudo package-cleanup --oldkernels --count=1
        ```
        
    10.  Run the following command to check the default kernel and the list of currently installed kernels:
        
        ```plaintext
        #cat /boot/grub2/grubenv |grep saved saved_entry=1
        ```
        
        Note: This saved entry value should point to the kernel that is currently running. This needs to be verified because the list of kernels provided by the following command will be shuffled after the removal of the old kernel:
        
        ```plaintext
        awk -F\' /^menuentry/{print\$2} /etc/grub2.cfg
        ```
        
        If not, after the next reboot, the operating kernel has to be changed to the default kernel. If the current kernel and the default-saved item do not match, run the following command with the correct value from the list of kernels:
        
        ```plaintext
        commandgrub2-set-default 1
        ```
        
        Skip the step 3.
        
3.  Run the following command from all non SPU nodes:
    
    ```plaintext
    package-cleanup --oldkernels --count=1
    ```
    
    Note: When the older kernel is removed, the `grub2.cfg` list (In Step 2.a) will get shuffled. Make sure that the `grubenv` (Step 2.b) points to the available current version.
    
    If this error was encountered during the security patch upgrade, then follow the procedures above and continue the upgrade.
    

The list of Red Hat CVEs, which are patched in this release:

```plaintext
CVE-2023-20569 Moderate/Sec. iwl100-firmware-39.31.5.1-81.el7_9.noarch CVE-2023-20593 Moderate/Sec. iwl100-firmware-39.31.5.1-81.el7_9.noarch CVE-2023-20569 Moderate/Sec. iwl1000-firmware-1:39.31.5.1-81.el7_9.noarch CVE-2023-20593 Moderate/Sec. iwl1000-firmware-1:39.31.5.1-81.el7_9.noarch CVE-2023-20569 Moderate/Sec. iwl105-firmware-18.168.6.1-81.el7_9.noarch CVE-2023-20593 Moderate/Sec. iwl105-firmware-18.168.6.1-81.el7_9.noarch CVE-2023-20569 Moderate/Sec. iwl135-firmware-18.168.6.1-81.el7_9.noarch CVE-2023-20593 Moderate/Sec. iwl135-firmware-18.168.6.1-81.el7_9.noarch CVE-2023-20569 Moderate/Sec. iwl2000-firmware-18.168.6.1-81.el7_9.noarch CVE-2023-20593 Moderate/Sec. iwl2000-firmware-18.168.6.1-81.el7_9.noarch CVE-2023-20569 Moderate/Sec. iwl2030-firmware-18.168.6.1-81.el7_9.noarch CVE-2023-20593 Moderate/Sec. iwl2030-firmware-18.168.6.1-81.el7_9.noarch CVE-2023-20569 Moderate/Sec. iwl3160-firmware-25.30.13.0-81.el7_9.noarch CVE-2023-20593 Moderate/Sec. iwl3160-firmware-25.30.13.0-81.el7_9.noarch CVE-2023-20569 Moderate/Sec. iwl3945-firmware-15.32.2.9-81.el7_9.noarch CVE-2023-20593 Moderate/Sec. iwl3945-firmware-15.32.2.9-81.el7_9.noarch CVE-2023-20569 Moderate/Sec. iwl4965-firmware-228.61.2.24-81.el7_9.noarch CVE-2023-20593 Moderate/Sec. iwl4965-firmware-228.61.2.24-81.el7_9.noarch CVE-2023-20569 Moderate/Sec. iwl5000-firmware-8.83.5.1_1-81.el7_9.noarch CVE-2023-20593 Moderate/Sec. iwl5000-firmware-8.83.5.1_1-81.el7_9.noarch CVE-2023-20569 Moderate/Sec. iwl5150-firmware-8.24.2.2-81.el7_9.noarch CVE-2023-20593 Moderate/Sec. iwl5150-firmware-8.24.2.2-81.el7_9.noarch CVE-2023-20569 Moderate/Sec. iwl6000-firmware-9.221.4.1-81.el7_9.noarch CVE-2023-20593 Moderate/Sec. iwl6000-firmware-9.221.4.1-81.el7_9.noarch CVE-2023-20569 Moderate/Sec. iwl6000g2a-firmware-18.168.6.1-81.el7_9.noarch CVE-2023-20593 Moderate/Sec. iwl6000g2a-firmware-18.168.6.1-81.el7_9.noarch CVE-2023-20569 Moderate/Sec. iwl6000g2b-firmware-18.168.6.1-81.el7_9.noarch CVE-2023-20593 Moderate/Sec. iwl6000g2b-firmware-18.168.6.1-81.el7_9.noarch CVE-2023-20569 Moderate/Sec. iwl6050-firmware-41.28.5.1-81.el7_9.noarch CVE-2023-20593 Moderate/Sec. iwl6050-firmware-41.28.5.1-81.el7_9.noarch CVE-2023-20569 Moderate/Sec. iwl7260-firmware-25.30.13.0-81.el7_9.noarch CVE-2023-20593 Moderate/Sec. iwl7260-firmware-25.30.13.0-81.el7_9.noarch CVE-2022-40982 Important/Sec. kernel-3.10.0-1160.105.1.el7.x86_64 CVE-2023-3611 Important/Sec. kernel-3.10.0-1160.105.1.el7.x86_64 CVE-2023-3776 Important/Sec. kernel-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4128 Important/Sec. kernel-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4206 Important/Sec. kernel-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4207 Important/Sec. kernel-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4208 Important/Sec. kernel-3.10.0-1160.105.1.el7.x86_64 CVE-2022-40982 Important/Sec. kernel-debuginfo-3.10.0-1160.105.1.el7.x86_64 CVE-2023-3611 Important/Sec. kernel-debuginfo-3.10.0-1160.105.1.el7.x86_64 CVE-2023-3776 Important/Sec. kernel-debuginfo-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4128 Important/Sec. kernel-debuginfo-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4206 Important/Sec. kernel-debuginfo-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4207 Important/Sec. kernel-debuginfo-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4208 Important/Sec. kernel-debuginfo-3.10.0-1160.105.1.el7.x86_64 CVE-2022-40982 Important/Sec. kernel-debuginfo-3.10.0-1160.105.1.el7.x86_64 CVE-2023-3611 Important/Sec. kernel-debuginfo-3.10.0-1160.105.1.el7.x86_64 CVE-2023-3776 Important/Sec. kernel-debuginfo-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4128 Important/Sec. kernel-debuginfo-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4206 Important/Sec. kernel-debuginfo-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4207 Important/Sec. kernel-debuginfo-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4208 Important/Sec. kernel-debuginfo-3.10.0-1160.105.1.el7.x86_64 CVE-2022-40982 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.105.1.el7.x86_64 CVE-2023-3611 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.105.1.el7.x86_64 CVE-2023-3776 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4128 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4206 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4207 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4208 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.105.1.el7.x86_64 CVE-2022-40982 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.105.1.el7.x86_64 CVE-2023-3611 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.105.1.el7.x86_64 CVE-2023-3776 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4128 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4206 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4207 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4208 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.105.1.el7.x86_64 CVE-2022-40982 Important/Sec. kernel-devel-3.10.0-1160.105.1.el7.x86_64 CVE-2023-3611 Important/Sec. kernel-devel-3.10.0-1160.105.1.el7.x86_64 CVE-2023-3776 Important/Sec. kernel-devel-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4128 Important/Sec. kernel-devel-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4206 Important/Sec. kernel-devel-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4207 Important/Sec. kernel-devel-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4208 Important/Sec. kernel-devel-3.10.0-1160.105.1.el7.x86_64 CVE-2022-40982 Important/Sec. kernel-headers-3.10.0-1160.105.1.el7.x86_64 CVE-2023-3611 Important/Sec. kernel-headers-3.10.0-1160.105.1.el7.x86_64 CVE-2023-3776 Important/Sec. kernel-headers-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4128 Important/Sec. kernel-headers-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4206 Important/Sec. kernel-headers-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4207 Important/Sec. kernel-headers-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4208 Important/Sec. kernel-headers-3.10.0-1160.105.1.el7.x86_64 CVE-2022-40982 Important/Sec. kernel-tools-3.10.0-1160.105.1.el7.x86_64 CVE-2023-3611 Important/Sec. kernel-tools-3.10.0-1160.105.1.el7.x86_64 CVE-2023-3776 Important/Sec. kernel-tools-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4128 Important/Sec. kernel-tools-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4206 Important/Sec. kernel-tools-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4207 Important/Sec. kernel-tools-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4208 Important/Sec. kernel-tools-3.10.0-1160.105.1.el7.x86_64 CVE-2022-40982 Important/Sec. kernel-tools-libs-3.10.0-1160.105.1.el7.x86_64 CVE-2023-3611 Important/Sec. kernel-tools-libs-3.10.0-1160.105.1.el7.x86_64 CVE-2023-3776 Important/Sec. kernel-tools-libs-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4128 Important/Sec. kernel-tools-libs-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4206 Important/Sec. kernel-tools-libs-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4207 Important/Sec. kernel-tools-libs-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4208 Important/Sec. kernel-tools-libs-3.10.0-1160.105.1.el7.x86_64 CVE-2023-20569 Moderate/Sec. linux-firmware-20200421-81.git78c0348.el7_9.noarch CVE-2023-20593 Moderate/Sec. linux-firmware-20200421-81.git78c0348.el7_9.noarch CVE-2022-40982 Important/Sec. perf-3.10.0-1160.105.1.el7.x86_64 CVE-2023-3611 Important/Sec. perf-3.10.0-1160.105.1.el7.x86_64 CVE-2023-3776 Important/Sec. perf-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4128 Important/Sec. perf-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4206 Important/Sec. perf-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4207 Important/Sec. perf-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4208 Important/Sec. perf-3.10.0-1160.105.1.el7.x86_64 CVE-2023-40217 Important/Sec. python-2.7.5-94.el7_9.x86_64 CVE-2023-40217 Important/Sec. python-devel-2.7.5-94.el7_9.x86_64 CVE-2023-40217 Important/Sec. python-libs-2.7.5-94.el7_9.x86_64 CVE-2022-40982 Important/Sec. python-perf-3.10.0-1160.105.1.el7.x86_64 CVE-2023-3611 Important/Sec. python-perf-3.10.0-1160.105.1.el7.x86_64 CVE-2023-3776 Important/Sec. python-perf-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4128 Important/Sec. python-perf-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4206 Important/Sec. python-perf-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4207 Important/Sec. python-perf-3.10.0-1160.105.1.el7.x86_64 CVE-2023-4208 Important/Sec. python-perf-3.10.0-1160.105.1.el7.x86_64 CVE-2023-40217 Important/Sec. python3-3.6.8-21.el7_9.x86_64 CVE-2023-40217 Important/Sec. python3-devel-3.6.8-21.el7_9.x86_64 CVE-2023-40217 Important/Sec. python3-libs-3.6.8-21.el7_9.x86_64 CVE-2022-43552 Low/Sec. curl-7.29.0-59.el7_9.2.x86_64 CVE-2022-43552 Low/Sec. libcurl-7.29.0-59.el7_9.2.x86_64
```

## 7.9.23.11.SP25

The release date of the security patch 7.9.23.11.SP25 is 20 December 2023. The estimated run time is around 80 minutes.

The 7.9.23.11.SP25 patch is based on RHEL 7.9, and it can only be installed on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x and 1.0.8.x.

Important: If you are using version 1.0.8, you must upgrade to 1.0.8.0 IF2 first to apply 7.9.23.11.SP25.

Restriction: After applying 7.9.23.11.SP25, you can upgrade Cloud Pak for Data System to version 1.0.8.4 or later versions only.

Note: The ap version -s might not show all of the docker upgrade component versions after applying 7.9.23.11.SP25 on Cloud Pak for Data System 1.0.7.8 or 1.0.7.8 IF2. This happens if Python 2 is installed.

Workaround

Run the ap version -d command.

Note: If the parameter /boot value exceeds 100% capacity after applying the security patch 7.9.23.11.SP25, the following alerts might be displayed:

```plaintext
[root@NPS-SAND-02-e1n1: ~]$ df -h /boot Filesystem Size Used Avail Use% Mounted on /dev/sda1 190M 177M 0 100% /boot | 3644 | 2024-03-25 20:37:29 | STORAGE_UTILIZATION | 901: Storage utilization above threshold | sw://fs.sda1/enclosure1.node1 | CRITICAL | N/A | | 3645 | 2024-03-25 20:37:45 | STORAGE_UTILIZATION | 901: Storage utilization above threshold | sw://fs.sda1/enclosure1.node4 | CRITICAL | N/A | | 3646 | 2024-03-25 20:37:45 | STORAGE_UTILIZATION | 901: Storage utilization above threshold | sw://fs.sda1/enclosure1.node3 | CRITICAL | N/A | | 3647 | 2024-03-25 20:37:45 | STORAGE_UTILIZATION | 901: Storage utilization above threshold | sw://fs.sda1/enclosure1.node2 | CRITICAL | N/A |
```

Workaround:

1.  Run the following command from all non SPU nodes to check the /boot parameter value:
    
    Example:
    
    ```plaintext
    df -h /boot Filesystem Size Used Avail Use% Mounted on /dev/sda1 190M 177M 0 100% /boot
    ```
    
2.  If the /boot parameter shows use of 95% or greater value, run the following commands on all non SPU nodes to free up storage in /boot.
    1.  Run the following command to check which kernel versions are present in each non SPU node:
        
        ```plaintext
        awk -F\' /^menuentry/{print\$2} /etc/grub2.cfg
        ```
        
        Example:
        
        ```plaintext
        Eg - # awk -F\' /^menuentry/{print\$2} /etc/grub2.cfg Red Hat Enterprise Linux Server, with Linux 3.10.0-123.el7.x86_64 <=== Entry 0 Red Hat Enterprise Linux Server, with Linux 3.10.0-123.9.2.el7.x86_64 <=== Entry 1 Red Hat Enterprise Linux Server, with Linux 3.10.0-123.6.3.el7.x86_64 <=== Entry 2 Red Hat Enterprise Linux Server, with Linux 0-rescue-b03fd2e1e769493994c88 b8da4257178 <=== Entry 3
        ```
        
    2.  Run the following command to find the default kernel version set:
        
        ```plaintext
        cat /boot/grub2/grubenv |grep saved
        ```
        
        Example:
        
        ```plaintext
        Eg - cat /boot/grub2/grubenv |grep saved saved_entry=Red Hat Enterprise Linux Server, with Linux 3.10.0-123.9.2.el7.x86_64
        ```
        
    3.  If the kernel version is the latest, proceed to step 3. If not, perform steps 2.d to 2.j to change the default kernel and uninstall the older version.
    4.  Check the current kernel installed, as in step 2.a.
        
        ```plaintext
        # awk -F\' /^menuentry/{print\$2} /etc/grub2.cfg Red Hat Enterprise Linux Server, with Linux 3.10.0-123.el7.x86_64 <=== Entry 0 Red Hat Enterprise Linux Server, with Linux 3.10.0-123.9.2.el7.x86_64 <=== Entry 1 Red Hat Enterprise Linux Server, with Linux 3.10.0-123.6.3.el7.x86_64 <=== Entry 2 Red Hat Enterprise Linux Server, with Linux 0-rescue-b03fd2e1e769493994c88 b8da4257178 <=== Entry 3
        ```
        
    5.  Set the default kernel based on the numbers in the previous steps:
    6.  Check that the default kernel is correctly set:
        
        ```plaintext
        # cat /boot/grub2/grubenv |grep saved saved_entry=1
        ```
        
    7.  Run the following commands to reboot the node:
        
        Alternatively, via `ipmitool`:
        
        -   For Dell system
            
            ```plaintext
            ipmitool -I lanplus -H <node>bmc -U root -P calvin power on ipmitool -I lanplus -H <node>bmc -U root -P calvin power off
            ```
            
        -   For Lenovo system
            
            ```plaintext
            ipmitool -H <node>bmc -U USERID -P PASSW0RD -I lanplus power on ipmitool -H <node>bmcbmc -U USERID -P PASSW0RD -I lanplus power off
            ```
            
        
    8.  After the reboot, run the following command to check the current kernel:
        
        ```plaintext
        #[root@sail81-t07-n3 ~]# uname -r 3.10.0-1160.102.1.el7.ppc64le
        ```
        
    9.  Run the following command to remove the old kernel:
        
        ```plaintext
        # sudo package-cleanup --oldkernels --count=1
        ```
        
    10.  Run the following command to check the default kernel and the list of currently installed kernels:
        
        ```plaintext
        #cat /boot/grub2/grubenv |grep saved saved_entry=1
        ```
        
        Note: This saved entry value should point to the kernel that is currently running. This needs to be verified because the list of kernels provided by the following command will be shuffled after the removal of the old kernel:
        
        ```plaintext
        awk -F\' /^menuentry/{print\$2} /etc/grub2.cfg
        ```
        
        If not, after the next reboot, the operating kernel has to be changed to the default kernel. If the current kernel and the default-saved item do not match, run the following command with the correct value from the list of kernels:
        
        ```plaintext
        commandgrub2-set-default 1
        ```
        
        Skip the step 3.
        
3.  Run the following command from all non SPU nodes:
    
    ```plaintext
    package-cleanup --oldkernels --count=1
    ```
    
    Note: When the older kernel is removed, the `grub2.cfg` list (In Step 2.a) will get shuffled. Make sure that the `grubenv` (Step 2.b) points to the available current version.
    
    If this error was encountered during the security patch upgrade, then follow the procedures above and continue the upgrade.
    

The list of Red Hat CVEs, which are patched in this release:

```plaintext
CVE-2023-3341 Important/Sec. bind-32:9.11.4-26.P2.el7_9.15.x86_64 CVE-2023-3341 Important/Sec. bind-export-libs-32:9.11.4-26.P2.el7_9.15.x86_64 CVE-2023-3341 Important/Sec. bind-libs-32:9.11.4-26.P2.el7_9.15.x86_64 CVE-2023-3341 Important/Sec. bind-libs-lite-32:9.11.4-26.P2.el7_9.15.x86_64 CVE-2023-3341 Important/Sec. bind-license-32:9.11.4-26.P2.el7_9.15.noarch CVE-2023-3341 Important/Sec. bind-pkcs11-32:9.11.4-26.P2.el7_9.15.x86_64 CVE-2023-3341 Important/Sec. bind-pkcs11-libs-32:9.11.4-26.P2.el7_9.15.x86_64 CVE-2023-3341 Important/Sec. bind-pkcs11-utils-32:9.11.4-26.P2.el7_9.15.x86_64 CVE-2023-3341 Important/Sec. bind-utils-32:9.11.4-26.P2.el7_9.15.x86_64 CVE-2023-22067 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.392.b08-2.el7_9.x86_64 CVE-2023-22081 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.392.b08-2.el7_9.x86_64 CVE-2023-22067 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.392.b08-2.el7_9.x86_64 CVE-2023-22081 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.392.b08-2.el7_9.x86_64 CVE-2023-3609 Important/Sec. kernel-3.10.0-1160.102.1.el7.x86_64 CVE-2023-32233 Important/Sec. kernel-3.10.0-1160.102.1.el7.x86_64 CVE-2023-35001 Important/Sec. kernel-3.10.0-1160.102.1.el7.x86_64 CVE-2023-3609 Important/Sec. kernel-debuginfo-3.10.0-1160.102.1.el7.x86_64 CVE-2023-32233 Important/Sec. kernel-debuginfo-3.10.0-1160.102.1.el7.x86_64 CVE-2023-35001 Important/Sec. kernel-debuginfo-3.10.0-1160.102.1.el7.x86_64 CVE-2023-3609 Important/Sec. kernel-debuginfo-3.10.0-1160.102.1.el7.x86_64 CVE-2023-32233 Important/Sec. kernel-debuginfo-3.10.0-1160.102.1.el7.x86_64 CVE-2023-35001 Important/Sec. kernel-debuginfo-3.10.0-1160.102.1.el7.x86_64 CVE-2023-3609 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.102.1.el7.x86_64 CVE-2023-32233 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.102.1.el7.x86_64 CVE-2023-35001 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.102.1.el7.x86_64 CVE-2023-3609 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.102.1.el7.x86_64 CVE-2023-32233 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.102.1.el7.x86_64 CVE-2023-35001 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.102.1.el7.x86_64 CVE-2023-3609 Important/Sec. kernel-devel-3.10.0-1160.102.1.el7.x86_64 CVE-2023-32233 Important/Sec. kernel-devel-3.10.0-1160.102.1.el7.x86_64 CVE-2023-35001 Important/Sec. kernel-devel-3.10.0-1160.102.1.el7.x86_64 CVE-2023-3609 Important/Sec. kernel-headers-3.10.0-1160.102.1.el7.x86_64 CVE-2023-32233 Important/Sec. kernel-headers-3.10.0-1160.102.1.el7.x86_64 CVE-2023-35001 Important/Sec. kernel-headers-3.10.0-1160.102.1.el7.x86_64 CVE-2023-3609 Important/Sec. kernel-tools-3.10.0-1160.102.1.el7.x86_64 CVE-2023-32233 Important/Sec. kernel-tools-3.10.0-1160.102.1.el7.x86_64 CVE-2023-35001 Important/Sec. kernel-tools-3.10.0-1160.102.1.el7.x86_64 CVE-2023-3609 Important/Sec. kernel-tools-libs-3.10.0-1160.102.1.el7.x86_64 CVE-2023-32233 Important/Sec. kernel-tools-libs-3.10.0-1160.102.1.el7.x86_64 CVE-2023-35001 Important/Sec. kernel-tools-libs-3.10.0-1160.102.1.el7.x86_64 CVE-2020-22218 Moderate/Sec. libssh2-1.8.0-4.el7_9.1.x86_64 CVE-2023-3609 Important/Sec. perf-3.10.0-1160.102.1.el7.x86_64 CVE-2023-32233 Important/Sec. perf-3.10.0-1160.102.1.el7.x86_64 CVE-2023-35001 Important/Sec. perf-3.10.0-1160.102.1.el7.x86_64 CVE-2023-3609 Important/Sec. python-perf-3.10.0-1160.102.1.el7.x86_64 CVE-2023-32233 Important/Sec. python-perf-3.10.0-1160.102.1.el7.x86_64 CVE-2023-35001 Important/Sec. python-perf-3.10.0-1160.102.1.el7.x86_64
```

## 7.9.23.09.SP24

The release date of the security patch 7.9.23.09.SP24 is 9 October 2023. The estimated run time is around 70 minutes.

The 7.9.23.09.SP24 patch is based on RHEL 7.9, and it can be installed only on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x and 1.0.8.x.

Important: Upgrading to Cloud Pak for Data System 1.0.8.x versions till 1.0.8.3 after applying 7.9.23.09.SP24 will overwrite the fix for the `cve-2023-24329`. To resolve this CVE, proceed with one of the following options:

-   Upgrade to Cloud Pak for Data System 1.0.8.4 or a later version when available.
-   Apply SP25 when available.
-   Contact IBM support.

Note: You don't have to apply 7.9.23.09.SP24 on Cloud Pak for Data System 1.0.8.4. Version 1.0.8.4 comes with security updates till SP24. Apply SP25 and later versions on 1.0.8.4 when available.

Note: If after applying the security patch 7.9.23.09.SP24 or greater, you try to upgrade to 1.0.7.8, the upgrade might fail with the following error:

```plaintext
1. NodeosUpgrader.install Upgrade Detail: Component install for nodeos Caller Info:The call was made from 'NodeOSYosemiteInstaller.install' on line 100 with file located at '/localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/bundle_upgraders/../nodeos/node_os_yosemite_installer.py' Message: nodeos:NodeosUpgrader.install:Fatal Problem: Failed to install any new Node OS rpms...
```

Workaround:

1.  Run the following two commands from `e1n1`. Replace the `<your-1.0.7.8-upgrade-dir>` directory name in the commands with the actual upgrade directory name that you used on your system.
    1.  ```plaintext
        sed -i -e "0,/self._get_yum_repos_options() + ' ' + self.install_y/s/self._get_yum_repos_options() + ' ' + self.install_y/self._get_yum_repos_options() + ' ' + '--exclude=\"kernel*\"' + ' ' + self.install_y/" /localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/nodeos/node_os_installer.py
        ```
        
    2.  ```plaintext
        sed -i -e 's,self.verify_bundle,#self.verify_bundle,g' /opt/ibm/appliance/apupgrade/bin/apupgrade
        ```
        
2.  Rerun the same `apupgrade` command that failed:
    
    ```plaintext
    apupgrade --upgrade --upgrade-directory /localrepo --bundle system --use-version <your-1.0.7.8-upgrade-dir>
    ```
    

Note: If the parameter /boot value exceeds 100% capacity after applying the security patch 7.9.23.09.SP24, the following alerts might be displayed:

```plaintext
[root@NPS-SAND-02-e1n1: ~]$ df -h /boot Filesystem Size Used Avail Use% Mounted on /dev/sda1 190M 177M 0 100% /boot | 3644 | 2024-03-25 20:37:29 | STORAGE_UTILIZATION | 901: Storage utilization above threshold | sw://fs.sda1/enclosure1.node1 | CRITICAL | N/A | | 3645 | 2024-03-25 20:37:45 | STORAGE_UTILIZATION | 901: Storage utilization above threshold | sw://fs.sda1/enclosure1.node4 | CRITICAL | N/A | | 3646 | 2024-03-25 20:37:45 | STORAGE_UTILIZATION | 901: Storage utilization above threshold | sw://fs.sda1/enclosure1.node3 | CRITICAL | N/A | | 3647 | 2024-03-25 20:37:45 | STORAGE_UTILIZATION | 901: Storage utilization above threshold | sw://fs.sda1/enclosure1.node2 | CRITICAL | N/A |
```

Workaround:

1.  Run the following command from all non SPU nodes to check the /boot parameter value:
    
    Example:
    
    ```plaintext
    df -h /boot Filesystem Size Used Avail Use% Mounted on /dev/sda1 190M 177M 0 100% /boot
    ```
    
2.  If the /boot parameter shows use of 95% or greater value, run the following commands on all non SPU nodes to free up storage in /boot.
    1.  Run the following command to check which kernel versions are present in each non SPU node:
        
        ```plaintext
        awk -F\' /^menuentry/{print\$2} /etc/grub2.cfg
        ```
        
        Example:
        
        ```plaintext
        Eg - # awk -F\' /^menuentry/{print\$2} /etc/grub2.cfg Red Hat Enterprise Linux Server, with Linux 3.10.0-123.el7.x86_64 <=== Entry 0 Red Hat Enterprise Linux Server, with Linux 3.10.0-123.9.2.el7.x86_64 <=== Entry 1 Red Hat Enterprise Linux Server, with Linux 3.10.0-123.6.3.el7.x86_64 <=== Entry 2 Red Hat Enterprise Linux Server, with Linux 0-rescue-b03fd2e1e769493994c88 b8da4257178 <=== Entry 3
        ```
        
    2.  Run the following command to find the default kernel version set:
        
        ```plaintext
        cat /boot/grub2/grubenv |grep saved
        ```
        
        Example:
        
        ```plaintext
        Eg - cat /boot/grub2/grubenv |grep saved saved_entry=Red Hat Enterprise Linux Server, with Linux 3.10.0-123.9.2.el7.x86_64
        ```
        
    3.  If the kernel version is the latest, proceed to step 3. If not, perform steps 2.d to 2.j to change the default kernel and uninstall the older version.
    4.  Check the current kernel installed, as in step 2.a.
        
        ```plaintext
        # awk -F\' /^menuentry/{print\$2} /etc/grub2.cfg Red Hat Enterprise Linux Server, with Linux 3.10.0-123.el7.x86_64 <=== Entry 0 Red Hat Enterprise Linux Server, with Linux 3.10.0-123.9.2.el7.x86_64 <=== Entry 1 Red Hat Enterprise Linux Server, with Linux 3.10.0-123.6.3.el7.x86_64 <=== Entry 2 Red Hat Enterprise Linux Server, with Linux 0-rescue-b03fd2e1e769493994c88 b8da4257178 <=== Entry 3
        ```
        
    5.  Set the default kernel based on the numbers in the previous steps:
    6.  Check that the default kernel is correctly set:
        
        ```plaintext
        # cat /boot/grub2/grubenv |grep saved saved_entry=1
        ```
        
    7.  Run the following commands to reboot the node:
        
        Alternatively, via `ipmitool`:
        
        -   For Dell system
            
            ```plaintext
            ipmitool -I lanplus -H <node>bmc -U root -P calvin power on ipmitool -I lanplus -H <node>bmc -U root -P calvin power off
            ```
            
        -   For Lenovo system
            
            ```plaintext
            ipmitool -H <node>bmc -U USERID -P PASSW0RD -I lanplus power on ipmitool -H <node>bmcbmc -U USERID -P PASSW0RD -I lanplus power off
            ```
            
        
    8.  After the reboot, run the following command to check the current kernel:
        
        ```plaintext
        #[root@sail81-t07-n3 ~]# uname -r 3.10.0-1160.102.1.el7.ppc64le
        ```
        
    9.  Run the following command to remove the old kernel:
        
        ```plaintext
        # sudo package-cleanup --oldkernels --count=1
        ```
        
    10.  Run the following command to check the default kernel and the list of currently installed kernels:
        
        ```plaintext
        #cat /boot/grub2/grubenv |grep saved saved_entry=1
        ```
        
        Note: This saved entry value should point to the kernel that is currently running. This needs to be verified because the list of kernels provided by the following command will be shuffled after the removal of the old kernel:
        
        ```plaintext
        awk -F\' /^menuentry/{print\$2} /etc/grub2.cfg
        ```
        
        If not, after the next reboot, the operating kernel has to be changed to the default kernel. If the current kernel and the default-saved item do not match, run the following command with the correct value from the list of kernels:
        
        ```plaintext
        commandgrub2-set-default 1
        ```
        
        Skip the step 3.
        
3.  Run the following command from all non SPU nodes:
    
    ```plaintext
    package-cleanup --oldkernels --count=1
    ```
    
    Note: When the older kernel is removed, the `grub2.cfg` list (In Step 2.a) will get shuffled. Make sure that the `grubenv` (Step 2.b) points to the available current version.
    
    If this error was encountered during the security patch upgrade, then follow the procedures above and continue the upgrade.
    

The list of Red Hat CVEs, which are patched in this release:

```plaintext
CVE-2023-32360 Important/Sec. cups-1:1.6.3-52.el7_9.x86_64 CVE-2023-32360 Important/Sec. cups-client-1:1.6.3-52.el7_9.x86_64 CVE-2023-32360 Important/Sec. cups-filesystem-1:1.6.3-52.el7_9.noarch CVE-2023-32360 Important/Sec. cups-libs-1:1.6.3-52.el7_9.x86_64 CVE-2020-5208 Important/Sec. ipmitool-1.8.18-9.el7_7.x86_64 CVE-2023-3899 Moderate/Sec. python-syspurpose-1.24.52-2.el7_9.x86_64 CVE-2023-3899 Moderate/Sec. subscription-manager-1.24.52-2.el7_9.x86_64 CVE-2023-3899 Moderate/Sec. subscription-manager-rhsm-1.24.52-2.el7_9.x86_64 CVE-2023-3899 Moderate/Sec. subscription-manager-rhsm-certificates-1.24.52-2.el7_9.x86_64 CVE-2023-2828 Important/Sec. bind-32:9.11.4-26.P2.el7_9.14.x86_64 CVE-2023-2828 Important/Sec. bind-export-libs-32:9.11.4-26.P2.el7_9.14.x86_64 CVE-2023-2828 Important/Sec. bind-libs-32:9.11.4-26.P2.el7_9.14.x86_64 CVE-2023-2828 Important/Sec. bind-libs-lite-32:9.11.4-26.P2.el7_9.14.x86_64 CVE-2023-2828 Important/Sec. bind-license-32:9.11.4-26.P2.el7_9.14.noarch CVE-2023-2828 Important/Sec. bind-pkcs11-32:9.11.4-26.P2.el7_9.14.x86_64 CVE-2023-2828 Important/Sec. bind-pkcs11-libs-32:9.11.4-26.P2.el7_9.14.x86_64 CVE-2023-2828 Important/Sec. bind-pkcs11-utils-32:9.11.4-26.P2.el7_9.14.x86_64 CVE-2023-2828 Important/Sec. bind-utils-32:9.11.4-26.P2.el7_9.14.x86_64 CVE-2023-38403 Important/Sec. iperf3-3.1.7-3.el7_9.x86_64 CVE-2023-22045 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.382.b05-1.el7_9.x86_64 CVE-2023-22049 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.382.b05-1.el7_9.x86_64 CVE-2023-22045 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.382.b05-1.el7_9.x86_64 CVE-2023-22049 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.382.b05-1.el7_9.x86_64 CVE-2023-20593 Important/Sec. kernel-3.10.0-1160.99.1.el7.x86_64 CVE-2023-35788 Important/Sec. kernel-3.10.0-1160.99.1.el7.x86_64 CVE-2023-20593 Important/Sec. kernel-debuginfo-3.10.0-1160.99.1.el7.x86_64 CVE-2023-35788 Important/Sec. kernel-debuginfo-3.10.0-1160.99.1.el7.x86_64 CVE-2023-20593 Important/Sec. kernel-debuginfo-3.10.0-1160.99.1.el7.x86_64 CVE-2023-35788 Important/Sec. kernel-debuginfo-3.10.0-1160.99.1.el7.x86_64 CVE-2023-20593 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.99.1.el7.x86_64 CVE-2023-35788 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.99.1.el7.x86_64 CVE-2023-20593 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.99.1.el7.x86_64 CVE-2023-35788 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.99.1.el7.x86_64 CVE-2023-20593 Important/Sec. kernel-devel-3.10.0-1160.99.1.el7.x86_64 CVE-2023-35788 Important/Sec. kernel-devel-3.10.0-1160.99.1.el7.x86_64 CVE-2023-20593 Important/Sec. kernel-headers-3.10.0-1160.99.1.el7.x86_64 CVE-2023-35788 Important/Sec. kernel-headers-3.10.0-1160.99.1.el7.x86_64 CVE-2023-20593 Important/Sec. kernel-tools-3.10.0-1160.99.1.el7.x86_64 CVE-2023-35788 Important/Sec. kernel-tools-3.10.0-1160.99.1.el7.x86_64 CVE-2023-20593 Important/Sec. kernel-tools-libs-3.10.0-1160.99.1.el7.x86_64 CVE-2023-35788 Important/Sec. kernel-tools-libs-3.10.0-1160.99.1.el7.x86_64 CVE-2023-38408 Important/Sec. openssh-7.4p1-23.el7_9.x86_64 CVE-2023-38408 Important/Sec. openssh-clients-7.4p1-23.el7_9.x86_64 CVE-2023-38408 Important/Sec. openssh-server-7.4p1-23.el7_9.x86_64 CVE-2023-20593 Important/Sec. perf-3.10.0-1160.99.1.el7.x86_64 CVE-2023-35788 Important/Sec. perf-3.10.0-1160.99.1.el7.x86_64 CVE-2023-20593 Important/Sec. python-perf-3.10.0-1160.99.1.el7.x86_64 CVE-2023-35788 Important/Sec. python-perf-3.10.0-1160.99.1.el7.x86_64 CVE-2023-30861 python-flask-0.10.1-7.el7_9.noarch.rpm CVE-2023-24329 Important/Sec. python3-3.6.8-19.el7_9.x86_64 CVE-2023-24329 Important/Sec. python3-devel-3.6.8-19.el7_9.x86_64 CVE-2023-24329 Important/Sec. python3-libs-3.6.8-19.el7_9.x86_64
```

## 7.9.23.07.SP23

The release date of the security patch 7.9.23.07.SP23 is 8 September 2023. The estimated run time is around 70 minutes.

The 7.9.23.07.SP23 patch is based on RHEL 7.9, and it can only be installed on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x and 1.0.8.x.

Note: You don't have to apply 7.9.23.07.SP23 on Cloud Pak for Data System 1.0.8.3. Version 1.0.8.3 comes with security updates till SP23. Apply SP24 and later versions on 1.0.8.3 when available.

Note: If after applying the security patch 7.9.23.07.SP23 or greater, you try to upgrade to 1.0.7.8, the upgrade might fail with the following error:

```plaintext
1. NodeosUpgrader.install Upgrade Detail: Component install for nodeos Caller Info:The call was made from 'NodeOSYosemiteInstaller.install' on line 100 with file located at '/localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/bundle_upgraders/../nodeos/node_os_yosemite_installer.py' Message: nodeos:NodeosUpgrader.install:Fatal Problem: Failed to install any new Node OS rpms...
```

Workaround:

1.  Run the following two commands from `e1n1`. Replace the `<your-1.0.7.8-upgrade-dir>` directory name in the commands with the actual upgrade directory name that you used on your system.
    1.  ```plaintext
        sed -i -e "0,/self._get_yum_repos_options() + ' ' + self.install_y/s/self._get_yum_repos_options() + ' ' + self.install_y/self._get_yum_repos_options() + ' ' + '--exclude=\"kernel*\"' + ' ' + self.install_y/" /localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/nodeos/node_os_installer.py
        ```
        
    2.  ```plaintext
        sed -i -e 's,self.verify_bundle,#self.verify_bundle,g' /opt/ibm/appliance/apupgrade/bin/apupgrade
        ```
        
2.  Rerun the same `apupgrade` command that failed:
    
    ```plaintext
    apupgrade --upgrade --upgrade-directory /localrepo --bundle system --use-version <your-1.0.7.8-upgrade-dir>
    ```
    

The list of Red Hat CVEs, which are patched in this release:

```plaintext
CVE-2023-32067 Important/Sec. c-ares-1.10.0-3.el7_9.1.x86_64 CVE-2022-48339 Moderate/Sec. emacs-filesystem-1:24.3-23.el7_9.1.noarch CVE-2023-24329 Important/Sec. python-2.7.5-93.el7_9.x86_64 CVE-2023-24329 Important/Sec. python-devel-2.7.5-93.el7_9.x86_64 CVE-2023-24329 Important/Sec. python-libs-2.7.5-93.el7_9.x86_64
```

## 7.9.23.06.SP22

The release date of the 7.9.23.06.SP22 security patch is 27 June 2023. The estimated run time is around 60 minutes.

The 7.9.23.06.SP22 patch is based on RHEL 7.9, and it can only be installed on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x and 1.0.8.x.

Note:

-   If after applying the security patch 7.9.23.06.SP22 or greater, you try to upgrade to 1.0.7.8, the upgrade might fail with the following error:
    
    ```plaintext
    1. NodeosUpgrader.install Upgrade Detail: Component install for nodeos Caller Info:The call was made from 'NodeOSYosemiteInstaller.install' on line 100 with file located at '/localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/bundle_upgraders/../nodeos/node_os_yosemite_installer.py' Message: nodeos:NodeosUpgrader.install:Fatal Problem: Failed to install any new Node OS rpms...
    ```
    
    Workaround:
    
    1.  Run the following two commands from e1n1. Replace the `<your-1.0.7.8-upgrade-dir>` directory name in the commands with the actual upgrade directory name that you used on your system.
        1.  ```plaintext
            sed -i -e "0,/self._get_yum_repos_options() + ' ' + self.install_y/s/self._get_yum_repos_options() + ' ' + self.install_y/self._get_yum_repos_options() + ' ' + '--exclude=\"kernel*\"' + ' ' + self.install_y/" /localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/nodeos/node_os_installer.py
            ```
            
        2.  ```plaintext
            sed -i -e 's,self.verify_bundle,#self.verify_bundle,g' /opt/ibm/appliance/apupgrade/bin/apupgrade
            ```
            
    2.  Rerun the same `apupgrade` command that failed:
        
        ```plaintext
        apupgrade --upgrade --upgrade-directory /localrepo --bundle system --use-version <your-1.0.7.8-upgrade-dir>
        ```
        
-   While applying the security patch 7.9.23.06.SP22, the process might get stuck with the following error:
    
    ```plaintext
    2023-07-21 09:09:32 TRACE: Running command [ssh e1n1 'ipmitool lan print 1']. LOGGING FROM: node_os_prechecker.py:check_ipmitool_lan:89 2023-07-21 09:09:33 TRACE: RC: 1. STDOUT: [] STDERR: [Invalid channel: 1 ]
    ```
    
    Workaround:
    
    Run the following commands to overcome the error:
    
    1.  ```plaintext
        sed -i '60 s/node0101/e1n1/' <full path of node_os_prechecker_fixer.py>;sed -i '106 s/node0101/e1n1/' <full path of node_os_prechecker_fixer.py>
        ```
        
    2.  ```plaintext
        sed -i -e 's,self.verify_bundle,#self.verify_bundle,g' /opt/ibm/appliance/apupgrade/bin/apupgrade
        ```
        
    

The list of Red Hat CVEs, which are patched in this release:

```plaintext
CVE-2023-21930 Important/Sec. java-1.8.0-openjdk-1:1.8.0.372.b07-1.el7_9.x86_64 CVE-2023-21937 Important/Sec. java-1.8.0-openjdk-1:1.8.0.372.b07-1.el7_9.x86_64 CVE-2023-21938 Important/Sec. java-1.8.0-openjdk-1:1.8.0.372.b07-1.el7_9.x86_64 CVE-2023-21939 Important/Sec. java-1.8.0-openjdk-1:1.8.0.372.b07-1.el7_9.x86_64 CVE-2023-21954 Important/Sec. java-1.8.0-openjdk-1:1.8.0.372.b07-1.el7_9.x86_64 CVE-2023-21967 Important/Sec. java-1.8.0-openjdk-1:1.8.0.372.b07-1.el7_9.x86_64 CVE-2023-21968 Important/Sec. java-1.8.0-openjdk-1:1.8.0.372.b07-1.el7_9.x86_64 CVE-2023-21930 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.372.b07-1.el7_9.x86_64 CVE-2023-21937 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.372.b07-1.el7_9.x86_64 CVE-2023-21938 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.372.b07-1.el7_9.x86_64 CVE-2023-21939 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.372.b07-1.el7_9.x86_64 CVE-2023-21954 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.372.b07-1.el7_9.x86_64 CVE-2023-21967 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.372.b07-1.el7_9.x86_64 CVE-2023-21968 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.372.b07-1.el7_9.x86_64 CVE-2022-43750 Moderate/Sec. kernel-3.10.0-1160.90.1.el7.x86_64 CVE-2022-43750 Moderate/Sec. kernel-debuginfo-3.10.0-1160.90.1.el7.x86_64 CVE-2022-43750 Moderate/Sec. kernel-debuginfo-3.10.0-1160.90.1.el7.x86_64 CVE-2022-43750 Moderate/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.90.1.el7.x86_64 CVE-2022-43750 Moderate/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.90.1.el7.x86_64 CVE-2022-43750 Moderate/Sec. kernel-devel-3.10.0-1160.90.1.el7.x86_64 CVE-2022-43750 Moderate/Sec. kernel-headers-3.10.0-1160.90.1.el7.x86_64 CVE-2022-43750 Moderate/Sec. kernel-tools-3.10.0-1160.90.1.el7.x86_64 CVE-2022-43750 Moderate/Sec. kernel-tools-libs-3.10.0-1160.90.1.el7.x86_64 CVE-2023-1999 Important/Sec. libwebp-0.3.0-11.el7.x86_64 CVE-2022-43750 Moderate/Sec. perf-3.10.0-1160.90.1.el7.x86_64 CVE-2022-43750 Moderate/Sec. python-perf-3.10.0-1160.90.1.el7.x86_64 CVE-2022-25147 Important/Sec. apr-util-1.5.2-6.el7_9.1.x86_64 CVE-2022-25147 Important/Sec. apr-util-openssl-1.5.2-6.el7_9.1.x86_64 CVE-2023-25652 Important/Sec. git-1.8.3.1-25.el7_9.x86_64 CVE-2023-29007 Important/Sec. git-1.8.3.1-25.el7_9.x86_64 CVE-2023-25652 Important/Sec. perl-Git-1.8.3.1-25.el7_9.noarch CVE-2023-29007 Important/Sec. perl-Git-1.8.3.1-25.el7_9.noarch
```

## 7.9.23.04.SP21

The release date of the 7.9.23.04.SP21 security patch is 12 May 2023. The estimated run time is around 60 minutes.

The 7.9.23.04.SP21 patch is based on RHEL 7.9, and it can only be installed on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x and 1.0.8.x.

Note: If after applying the security patch 7.9.23.04.SP21 or greater, you try to upgrade to 1.0.7.8, the upgrade might fail with the following error:

```plaintext
1. NodeosUpgrader.install Upgrade Detail: Component install for nodeos Caller Info:The call was made from 'NodeOSYosemiteInstaller.install' on line 100 with file located at '/localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/bundle_upgraders/../nodeos/node_os_yosemite_installer.py' Message: nodeos:NodeosUpgrader.install:Fatal Problem: Failed to install any new Node OS rpms...
```

Workaround:

1.  Run the following two commands from e1n1. Replace the `<your-1.0.7.8-upgrade-dir>` directory name in the commands with the actual upgrade directory name that you used on your system.
    1.  ```plaintext
        sed -i -e "0,/self._get_yum_repos_options() + ' ' + self.install_y/s/self._get_yum_repos_options() + ' ' + self.install_y/self._get_yum_repos_options() + ' ' + '--exclude=\"kernel*\"' + ' ' + self.install_y/" /localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/nodeos/node_os_installer.py
        ```
        
    2.  ```plaintext
        sed -i -e 's,self.verify_bundle,#self.verify_bundle,g' /opt/ibm/appliance/apupgrade/bin/apupgrade
        ```
        
2.  Rerun the same `apupgrade` command that failed:
    
    ```plaintext
    apupgrade --upgrade --upgrade-directory /localrepo --bundle system --use-version <your-1.0.7.8-upgrade-dir>
    ```
    

If you are upgrading from 1.0.7.x to 7.9.23.04.SP21, perform the following steps to avoid possible upgrade failure.

1.  Run the following commands in order.
    1.  ```plaintext
        apupgrade --upgrade-apupgrade --upgrade-directory /localrepo --use-version 7.9.23.04.SP21_release --bundle system
        ```
        
    2.  ```plaintext
        apupgrade --upgrade-details --upgrade-directory /localrepo --use-version 7.9.23.04.SP21_release --bundle system
        ```
        
    3.  ```plaintext
        apupgrade --preliminary-check --upgrade-directory /localrepo --use-version 7.9.23.04.SP21_release --bundle system
        ```
        
2.  Run the following command to start the upgrade.
    
    ```plaintext
    apupgrade --upgrade-directory /localrepo --use-version 7.9.23.04.SP21_release --bundle system --upgrade
    ```
    

The list of Red Hat CVEs, which are patched in this release:

```plaintext
CVE-2022-23521 Important/Sec. git-1.8.3.1-24.el7_9.x86_64 CVE-2022-41903 Important/Sec. git-1.8.3.1-24.el7_9.x86_64 CVE-2023-25690 Important/Sec. httpd-2.4.6-98.el7_9.7.x86_64 CVE-2023-25690 Important/Sec. httpd-tools-2.4.6-98.el7_9.7.x86_64 CVE-2022-4378 Important/Sec. kernel-3.10.0-1160.88.1.el7.x86_64 CVE-2022-42703 Important/Sec. kernel-3.10.0-1160.88.1.el7.x86_64 CVE-2022-4378 Important/Sec. kernel-debuginfo-3.10.0-1160.88.1.el7.x86_64 CVE-2022-42703 Important/Sec. kernel-debuginfo-3.10.0-1160.88.1.el7.x86_64 CVE-2022-4378 Important/Sec. kernel-debuginfo-3.10.0-1160.88.1.el7.x86_64 CVE-2022-42703 Important/Sec. kernel-debuginfo-3.10.0-1160.88.1.el7.x86_64 CVE-2022-4378 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.88.1.el7.x86_64 CVE-2022-42703 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.88.1.el7.x86_64 CVE-2022-4378 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.88.1.el7.x86_64 CVE-2022-42703 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.88.1.el7.x86_64 CVE-2022-4378 Important/Sec. kernel-devel-3.10.0-1160.88.1.el7.x86_64 CVE-2022-42703 Important/Sec. kernel-devel-3.10.0-1160.88.1.el7.x86_64 CVE-2022-4378 Important/Sec. kernel-headers-3.10.0-1160.88.1.el7.x86_64 CVE-2022-42703 Important/Sec. kernel-headers-3.10.0-1160.88.1.el7.x86_64 CVE-2022-4378 Important/Sec. kernel-tools-3.10.0-1160.88.1.el7.x86_64 CVE-2022-42703 Important/Sec. kernel-tools-3.10.0-1160.88.1.el7.x86_64 CVE-2022-4378 Important/Sec. kernel-tools-libs-3.10.0-1160.88.1.el7.x86_64 CVE-2022-42703 Important/Sec. kernel-tools-libs-3.10.0-1160.88.1.el7.x86_64 CVE-2022-38023 Important/Sec. libsmbclient-4.10.16-24.el7_9.x86_64 CVE-2022-38023 Important/Sec. libwbclient-4.10.16-24.el7_9.x86_64 CVE-2023-25690 Important/Sec. mod_session-2.4.6-98.el7_9.7.x86_64 CVE-2023-0767 Important/Sec. nss-3.79.0-5.el7_9.x86_64 CVE-2023-0767 Important/Sec. nss-sysinit-3.79.0-5.el7_9.x86_64 CVE-2023-0767 Important/Sec. nss-tools-3.79.0-5.el7_9.x86_64 CVE-2023-0286 Important/Sec. openssl-1:1.0.2k-26.el7_9.x86_64 CVE-2023-0286 Important/Sec. openssl-devel-1:1.0.2k-26.el7_9.x86_64 CVE-2023-0286 Important/Sec. openssl-libs-1:1.0.2k-26.el7_9.x86_64 CVE-2022-4378 Important/Sec. perf-3.10.0-1160.88.1.el7.x86_64 CVE-2022-42703 Important/Sec. perf-3.10.0-1160.88.1.el7.x86_64 CVE-2022-23521 Important/Sec. perl-Git-1.8.3.1-24.el7_9.noarch CVE-2022-41903 Important/Sec. perl-Git-1.8.3.1-24.el7_9.noarch CVE-2022-4378 Important/Sec. python-perf-3.10.0-1160.88.1.el7.x86_64 CVE-2022-42703 Important/Sec. python-perf-3.10.0-1160.88.1.el7.x86_64 CVE-2022-38023 Important/Sec. samba-4.10.16-24.el7_9.x86_64 CVE-2022-38023 Important/Sec. samba-client-4.10.16-24.el7_9.x86_64 CVE-2022-38023 Important/Sec. samba-client-libs-4.10.16-24.el7_9.x86_64 CVE-2022-38023 Important/Sec. samba-common-4.10.16-24.el7_9.noarch CVE-2022-38023 Important/Sec. samba-common-libs-4.10.16-24.el7_9.x86_64 CVE-2022-38023 Important/Sec. samba-common-tools-4.10.16-24.el7_9.x86_64 CVE-2022-38023 Important/Sec. samba-libs-4.10.16-24.el7_9.x86_64 CVE-2022-38023 Important/Sec. samba-python-4.10.16-24.el7_9.x86_64 CVE-2022-38023 Important/Sec. samba-winbind-4.10.16-24.el7_9.x86_64 CVE-2022-38023 Important/Sec. samba-winbind-modules-4.10.16-24.el7_9.x86_64 CVE-2022-37434 Moderate/Sec. zlib-1.2.7-21.el7_9.x86_64 CVE-2022-37434 Moderate/Sec. zlib-devel-1.2.7-21.el7_9.x86_64
```

## 7.9.23.02.SP20

The release date of the 7.9.23.02.SP20 security patch is 24 March 2023. This security patch includes the list of CVEs for January and February 2023.

The 7.9.23.02.SP20 patch is based on RHEL 7.9, and it can only be installed on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x and 1.0.8.x.

Important: The 7.9.23.02.SP20 is removed due to some upgrade issues. The issues are addressed in 7.9.23.04.SP21. Use 7.9.23.04.SP21 to get the CVEs addressed.

The list of Red Hat CVEs patched in this release:

```plaintext
CVE-2022-42920 Important/Sec. bcel-5.2-19.el7_9.noarch CVE-2021-25220 Moderate/Sec. bind-32:9.11.4-26.P2.el7_9.13.x86_64 CVE-2022-2795 Moderate/Sec. bind-32:9.11.4-26.P2.el7_9.13.x86_64 CVE-2021-25220 Moderate/Sec. bind-export-libs-32:9.11.4-26.P2.el7_9.13.x86_64 CVE-2022-2795 Moderate/Sec. bind-export-libs-32:9.11.4-26.P2.el7_9.13.x86_64 CVE-2021-25220 Moderate/Sec. bind-libs-32:9.11.4-26.P2.el7_9.13.x86_64 CVE-2022-2795 Moderate/Sec. bind-libs-32:9.11.4-26.P2.el7_9.13.x86_64 CVE-2021-25220 Moderate/Sec. bind-libs-lite-32:9.11.4-26.P2.el7_9.13.x86_64 CVE-2022-2795 Moderate/Sec. bind-libs-lite-32:9.11.4-26.P2.el7_9.13.x86_64 CVE-2021-25220 Moderate/Sec. bind-license-32:9.11.4-26.P2.el7_9.13.noarch CVE-2022-2795 Moderate/Sec. bind-license-32:9.11.4-26.P2.el7_9.13.noarch CVE-2021-25220 Moderate/Sec. bind-pkcs11-32:9.11.4-26.P2.el7_9.13.x86_64 CVE-2022-2795 Moderate/Sec. bind-pkcs11-32:9.11.4-26.P2.el7_9.13.x86_64 CVE-2021-25220 Moderate/Sec. bind-pkcs11-libs-32:9.11.4-26.P2.el7_9.13.x86_64 CVE-2022-2795 Moderate/Sec. bind-pkcs11-libs-32:9.11.4-26.P2.el7_9.13.x86_64 CVE-2021-25220 Moderate/Sec. bind-pkcs11-utils-32:9.11.4-26.P2.el7_9.13.x86_64 CVE-2022-2795 Moderate/Sec. bind-pkcs11-utils-32:9.11.4-26.P2.el7_9.13.x86_64 CVE-2021-25220 Moderate/Sec. bind-utils-32:9.11.4-26.P2.el7_9.13.x86_64 CVE-2022-2795 Moderate/Sec. bind-utils-32:9.11.4-26.P2.el7_9.13.x86_64 CVE-2022-28733 Important/Sec. grub2-1:2.02-0.87.el7_9.11.x86_64 CVE-2022-28733 Important/Sec. grub2-common-1:2.02-0.87.el7_9.11.noarch CVE-2022-28733 Important/Sec. grub2-pc-1:2.02-0.87.el7_9.11.x86_64 CVE-2022-28733 Important/Sec. grub2-pc-modules-1:2.02-0.87.el7_9.11.noarch CVE-2022-28733 Important/Sec. grub2-tools-1:2.02-0.87.el7_9.11.x86_64 CVE-2022-28733 Important/Sec. grub2-tools-extra-1:2.02-0.87.el7_9.11.x86_64 CVE-2022-28733 Important/Sec. grub2-tools-minimal-1:2.02-0.87.el7_9.11.x86_64 CVE-2023-21830 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.362.b08-1.el7_9.x86_64 CVE-2023-21843 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.362.b08-1.el7_9.x86_64 CVE-2023-21830 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.362.b08-1.el7_9.x86_64 CVE-2023-21843 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.362.b08-1.el7_9.x86_64 CVE-2021-26401 Important/Sec. kernel-3.10.0-1160.83.1.el7.x86_64 CVE-2022-2964 Important/Sec. kernel-3.10.0-1160.83.1.el7.x86_64 CVE-2021-26401 Important/Sec. kernel-debuginfo-3.10.0-1160.83.1.el7.x86_64 CVE-2022-2964 Important/Sec. kernel-debuginfo-3.10.0-1160.83.1.el7.x86_64 CVE-2021-26401 Important/Sec. kernel-debuginfo-3.10.0-1160.83.1.el7.x86_64 CVE-2022-2964 Important/Sec. kernel-debuginfo-3.10.0-1160.83.1.el7.x86_64 CVE-2021-26401 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.83.1.el7.x86_64 CVE-2022-2964 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.83.1.el7.x86_64 CVE-2021-26401 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.83.1.el7.x86_64 CVE-2022-2964 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.83.1.el7.x86_64 CVE-2021-26401 Important/Sec. kernel-devel-3.10.0-1160.83.1.el7.x86_64 CVE-2022-2964 Important/Sec. kernel-devel-3.10.0-1160.83.1.el7.x86_64 CVE-2021-26401 Important/Sec. kernel-headers-3.10.0-1160.83.1.el7.x86_64 CVE-2022-2964 Important/Sec. kernel-headers-3.10.0-1160.83.1.el7.x86_64 CVE-2021-26401 Important/Sec. kernel-tools-3.10.0-1160.83.1.el7.x86_64 CVE-2022-2964 Important/Sec. kernel-tools-3.10.0-1160.83.1.el7.x86_64 CVE-2021-26401 Important/Sec. kernel-tools-libs-3.10.0-1160.83.1.el7.x86_64 CVE-2022-2964 Important/Sec. kernel-tools-libs-3.10.0-1160.83.1.el7.x86_64 CVE-2022-4254 Important/Sec. libipa_hbac-1.16.5-10.el7_9.15.x86_64 CVE-2022-4254 Important/Sec. libsss_autofs-1.16.5-10.el7_9.15.x86_64 CVE-2022-4254 Important/Sec. libsss_certmap-1.16.5-10.el7_9.15.x86_64 CVE-2022-4254 Important/Sec. libsss_idmap-1.16.5-10.el7_9.15.x86_64 CVE-2022-4254 Important/Sec. libsss_nss_idmap-1.16.5-10.el7_9.15.x86_64 CVE-2022-4254 Important/Sec. libsss_simpleifp-1.16.5-10.el7_9.15.x86_64 CVE-2022-4254 Important/Sec. libsss_sudo-1.16.5-10.el7_9.15.x86_64 CVE-2021-26401 Important/Sec. perf-3.10.0-1160.83.1.el7.x86_64 CVE-2022-2964 Important/Sec. perf-3.10.0-1160.83.1.el7.x86_64 CVE-2022-2414 Important/Sec. pki-base-10.5.18-24.el7_9.noarch CVE-2022-2414 Important/Sec. pki-base-java-10.5.18-24.el7_9.noarch CVE-2022-2414 Important/Sec. pki-ca-10.5.18-24.el7_9.noarch CVE-2022-2414 Important/Sec. pki-kra-10.5.18-24.el7_9.noarch CVE-2022-2414 Important/Sec. pki-server-10.5.18-24.el7_9.noarch CVE-2022-2414 Important/Sec. pki-tools-10.5.18-24.el7_9.x86_64 CVE-2022-4254 Important/Sec. python-libipa_hbac-1.16.5-10.el7_9.15.x86_64 CVE-2022-4254 Important/Sec. python-libsss_nss_idmap-1.16.5-10.el7_9.15.x86_64 CVE-2021-26401 Important/Sec. python-perf-3.10.0-1160.83.1.el7.x86_64 CVE-2022-2964 Important/Sec. python-perf-3.10.0-1160.83.1.el7.x86_64 CVE-2022-4254 Important/Sec. python-sss-1.16.5-10.el7_9.15.x86_64 CVE-2022-4254 Important/Sec. python-sss-murmur-1.16.5-10.el7_9.15.x86_64 CVE-2022-4254 Important/Sec. python-sssdconfig-1.16.5-10.el7_9.15.noarch CVE-2022-4254 Important/Sec. sssd-1.16.5-10.el7_9.15.x86_64 CVE-2022-4254 Important/Sec. sssd-ad-1.16.5-10.el7_9.15.x86_64 CVE-2022-4254 Important/Sec. sssd-client-1.16.5-10.el7_9.15.x86_64 CVE-2022-4254 Important/Sec. sssd-common-1.16.5-10.el7_9.15.x86_64 CVE-2022-4254 Important/Sec. sssd-common-pac-1.16.5-10.el7_9.15.x86_64 CVE-2022-4254 Important/Sec. sssd-dbus-1.16.5-10.el7_9.15.x86_64 CVE-2022-4254 Important/Sec. sssd-ipa-1.16.5-10.el7_9.15.x86_64 CVE-2022-4254 Important/Sec. sssd-krb5-1.16.5-10.el7_9.15.x86_64 CVE-2022-4254 Important/Sec. sssd-krb5-common-1.16.5-10.el7_9.15.x86_64 CVE-2022-4254 Important/Sec. sssd-ldap-1.16.5-10.el7_9.15.x86_64 CVE-2022-4254 Important/Sec. sssd-proxy-1.16.5-10.el7_9.15.x86_64 CVE-2022-4254 Important/Sec. sssd-tools-1.16.5-10.el7_9.15.x86_64 CVE-2023-22809 Important/Sec. sudo-1.8.23-10.el7_9.3.x86_64
```

## 7.9.22.12.SP19

The release date of the 7.9.22.12.SP19 security patch is 3 January 2023. The estimated run time is around 54 minutes. This security patch includes the list of CVEs for November and December 2022.

The 7.9.22.12.SP19 patch is based on RHEL 7.9, and it can only be installed on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x.

Note: If after applying the security patch 7.9.22.12.SP19 or greater, you try to upgrade to 1.0.7.8, the upgrade might fail with the following error:

```plaintext
1. NodeosUpgrader.install Upgrade Detail: Component install for nodeos Caller Info:The call was made from 'NodeOSYosemiteInstaller.install' on line 100 with file located at '/localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/bundle_upgraders/../nodeos/node_os_yosemite_installer.py' Message: nodeos:NodeosUpgrader.install:Fatal Problem: Failed to install any new Node OS rpms...
```

Workaround:

1.  Run the following two commands from e1n1. Replace the `<your-1.0.7.8-upgrade-dir>` directory name in the commands with the actual upgrade directory name that you used on your system.
    1.  ```plaintext
        sed -i -e "0,/self._get_yum_repos_options() + ' ' + self.install_y/s/self._get_yum_repos_options() + ' ' + self.install_y/self._get_yum_repos_options() + ' ' + '--exclude=\"kernel*\"' + ' ' + self.install_y/" /localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/nodeos/node_os_installer.py
        ```
        
    2.  ```plaintext
        sed -i -e 's,self.verify_bundle,#self.verify_bundle,g' /opt/ibm/appliance/apupgrade/bin/apupgrade
        ```
        
2.  Rerun the same `apupgrade` command that failed:
    
    ```plaintext
    apupgrade --upgrade --upgrade-directory /localrepo --bundle system --use-version <your-1.0.7.8-upgrade-dir>
    ```
    

The list of Red Hat CVEs patched in this release:

```plaintext
CVE-2022-2850 Moderate/Sec. 389-ds-base-1.3.10.2-17.el7_9.x86_64 CVE-2022-2850 Moderate/Sec. 389-ds-base-libs-1.3.10.2-17.el7_9.x86_64 CVE-2022-41974 Important/Sec. device-mapper-multipath-0.4.9-136.el7_9.x86_64 CVE-2022-41974 Important/Sec. device-mapper-multipath-libs-0.4.9-136.el7_9.x86_64 CVE-2022-21619 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.352.b08-2.el7_9.x86_64 CVE-2022-21624 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.352.b08-2.el7_9.x86_64 CVE-2022-21626 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.352.b08-2.el7_9.x86_64 CVE-2022-21628 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.352.b08-2.el7_9.x86_64 CVE-2022-21619 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.352.b08-2.el7_9.x86_64 CVE-2022-21624 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.352.b08-2.el7_9.x86_64 CVE-2022-21626 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.352.b08-2.el7_9.x86_64 CVE-2022-21628 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.352.b08-2.el7_9.x86_64 CVE-2022-2588 Important/Sec. kernel-3.10.0-1160.80.1.el7.x86_64 CVE-2022-23816 Important/Sec. kernel-3.10.0-1160.80.1.el7.x86_64 CVE-2022-23825 Important/Sec. kernel-3.10.0-1160.80.1.el7.x86_64 CVE-2022-26373 Important/Sec. kernel-3.10.0-1160.80.1.el7.x86_64 CVE-2022-29900 Important/Sec. kernel-3.10.0-1160.80.1.el7.x86_64 CVE-2022-29901 Important/Sec. kernel-3.10.0-1160.80.1.el7.x86_64 CVE-2022-2588 Important/Sec. kernel-debuginfo-3.10.0-1160.80.1.el7.x86_64 CVE-2022-23816 Important/Sec. kernel-debuginfo-3.10.0-1160.80.1.el7.x86_64 CVE-2022-23825 Important/Sec. kernel-debuginfo-3.10.0-1160.80.1.el7.x86_64 CVE-2022-26373 Important/Sec. kernel-debuginfo-3.10.0-1160.80.1.el7.x86_64 CVE-2022-29900 Important/Sec. kernel-debuginfo-3.10.0-1160.80.1.el7.x86_64 CVE-2022-29901 Important/Sec. kernel-debuginfo-3.10.0-1160.80.1.el7.x86_64 CVE-2022-2588 Important/Sec. kernel-debuginfo-3.10.0-1160.80.1.el7.x86_64 CVE-2022-23816 Important/Sec. kernel-debuginfo-3.10.0-1160.80.1.el7.x86_64 CVE-2022-23825 Important/Sec. kernel-debuginfo-3.10.0-1160.80.1.el7.x86_64 CVE-2022-26373 Important/Sec. kernel-debuginfo-3.10.0-1160.80.1.el7.x86_64 CVE-2022-29900 Important/Sec. kernel-debuginfo-3.10.0-1160.80.1.el7.x86_64 CVE-2022-29901 Important/Sec. kernel-debuginfo-3.10.0-1160.80.1.el7.x86_64 CVE-2022-2588 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.80.1.el7.x86_64 CVE-2022-23816 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.80.1.el7.x86_64 CVE-2022-23825 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.80.1.el7.x86_64 CVE-2022-26373 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.80.1.el7.x86_64 CVE-2022-29900 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.80.1.el7.x86_64 CVE-2022-29901 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.80.1.el7.x86_64 CVE-2022-2588 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.80.1.el7.x86_64 CVE-2022-23816 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.80.1.el7.x86_64 CVE-2022-23825 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.80.1.el7.x86_64 CVE-2022-26373 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.80.1.el7.x86_64 CVE-2022-29900 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.80.1.el7.x86_64 CVE-2022-29901 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.80.1.el7.x86_64 CVE-2022-2588 Important/Sec. kernel-devel-3.10.0-1160.80.1.el7.x86_64 CVE-2022-23816 Important/Sec. kernel-devel-3.10.0-1160.80.1.el7.x86_64 CVE-2022-23825 Important/Sec. kernel-devel-3.10.0-1160.80.1.el7.x86_64 CVE-2022-26373 Important/Sec. kernel-devel-3.10.0-1160.80.1.el7.x86_64 CVE-2022-29900 Important/Sec. kernel-devel-3.10.0-1160.80.1.el7.x86_64 CVE-2022-29901 Important/Sec. kernel-devel-3.10.0-1160.80.1.el7.x86_64 CVE-2022-2588 Important/Sec. kernel-headers-3.10.0-1160.80.1.el7.x86_64 CVE-2022-23816 Important/Sec. kernel-headers-3.10.0-1160.80.1.el7.x86_64 CVE-2022-23825 Important/Sec. kernel-headers-3.10.0-1160.80.1.el7.x86_64 CVE-2022-26373 Important/Sec. kernel-headers-3.10.0-1160.80.1.el7.x86_64 CVE-2022-29900 Important/Sec. kernel-headers-3.10.0-1160.80.1.el7.x86_64 CVE-2022-29901 Important/Sec. kernel-headers-3.10.0-1160.80.1.el7.x86_64 CVE-2022-2588 Important/Sec. kernel-tools-3.10.0-1160.80.1.el7.x86_64 CVE-2022-23816 Important/Sec. kernel-tools-3.10.0-1160.80.1.el7.x86_64 CVE-2022-23825 Important/Sec. kernel-tools-3.10.0-1160.80.1.el7.x86_64 CVE-2022-26373 Important/Sec. kernel-tools-3.10.0-1160.80.1.el7.x86_64 CVE-2022-29900 Important/Sec. kernel-tools-3.10.0-1160.80.1.el7.x86_64 CVE-2022-29901 Important/Sec. kernel-tools-3.10.0-1160.80.1.el7.x86_64 CVE-2022-2588 Important/Sec. kernel-tools-libs-3.10.0-1160.80.1.el7.x86_64 CVE-2022-23816 Important/Sec. kernel-tools-libs-3.10.0-1160.80.1.el7.x86_64 CVE-2022-23825 Important/Sec. kernel-tools-libs-3.10.0-1160.80.1.el7.x86_64 CVE-2022-26373 Important/Sec. kernel-tools-libs-3.10.0-1160.80.1.el7.x86_64 CVE-2022-29900 Important/Sec. kernel-tools-libs-3.10.0-1160.80.1.el7.x86_64 CVE-2022-29901 Important/Sec. kernel-tools-libs-3.10.0-1160.80.1.el7.x86_64 CVE-2022-41974 Important/Sec. kpartx-0.4.9-136.el7_9.x86_64 CVE-2022-2588 Important/Sec. perf-3.10.0-1160.80.1.el7.x86_64 CVE-2022-23816 Important/Sec. perf-3.10.0-1160.80.1.el7.x86_64 CVE-2022-23825 Important/Sec. perf-3.10.0-1160.80.1.el7.x86_64 CVE-2022-26373 Important/Sec. perf-3.10.0-1160.80.1.el7.x86_64 CVE-2022-29900 Important/Sec. perf-3.10.0-1160.80.1.el7.x86_64 CVE-2022-29901 Important/Sec. perf-3.10.0-1160.80.1.el7.x86_64 CVE-2022-2393 Moderate/Sec. pki-base-10.5.18-23.el7_9.noarch CVE-2022-2393 Moderate/Sec. pki-base-java-10.5.18-23.el7_9.noarch CVE-2022-2393 Moderate/Sec. pki-ca-10.5.18-23.el7_9.noarch CVE-2022-2393 Moderate/Sec. pki-kra-10.5.18-23.el7_9.noarch CVE-2022-2393 Moderate/Sec. pki-server-10.5.18-23.el7_9.noarch CVE-2022-2393 Moderate/Sec. pki-tools-10.5.18-23.el7_9.x86_64 CVE-2022-2588 Important/Sec. python-perf-3.10.0-1160.80.1.el7.x86_64 CVE-2022-23816 Important/Sec. python-perf-3.10.0-1160.80.1.el7.x86_64 CVE-2022-23825 Important/Sec. python-perf-3.10.0-1160.80.1.el7.x86_64 CVE-2022-26373 Important/Sec. python-perf-3.10.0-1160.80.1.el7.x86_64 CVE-2022-29900 Important/Sec. python-perf-3.10.0-1160.80.1.el7.x86_64 CVE-2022-29901 Important/Sec. python-perf-3.10.0-1160.80.1.el7.x86_64 CVE-2022-41853 Important/Sec. hsqldb-1:1.8.1.3-15.el7_9.noarch CVE-2022-42898 Important/Sec. krb5-devel-1.15.1-55.el7_9.x86_64 CVE-2022-42898 Important/Sec. krb5-libs-1.15.1-55.el7_9.x86_64 CVE-2022-42898 Important/Sec. krb5-pkinit-1.15.1-55.el7_9.x86_64 CVE-2022-42898 Important/Sec. krb5-server-1.15.1-55.el7_9.x86_64 CVE-2022-42898 Important/Sec. krb5-workstation-1.15.1-55.el7_9.x86_64 CVE-2022-42898 Important/Sec. libkadm5-1.15.1-55.el7_9.x86_64 CVE-2021-29740 gpfs.adv-5.1.2-7.x86_64
```

## 7.9.22.10.SP18

The release date of the 7.9.22.10.SP18 security patch is 26 October 2022. The estimated run time is around 60 minutes.

The 7.9.22.10.SP18 patch is based on RHEL 7.9, and it can only be installed on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x.

Note: If after applying the security patch 7.9.22.10.SP18 or greater, you try to upgrade to 1.0.7.8, the upgrade might fail with the following error:

```plaintext
1. NodeosUpgrader.install Upgrade Detail: Component install for nodeos Caller Info:The call was made from 'NodeOSYosemiteInstaller.install' on line 100 with file located at '/localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/bundle_upgraders/../nodeos/node_os_yosemite_installer.py' Message: nodeos:NodeosUpgrader.install:Fatal Problem: Failed to install any new Node OS rpms...
```

Workaround:

1.  Run the following two commands from e1n1. Replace the `<your-1.0.7.8-upgrade-dir>` directory name in the commands with the actual upgrade directory name that you used on your system.
    1.  ```plaintext
        sed -i -e "0,/self._get_yum_repos_options() + ' ' + self.install_y/s/self._get_yum_repos_options() + ' ' + self.install_y/self._get_yum_repos_options() + ' ' + '--exclude=\"kernel*\"' + ' ' + self.install_y/" /localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/nodeos/node_os_installer.py
        ```
        
    2.  ```plaintext
        sed -i -e 's,self.verify_bundle,#self.verify_bundle,g' /opt/ibm/appliance/apupgrade/bin/apupgrade
        ```
        
2.  Rerun the same `apupgrade` command that failed:
    
    ```plaintext
    apupgrade --upgrade --upgrade-directory /localrepo --bundle system --use-version <your-1.0.7.8-upgrade-dir>
    ```
    

The list of Red Hat CVEs patched in this release:

```plaintext
CVE-2022-38177 Important/Sec. bind-32:9.11.4-26.P2.el7_9.10.x86_64 CVE-2022-38178 Important/Sec. bind-32:9.11.4-26.P2.el7_9.10.x86_64 CVE-2022-38177 Important/Sec. bind-export-libs-32:9.11.4-26.P2.el7_9.10.x86_64 CVE-2022-38178 Important/Sec. bind-export-libs-32:9.11.4-26.P2.el7_9.10.x86_64 CVE-2022-38177 Important/Sec. bind-libs-32:9.11.4-26.P2.el7_9.10.x86_64 CVE-2022-38178 Important/Sec. bind-libs-32:9.11.4-26.P2.el7_9.10.x86_64 CVE-2022-38177 Important/Sec. bind-libs-lite-32:9.11.4-26.P2.el7_9.10.x86_64 CVE-2022-38178 Important/Sec. bind-libs-lite-32:9.11.4-26.P2.el7_9.10.x86_64 CVE-2022-38177 Important/Sec. bind-license-32:9.11.4-26.P2.el7_9.10.noarch CVE-2022-38178 Important/Sec. bind-license-32:9.11.4-26.P2.el7_9.10.noarch CVE-2022-38177 Important/Sec. bind-pkcs11-32:9.11.4-26.P2.el7_9.10.x86_64 CVE-2022-38178 Important/Sec. bind-pkcs11-32:9.11.4-26.P2.el7_9.10.x86_64 CVE-2022-38177 Important/Sec. bind-pkcs11-libs-32:9.11.4-26.P2.el7_9.10.x86_64 CVE-2022-38178 Important/Sec. bind-pkcs11-libs-32:9.11.4-26.P2.el7_9.10.x86_64 CVE-2022-38177 Important/Sec. bind-pkcs11-utils-32:9.11.4-26.P2.el7_9.10.x86_64 CVE-2022-38178 Important/Sec. bind-pkcs11-utils-32:9.11.4-26.P2.el7_9.10.x86_64 CVE-2022-38177 Important/Sec. bind-utils-32:9.11.4-26.P2.el7_9.10.x86_64 CVE-2022-38178 Important/Sec. bind-utils-32:9.11.4-26.P2.el7_9.10.x86_64 CVE-2022-40674 Important/Sec. expat-2.1.0-15.el7_9.x86_64 updateinfo list done
```

## 7.9.22.09.SP17

The security patch released in September 2022. The estimated run time is around 60 minutes.

The 7.9.22.09.SP17 patch is based on RHEL 7.9, and it can only be installed on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x.

Note: If after applying the security patch 7.9.22.09.SP17 or greater, you try to upgrade to 1.0.7.8, the upgrade might fail with the following error:

```plaintext
1. NodeosUpgrader.install Upgrade Detail: Component install for nodeos Caller Info:The call was made from 'NodeOSYosemiteInstaller.install' on line 100 with file located at '/localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/bundle_upgraders/../nodeos/node_os_yosemite_installer.py' Message: nodeos:NodeosUpgrader.install:Fatal Problem: Failed to install any new Node OS rpms...
```

Workaround:

1.  Run the following two commands from e1n1. Replace the `<your-1.0.7.8-upgrade-dir>` directory name in the commands with the actual upgrade directory name that you used on your system.
    1.  ```plaintext
        sed -i -e "0,/self._get_yum_repos_options() + ' ' + self.install_y/s/self._get_yum_repos_options() + ' ' + self.install_y/self._get_yum_repos_options() + ' ' + '--exclude=\"kernel*\"' + ' ' + self.install_y/" /localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/nodeos/node_os_installer.py
        ```
        
    2.  ```plaintext
        sed -i -e 's,self.verify_bundle,#self.verify_bundle,g' /opt/ibm/appliance/apupgrade/bin/apupgrade
        ```
        
2.  Rerun the same `apupgrade` command that failed:
    
    ```plaintext
    apupgrade --upgrade --upgrade-directory /localrepo --bundle system --use-version <your-1.0.7.8-upgrade-dir>
    ```
    

The list of Red Hat CVEs patched in this release:

```plaintext
CVE-2022-21123 Moderate/Sec. kernel-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21125 Moderate/Sec. kernel-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21166 Moderate/Sec. kernel-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21123 Moderate/Sec. kernel-debuginfo-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21125 Moderate/Sec. kernel-debuginfo-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21166 Moderate/Sec. kernel-debuginfo-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21123 Moderate/Sec. kernel-debuginfo-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21125 Moderate/Sec. kernel-debuginfo-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21166 Moderate/Sec. kernel-debuginfo-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21123 Moderate/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21125 Moderate/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21166 Moderate/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21123 Moderate/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21125 Moderate/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21166 Moderate/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21123 Moderate/Sec. kernel-devel-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21125 Moderate/Sec. kernel-devel-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21166 Moderate/Sec. kernel-devel-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21123 Moderate/Sec. kernel-headers-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21125 Moderate/Sec. kernel-headers-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21166 Moderate/Sec. kernel-headers-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21123 Moderate/Sec. kernel-tools-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21125 Moderate/Sec. kernel-tools-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21166 Moderate/Sec. kernel-tools-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21123 Moderate/Sec. kernel-tools-libs-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21125 Moderate/Sec. kernel-tools-libs-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21166 Moderate/Sec. kernel-tools-libs-3.10.0-1160.76.1.el7.x86_64 CVE-2022-2526 Important/Sec. libgudev1-219-78.el7_9.7.x86_64 CVE-2022-21123 Moderate/Sec. perf-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21125 Moderate/Sec. perf-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21166 Moderate/Sec. perf-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21123 Moderate/Sec. python-perf-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21125 Moderate/Sec. python-perf-3.10.0-1160.76.1.el7.x86_64 CVE-2022-21166 Moderate/Sec. python-perf-3.10.0-1160.76.1.el7.x86_64 CVE-2022-29154 Important/Sec. rsync-3.1.2-11.el7_9.x86_64 CVE-2022-2526 Important/Sec. systemd-219-78.el7_9.7.x86_64 CVE-2022-2526 Important/Sec. systemd-libs-219-78.el7_9.7.x86_64 CVE-2022-2526 Important/Sec. systemd-python-219-78.el7_9.7.x86_64 CVE-2022-2526 Important/Sec. systemd-sysv-219-78.el7_9.7.x86_64
```

## 7.9.22.08.SP16

The security patch released in August 2022. The estimated run time is around 60 minutes.

The 7.9.22.08.SP16 patch is based on RHEL 7.9, and it can only be installed on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x.

Note: If after applying the security patch 7.9.22.08.SP16 or greater, you try to upgrade to 1.0.7.8, the upgrade might fail with the following error:

```plaintext
1. NodeosUpgrader.install Upgrade Detail: Component install for nodeos Caller Info:The call was made from 'NodeOSYosemiteInstaller.install' on line 100 with file located at '/localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/bundle_upgraders/../nodeos/node_os_yosemite_installer.py' Message: nodeos:NodeosUpgrader.install:Fatal Problem: Failed to install any new Node OS rpms...
```

Workaround:

1.  Run the following two commands from e1n1. Replace the `<your-1.0.7.8-upgrade-dir>` directory name in the commands with the actual upgrade directory name that you used on your system.
    1.  ```plaintext
        sed -i -e "0,/self._get_yum_repos_options() + ' ' + self.install_y/s/self._get_yum_repos_options() + ' ' + self.install_y/self._get_yum_repos_options() + ' ' + '--exclude=\"kernel*\"' + ' ' + self.install_y/" /localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/nodeos/node_os_installer.py
        ```
        
    2.  ```plaintext
        sed -i -e 's,self.verify_bundle,#self.verify_bundle,g' /opt/ibm/appliance/apupgrade/bin/apupgrade
        ```
        
2.  Rerun the same `apupgrade` command that failed:
    
    ```plaintext
    apupgrade --upgrade --upgrade-directory /localrepo --bundle system --use-version <your-1.0.7.8-upgrade-dir>
    ```
    

The list of Red Hat CVEs patched in this release:

```plaintext
CVE-2022-21540 Important/Sec. java-1.8.0-openjdk-1:1.8.0.342.b07-1.el7_9.x86_64 CVE-2022-21541 Important/Sec. java-1.8.0-openjdk-1:1.8.0.342.b07-1.el7_9.x86_64 CVE-2022-34169 Important/Sec. java-1.8.0-openjdk-1:1.8.0.342.b07-1.el7_9.x86_64 CVE-2022-21540 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.342.b07-1.el7_9.x86_64 CVE-2022-21541 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.342.b07-1.el7_9.x86_64 CVE-2022-34169 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.342.b07-1.el7_9.x86_64
```

## 7.9.22.07.SP15

The security patch released in July 2022. The estimated run time is around 60 minutes.

The 7.9.22.07.SP15 patch is based on RHEL 7.9, and it can only be installed on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x.

Note: If after applying the security patch 7.9.22.07.SP15 or greater, you try to upgrade to 1.0.7.8, the upgrade might fail with the following error:

```plaintext
1. NodeosUpgrader.install Upgrade Detail: Component install for nodeos Caller Info:The call was made from 'NodeOSYosemiteInstaller.install' on line 100 with file located at '/localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/bundle_upgraders/../nodeos/node_os_yosemite_installer.py' Message: nodeos:NodeosUpgrader.install:Fatal Problem: Failed to install any new Node OS rpms...
```

Workaround:

1.  Run the following two commands from e1n1. Replace the `<your-1.0.7.8-upgrade-dir>` directory name in the commands with the actual upgrade directory name that you used on your system.
    1.  ```plaintext
        sed -i -e "0,/self._get_yum_repos_options() + ' ' + self.install_y/s/self._get_yum_repos_options() + ' ' + self.install_y/self._get_yum_repos_options() + ' ' + '--exclude=\"kernel*\"' + ' ' + self.install_y/" /localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/nodeos/node_os_installer.py
        ```
        
    2.  ```plaintext
        sed -i -e 's,self.verify_bundle,#self.verify_bundle,g' /opt/ibm/appliance/apupgrade/bin/apupgrade
        ```
        
2.  Rerun the same `apupgrade` command that failed:
    
    ```plaintext
    apupgrade --upgrade --upgrade-directory /localrepo --bundle system --use-version <your-1.0.7.8-upgrade-dir>
    ```
    

The list of Red Hat CVEs patched in this release:

```plaintext
CVE-2022-0918 Moderate/Sec. 389-ds-base-1.3.10.2-16.el7_9.x86_64 CVE-2022-0996 Moderate/Sec. 389-ds-base-1.3.10.2-16.el7_9.x86_64 CVE-2022-0918 Moderate/Sec. 389-ds-base-libs-1.3.10.2-16.el7_9.x86_64 CVE-2022-0996 Moderate/Sec. 389-ds-base-libs-1.3.10.2-16.el7_9.x86_64 CVE-2022-1729 Important/Sec. kernel-3.10.0-1160.71.1.el7.x86_64 CVE-2022-1966 Important/Sec. kernel-3.10.0-1160.71.1.el7.x86_64 CVE-2022-32250 Important/Sec. kernel-3.10.0-1160.71.1.el7.x86_64 CVE-2022-1729 Important/Sec. kernel-debuginfo-3.10.0-1160.71.1.el7.x86_64 CVE-2022-1966 Important/Sec. kernel-debuginfo-3.10.0-1160.71.1.el7.x86_64 CVE-2022-32250 Important/Sec. kernel-debuginfo-3.10.0-1160.71.1.el7.x86_64 CVE-2022-1729 Important/Sec. kernel-debuginfo-3.10.0-1160.71.1.el7.x86_64 CVE-2022-1966 Important/Sec. kernel-debuginfo-3.10.0-1160.71.1.el7.x86_64 CVE-2022-32250 Important/Sec. kernel-debuginfo-3.10.0-1160.71.1.el7.x86_64 CVE-2022-1729 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.71.1.el7.x86_64 CVE-2022-1966 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.71.1.el7.x86_64 CVE-2022-32250 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.71.1.el7.x86_64 CVE-2022-1729 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.71.1.el7.x86_64 CVE-2022-1966 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.71.1.el7.x86_64 CVE-2022-32250 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.71.1.el7.x86_64 CVE-2022-1729 Important/Sec. kernel-devel-3.10.0-1160.71.1.el7.x86_64 CVE-2022-1966 Important/Sec. kernel-devel-3.10.0-1160.71.1.el7.x86_64 CVE-2022-32250 Important/Sec. kernel-devel-3.10.0-1160.71.1.el7.x86_64 CVE-2022-1729 Important/Sec. kernel-headers-3.10.0-1160.71.1.el7.x86_64 CVE-2022-1966 Important/Sec. kernel-headers-3.10.0-1160.71.1.el7.x86_64 CVE-2022-32250 Important/Sec. kernel-headers-3.10.0-1160.71.1.el7.x86_64 CVE-2022-1729 Important/Sec. kernel-tools-3.10.0-1160.71.1.el7.x86_64 CVE-2022-1966 Important/Sec. kernel-tools-3.10.0-1160.71.1.el7.x86_64 CVE-2022-32250 Important/Sec. kernel-tools-3.10.0-1160.71.1.el7.x86_64 CVE-2022-1729 Important/Sec. kernel-tools-libs-3.10.0-1160.71.1.el7.x86_64 CVE-2022-1966 Important/Sec. kernel-tools-libs-3.10.0-1160.71.1.el7.x86_64 CVE-2022-32250 Important/Sec. kernel-tools-libs-3.10.0-1160.71.1.el7.x86_64 CVE-2022-1729 Important/Sec. perf-3.10.0-1160.71.1.el7.x86_64 CVE-2022-1966 Important/Sec. perf-3.10.0-1160.71.1.el7.x86_64 CVE-2022-32250 Important/Sec. perf-3.10.0-1160.71.1.el7.x86_64 CVE-2020-26116 Moderate/Sec. python-2.7.5-92.el7_9.x86_64 CVE-2020-26137 Moderate/Sec. python-2.7.5-92.el7_9.x86_64 CVE-2021-3177 Moderate/Sec. python-2.7.5-92.el7_9.x86_64 CVE-2020-26116 Moderate/Sec. python-devel-2.7.5-92.el7_9.x86_64 CVE-2020-26137 Moderate/Sec. python-devel-2.7.5-92.el7_9.x86_64 CVE-2021-3177 Moderate/Sec. python-devel-2.7.5-92.el7_9.x86_64 CVE-2020-26116 Moderate/Sec. python-libs-2.7.5-92.el7_9.x86_64 CVE-2020-26137 Moderate/Sec. python-libs-2.7.5-92.el7_9.x86_64 CVE-2021-3177 Moderate/Sec. python-libs-2.7.5-92.el7_9.x86_64 CVE-2022-1729 Important/Sec. python-perf-3.10.0-1160.71.1.el7.x86_64 CVE-2022-1966 Important/Sec. python-perf-3.10.0-1160.71.1.el7.x86_64 CVE-2022-32250 Important/Sec. python-perf-3.10.0-1160.71.1.el7.x86_64 CVE-2022-1271 Important/Sec. xz-5.2.2-2.el7_9.x86_64 CVE-2022-1271 Important/Sec. xz-devel-5.2.2-2.el7_9.x86_64 CVE-2022-1271 Important/Sec. xz-libs-5.2.2-2.el7_9.x86_64
```

## 7.9.22.06.SP14

The security patch released in June 2022. The estimated run time is around 60 minutes.

The 7.9.22.06.SP14 patch is based on RHEL 7.9, and it can only be installed on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x.

Note: If after applying the security patch 7.9.22.06.SP14 or greater, you try to upgrade to 1.0.7.8, the upgrade might fail with the following error:

```plaintext
1. NodeosUpgrader.install Upgrade Detail: Component install for nodeos Caller Info:The call was made from 'NodeOSYosemiteInstaller.install' on line 100 with file located at '/localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/bundle_upgraders/../nodeos/node_os_yosemite_installer.py' Message: nodeos:NodeosUpgrader.install:Fatal Problem: Failed to install any new Node OS rpms...
```

Workaround:

1.  Run the following two commands from e1n1. Replace the `<your-1.0.7.8-upgrade-dir>` directory name in the commands with the actual upgrade directory name that you used on your system.
    1.  ```plaintext
        sed -i -e "0,/self._get_yum_repos_options() + ' ' + self.install_y/s/self._get_yum_repos_options() + ' ' + self.install_y/self._get_yum_repos_options() + ' ' + '--exclude=\"kernel*\"' + ' ' + self.install_y/" /localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/nodeos/node_os_installer.py
        ```
        
    2.  ```plaintext
        sed -i -e 's,self.verify_bundle,#self.verify_bundle,g' /opt/ibm/appliance/apupgrade/bin/apupgrade
        ```
        
2.  Rerun the same `apupgrade` command that failed:
    
    ```plaintext
    apupgrade --upgrade --upgrade-directory /localrepo --bundle system --use-version <your-1.0.7.8-upgrade-dir>
    ```
    

The list of Red Hat CVEs patched in this release:

```plaintext
CVE-2022-24903 Important/Sec. rsyslog-8.24.0-57.el7_9.3.x86_64
```

## 7.9.22.05.SP13

The security patch released in June 2022. The estimated run time is around 60 minutes.

The 7.9.22.05.SP13 patch is based on RHEL 7.9, and it can only be installed on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x.

Note: If after applying the security patch 7.9.22.05.SP13 or greater, you try to upgrade to 1.0.7.8, the upgrade might fail with the following error:

```plaintext
1. NodeosUpgrader.install Upgrade Detail: Component install for nodeos Caller Info:The call was made from 'NodeOSYosemiteInstaller.install' on line 100 with file located at '/localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/bundle_upgraders/../nodeos/node_os_yosemite_installer.py' Message: nodeos:NodeosUpgrader.install:Fatal Problem: Failed to install any new Node OS rpms...
```

Workaround:

1.  Run the following two commands from e1n1. Replace the `<your-1.0.7.8-upgrade-dir>` directory name in the commands with the actual upgrade directory name that you used on your system.
    1.  ```plaintext
        sed -i -e "0,/self._get_yum_repos_options() + ' ' + self.install_y/s/self._get_yum_repos_options() + ' ' + self.install_y/self._get_yum_repos_options() + ' ' + '--exclude=\"kernel*\"' + ' ' + self.install_y/" /localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/nodeos/node_os_installer.py
        ```
        
    2.  ```plaintext
        sed -i -e 's,self.verify_bundle,#self.verify_bundle,g' /opt/ibm/appliance/apupgrade/bin/apupgrade
        ```
        
2.  Rerun the same `apupgrade` command that failed:
    
    ```plaintext
    apupgrade --upgrade --upgrade-directory /localrepo --bundle system --use-version <your-1.0.7.8-upgrade-dir>
    ```
    

The list of Red Hat CVEs patched in this release:

```plaintext
CVE-2022-1271 Important/Sec. gzip-1.5-11.el7_9.x86_64 CVE-2022-21426 Important/Sec. java-1.8.0-openjdk-1:1.8.0.332.b09-1.el7_9.x86_64 CVE-2022-21434 Important/Sec. java-1.8.0-openjdk-1:1.8.0.332.b09-1.el7_9.x86_64 CVE-2022-21443 Important/Sec. java-1.8.0-openjdk-1:1.8.0.332.b09-1.el7_9.x86_64 CVE-2022-21476 Important/Sec. java-1.8.0-openjdk-1:1.8.0.332.b09-1.el7_9.x86_64 CVE-2022-21496 Important/Sec. java-1.8.0-openjdk-1:1.8.0.332.b09-1.el7_9.x86_64 CVE-2022-21426 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.332.b09-1.el7_9.x86_64 CVE-2022-21434 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.332.b09-1.el7_9.x86_64 CVE-2022-21443 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.332.b09-1.el7_9.x86_64 CVE-2022-21476 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.332.b09-1.el7_9.x86_64 CVE-2022-21496 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.332.b09-1.el7_9.x86_64 CVE-2022-0492 Important/Sec. kernel-3.10.0-1160.66.1.el7.x86_64 CVE-2020-8648 Important/Sec. kernel-debuginfo-3.10.0-1160.31.1.el7.x86_64 CVE-2020-12362 Important/Sec. kernel-debuginfo-3.10.0-1160.31.1.el7.x86_64 CVE-2020-12363 Important/Sec. kernel-debuginfo-3.10.0-1160.31.1.el7.x86_64 CVE-2020-12364 Important/Sec. kernel-debuginfo-3.10.0-1160.31.1.el7.x86_64 CVE-2020-27170 Important/Sec. kernel-debuginfo-3.10.0-1160.31.1.el7.x86_64 CVE-2021-3347 Important/Sec. kernel-debuginfo-3.10.0-1160.31.1.el7.x86_64 CVE-2019-20934 Important/Sec. kernel-debuginfo-3.10.0-1160.36.2.el7.x86_64 CVE-2020-11668 Important/Sec. kernel-debuginfo-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33033 Important/Sec. kernel-debuginfo-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33034 Important/Sec. kernel-debuginfo-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33909 Important/Sec. kernel-debuginfo-3.10.0-1160.36.2.el7.x86_64 CVE-2020-27777 Important/Sec. kernel-debuginfo-3.10.0-1160.41.1.el7.x86_64 CVE-2021-22555 Important/Sec. kernel-debuginfo-3.10.0-1160.41.1.el7.x86_64 CVE-2021-29154 Important/Sec. kernel-debuginfo-3.10.0-1160.41.1.el7.x86_64 CVE-2021-29650 Important/Sec. kernel-debuginfo-3.10.0-1160.41.1.el7.x86_64 CVE-2021-32399 Important/Sec. kernel-debuginfo-3.10.0-1160.41.1.el7.x86_64 CVE-2021-3715 Moderate/Sec. kernel-debuginfo-3.10.0-1160.42.2.el7.x86_64 CVE-2021-3653 Important/Sec. kernel-debuginfo-3.10.0-1160.45.1.el7.x86_64 CVE-2021-3656 Important/Sec. kernel-debuginfo-3.10.0-1160.45.1.el7.x86_64 CVE-2021-22543 Important/Sec. kernel-debuginfo-3.10.0-1160.45.1.el7.x86_64 CVE-2021-37576 Important/Sec. kernel-debuginfo-3.10.0-1160.45.1.el7.x86_64 CVE-2020-36385 Important/Sec. kernel-debuginfo-3.10.0-1160.49.1.el7.x86_64 CVE-2020-25704 Moderate/Sec. kernel-debuginfo-3.10.0-1160.53.1.el7.x86_64 CVE-2020-36322 Moderate/Sec. kernel-debuginfo-3.10.0-1160.53.1.el7.x86_64 CVE-2021-42739 Moderate/Sec. kernel-debuginfo-3.10.0-1160.53.1.el7.x86_64 CVE-2020-0465 Important/Sec. kernel-debuginfo-3.10.0-1160.59.1.el7.x86_64 CVE-2020-0466 Important/Sec. kernel-debuginfo-3.10.0-1160.59.1.el7.x86_64 CVE-2021-0920 Important/Sec. kernel-debuginfo-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3564 Important/Sec. kernel-debuginfo-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3573 Important/Sec. kernel-debuginfo-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3752 Important/Sec. kernel-debuginfo-3.10.0-1160.59.1.el7.x86_64 CVE-2021-4155 Important/Sec. kernel-debuginfo-3.10.0-1160.59.1.el7.x86_64 CVE-2022-0330 Important/Sec. kernel-debuginfo-3.10.0-1160.59.1.el7.x86_64 CVE-2022-22942 Important/Sec. kernel-debuginfo-3.10.0-1160.59.1.el7.x86_64 CVE-2021-4028 Important/Sec. kernel-debuginfo-3.10.0-1160.62.1.el7.x86_64 CVE-2021-4083 Important/Sec. kernel-debuginfo-3.10.0-1160.62.1.el7.x86_64 CVE-2022-0492 Important/Sec. kernel-debuginfo-3.10.0-1160.66.1.el7.x86_64 CVE-2020-8648 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.31.1.el7.x86_64 CVE-2020-12362 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.31.1.el7.x86_64 CVE-2020-12363 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.31.1.el7.x86_64 CVE-2020-12364 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.31.1.el7.x86_64 CVE-2020-27170 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.31.1.el7.x86_64 CVE-2021-3347 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.31.1.el7.x86_64 CVE-2019-20934 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.36.2.el7.x86_64 CVE-2020-11668 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33033 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33034 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33909 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.36.2.el7.x86_64 CVE-2020-27777 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.41.1.el7.x86_64 CVE-2021-22555 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.41.1.el7.x86_64 CVE-2021-29154 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.41.1.el7.x86_64 CVE-2021-29650 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.41.1.el7.x86_64 CVE-2021-32399 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.41.1.el7.x86_64 CVE-2021-3715 Moderate/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.42.2.el7.x86_64 CVE-2021-3653 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.45.1.el7.x86_64 CVE-2021-3656 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.45.1.el7.x86_64 CVE-2021-22543 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.45.1.el7.x86_64 CVE-2021-37576 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.45.1.el7.x86_64 CVE-2020-36385 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.49.1.el7.x86_64 CVE-2020-25704 Moderate/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.53.1.el7.x86_64 CVE-2020-36322 Moderate/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.53.1.el7.x86_64 CVE-2021-42739 Moderate/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.53.1.el7.x86_64 CVE-2020-0465 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.59.1.el7.x86_64 CVE-2020-0466 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.59.1.el7.x86_64 CVE-2021-0920 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3564 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3573 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3752 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.59.1.el7.x86_64 CVE-2021-4155 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.59.1.el7.x86_64 CVE-2022-0330 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.59.1.el7.x86_64 CVE-2022-22942 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.59.1.el7.x86_64 CVE-2021-4028 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.62.1.el7.x86_64 CVE-2021-4083 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.62.1.el7.x86_64 CVE-2022-0492 Important/Sec. kernel-debuginfo-common-x86_64-3.10.0-1160.66.1.el7.x86_64 CVE-2022-0492 Important/Sec. kernel-devel-3.10.0-1160.66.1.el7.x86_64 CVE-2022-0492 Important/Sec. kernel-headers-3.10.0-1160.66.1.el7.x86_64 CVE-2022-0492 Important/Sec. kernel-tools-3.10.0-1160.66.1.el7.x86_64 CVE-2022-0492 Important/Sec. kernel-tools-libs-3.10.0-1160.66.1.el7.x86_64 CVE-2022-0492 Important/Sec. perf-3.10.0-1160.66.1.el7.x86_64 CVE-2022-0492 Important/Sec. python-perf-3.10.0-1160.66.1.el7.x86_64 CVE-2018-25032 Important/Sec. zlib-1.2.7-20.el7_9.x86_64 CVE-2018-25032 Important/Sec. zlib-devel-1.2.7-20.el7_9.x86_64
```

## 7.9.22.04.SP12

The security patch released in May 2022.

The 7.9.22.04.SP12 patch is based on RHEL 7.9, and it can only be installed on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x.

Note: If after applying the security patch 7.9.22.04.SP12 or greater, you try to upgrade to 1.0.7.8, the upgrade might fail with the following error:

```plaintext
1. NodeosUpgrader.install Upgrade Detail: Component install for nodeos Caller Info:The call was made from 'NodeOSYosemiteInstaller.install' on line 100 with file located at '/localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/bundle_upgraders/../nodeos/node_os_yosemite_installer.py' Message: nodeos:NodeosUpgrader.install:Fatal Problem: Failed to install any new Node OS rpms...
```

Workaround:

1.  Run the following two commands from e1n1. Replace the `<your-1.0.7.8-upgrade-dir>` directory name in the commands with the actual upgrade directory name that you used on your system.
    1.  ```plaintext
        sed -i -e "0,/self._get_yum_repos_options() + ' ' + self.install_y/s/self._get_yum_repos_options() + ' ' + self.install_y/self._get_yum_repos_options() + ' ' + '--exclude=\"kernel*\"' + ' ' + self.install_y/" /localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/nodeos/node_os_installer.py
        ```
        
    2.  ```plaintext
        sed -i -e 's,self.verify_bundle,#self.verify_bundle,g' /opt/ibm/appliance/apupgrade/bin/apupgrade
        ```
        
2.  Rerun the same `apupgrade` command that failed:
    
    ```plaintext
    apupgrade --upgrade --upgrade-directory /localrepo --bundle system --use-version <your-1.0.7.8-upgrade-dir>
    ```
    

The list of Red Hat CVEs patched in this release:

```plaintext
CVE-2021-45960 Important/Sec. expat-2.1.0-14.el7_9.x86_64 CVE-2021-46143 Important/Sec. expat-2.1.0-14.el7_9.x86_64 CVE-2022-22822 Important/Sec. expat-2.1.0-14.el7_9.x86_64 CVE-2022-22823 Important/Sec. expat-2.1.0-14.el7_9.x86_64 CVE-2022-22824 Important/Sec. expat-2.1.0-14.el7_9.x86_64 CVE-2022-22825 Important/Sec. expat-2.1.0-14.el7_9.x86_64 CVE-2022-22826 Important/Sec. expat-2.1.0-14.el7_9.x86_64 CVE-2022-22827 Important/Sec. expat-2.1.0-14.el7_9.x86_64 CVE-2022-23852 Important/Sec. expat-2.1.0-14.el7_9.x86_64 CVE-2022-25235 Important/Sec. expat-2.1.0-14.el7_9.x86_64 CVE-2022-25236 Important/Sec. expat-2.1.0-14.el7_9.x86_64 CVE-2022-25315 Important/Sec. expat-2.1.0-14.el7_9.x86_64 CVE-2022-22720 Important/Sec. httpd-2.4.6-97.el7_9.5.x86_64 CVE-2022-22720 Important/Sec. httpd-tools-2.4.6-97.el7_9.5.x86_64 CVE-2020-5208 Important/Sec. ipmitool-1.8.18-9.el7_7.x86_64 CVE-2021-4028 Important/Sec. kernel-3.10.0-1160.62.1.el7.x86_64 CVE-2021-4083 Important/Sec. kernel-3.10.0-1160.62.1.el7.x86_64 CVE-2021-4028 Important/Sec. kernel-devel-3.10.0-1160.62.1.el7.x86_64 CVE-2021-4083 Important/Sec. kernel-devel-3.10.0-1160.62.1.el7.x86_64 CVE-2021-4028 Important/Sec. kernel-headers-3.10.0-1160.62.1.el7.x86_64 CVE-2021-4083 Important/Sec. kernel-headers-3.10.0-1160.62.1.el7.x86_64 CVE-2021-4028 Important/Sec. kernel-tools-3.10.0-1160.62.1.el7.x86_64 CVE-2021-4083 Important/Sec. kernel-tools-3.10.0-1160.62.1.el7.x86_64 CVE-2021-4028 Important/Sec. kernel-tools-libs-3.10.0-1160.62.1.el7.x86_64 CVE-2021-4083 Important/Sec. kernel-tools-libs-3.10.0-1160.62.1.el7.x86_64 CVE-2022-22720 Important/Sec. mod_session-2.4.6-97.el7_9.5.x86_64 CVE-2022-0778 Important/Sec. openssl-1:1.0.2k-25.el7_9.x86_64 CVE-2022-0778 Important/Sec. openssl-devel-1:1.0.2k-25.el7_9.x86_64 CVE-2022-0778 Important/Sec. openssl-libs-1:1.0.2k-25.el7_9.x86_64 CVE-2021-4028 Important/Sec. perf-3.10.0-1160.62.1.el7.x86_64 CVE-2021-4083 Important/Sec. perf-3.10.0-1160.62.1.el7.x86_64 CVE-2021-4028 Important/Sec. python-perf-3.10.0-1160.62.1.el7.x86_64 CVE-2021-4083 Important/Sec. python-perf-3.10.0-1160.62.1.el7.x86_64
```

## 7.9.22.03.SP11

The security patch released in April 2022.

The 7.9.22.03.SP11 patch is based on RHEL 7.9, and it can only be installed on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x.

Note: If after applying the security patch 7.9.22.03.SP11 or greater, you try to upgrade to 1.0.7.8, the upgrade might fail with the following error:

```plaintext
1. NodeosUpgrader.install Upgrade Detail: Component install for nodeos Caller Info:The call was made from 'NodeOSYosemiteInstaller.install' on line 100 with file located at '/localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/bundle_upgraders/../nodeos/node_os_yosemite_installer.py' Message: nodeos:NodeosUpgrader.install:Fatal Problem: Failed to install any new Node OS rpms...
```

Workaround:

1.  Run the following two commands from e1n1. Replace the `<your-1.0.7.8-upgrade-dir>` directory name in the commands with the actual upgrade directory name that you used on your system.
    1.  ```plaintext
        sed -i -e "0,/self._get_yum_repos_options() + ' ' + self.install_y/s/self._get_yum_repos_options() + ' ' + self.install_y/self._get_yum_repos_options() + ' ' + '--exclude=\"kernel*\"' + ' ' + self.install_y/" /localrepo/<your-1.0.7.8-upgrade-dir>/EXTRACT/system/upgrade/nodeos/node_os_installer.py
        ```
        
    2.  ```plaintext
        sed -i -e 's,self.verify_bundle,#self.verify_bundle,g' /opt/ibm/appliance/apupgrade/bin/apupgrade
        ```
        
2.  Rerun the same `apupgrade` command that failed:
    
    ```plaintext
    apupgrade --upgrade --upgrade-directory /localrepo --bundle system --use-version <your-1.0.7.8-upgrade-dir>
    ```
    

The list of Red Hat CVEs patched in this release:

```plaintext
CVE-2021-4091 Low/Sec. 389-ds-base-1.3.10.2-15.el7_9.x86_64 CVE-2021-4091 Low/Sec. 389-ds-base-libs-1.3.10.2-15.el7_9.x86_64 CVE-2022-24407 Important/Sec. cyrus-sasl-2.1.26-24.el7_9.x86_64 CVE-2022-24407 Important/Sec. cyrus-sasl-gssapi-2.1.26-24.el7_9.x86_64 CVE-2022-24407 Important/Sec. cyrus-sasl-lib-2.1.26-24.el7_9.x86_64 CVE-2022-24407 Important/Sec. cyrus-sasl-md5-2.1.26-24.el7_9.x86_64 CVE-2022-24407 Important/Sec. cyrus-sasl-plain-2.1.26-24.el7_9.x86_64 CVE-2020-5208 Important/Sec. ipmitool-1.8.18-9.el7_7.x86_64 CVE-2020-0465 Important/Sec. kernel-3.10.0-1160.59.1.el7.x86_64 CVE-2020-0466 Important/Sec. kernel-3.10.0-1160.59.1.el7.x86_64 CVE-2021-0920 Important/Sec. kernel-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3564 Important/Sec. kernel-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3573 Important/Sec. kernel-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3752 Important/Sec. kernel-3.10.0-1160.59.1.el7.x86_64 CVE-2021-4155 Important/Sec. kernel-3.10.0-1160.59.1.el7.x86_64 CVE-2022-0330 Important/Sec. kernel-3.10.0-1160.59.1.el7.x86_64 CVE-2022-22942 Important/Sec. kernel-3.10.0-1160.59.1.el7.x86_64 CVE-2020-0465 Important/Sec. kernel-devel-3.10.0-1160.59.1.el7.x86_64 CVE-2020-0466 Important/Sec. kernel-devel-3.10.0-1160.59.1.el7.x86_64 CVE-2021-0920 Important/Sec. kernel-devel-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3564 Important/Sec. kernel-devel-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3573 Important/Sec. kernel-devel-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3752 Important/Sec. kernel-devel-3.10.0-1160.59.1.el7.x86_64 CVE-2021-4155 Important/Sec. kernel-devel-3.10.0-1160.59.1.el7.x86_64 CVE-2022-0330 Important/Sec. kernel-devel-3.10.0-1160.59.1.el7.x86_64 CVE-2022-22942 Important/Sec. kernel-devel-3.10.0-1160.59.1.el7.x86_64 CVE-2020-0465 Important/Sec. kernel-headers-3.10.0-1160.59.1.el7.x86_64 CVE-2020-0466 Important/Sec. kernel-headers-3.10.0-1160.59.1.el7.x86_64 CVE-2021-0920 Important/Sec. kernel-headers-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3564 Important/Sec. kernel-headers-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3573 Important/Sec. kernel-headers-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3752 Important/Sec. kernel-headers-3.10.0-1160.59.1.el7.x86_64 CVE-2021-4155 Important/Sec. kernel-headers-3.10.0-1160.59.1.el7.x86_64 CVE-2022-0330 Important/Sec. kernel-headers-3.10.0-1160.59.1.el7.x86_64 CVE-2022-22942 Important/Sec. kernel-headers-3.10.0-1160.59.1.el7.x86_64 CVE-2020-0465 Important/Sec. kernel-tools-3.10.0-1160.59.1.el7.x86_64 CVE-2020-0466 Important/Sec. kernel-tools-3.10.0-1160.59.1.el7.x86_64 CVE-2021-0920 Important/Sec. kernel-tools-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3564 Important/Sec. kernel-tools-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3573 Important/Sec. kernel-tools-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3752 Important/Sec. kernel-tools-3.10.0-1160.59.1.el7.x86_64 CVE-2021-4155 Important/Sec. kernel-tools-3.10.0-1160.59.1.el7.x86_64 CVE-2022-0330 Important/Sec. kernel-tools-3.10.0-1160.59.1.el7.x86_64 CVE-2022-22942 Important/Sec. kernel-tools-3.10.0-1160.59.1.el7.x86_64 CVE-2020-0465 Important/Sec. kernel-tools-libs-3.10.0-1160.59.1.el7.x86_64 CVE-2020-0466 Important/Sec. kernel-tools-libs-3.10.0-1160.59.1.el7.x86_64 CVE-2021-0920 Important/Sec. kernel-tools-libs-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3564 Important/Sec. kernel-tools-libs-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3573 Important/Sec. kernel-tools-libs-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3752 Important/Sec. kernel-tools-libs-3.10.0-1160.59.1.el7.x86_64 CVE-2021-4155 Important/Sec. kernel-tools-libs-3.10.0-1160.59.1.el7.x86_64 CVE-2022-0330 Important/Sec. kernel-tools-libs-3.10.0-1160.59.1.el7.x86_64 CVE-2022-22942 Important/Sec. kernel-tools-libs-3.10.0-1160.59.1.el7.x86_64 CVE-2020-25709 Moderate/Sec. openldap-2.4.44-25.el7_9.x86_64 CVE-2020-25710 Moderate/Sec. openldap-2.4.44-25.el7_9.x86_64 CVE-2020-25709 Moderate/Sec. openldap-clients-2.4.44-25.el7_9.x86_64 CVE-2020-25710 Moderate/Sec. openldap-clients-2.4.44-25.el7_9.x86_64 CVE-2020-0465 Important/Sec. perf-3.10.0-1160.59.1.el7.x86_64 CVE-2020-0466 Important/Sec. perf-3.10.0-1160.59.1.el7.x86_64 CVE-2021-0920 Important/Sec. perf-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3564 Important/Sec. perf-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3573 Important/Sec. perf-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3752 Important/Sec. perf-3.10.0-1160.59.1.el7.x86_64 CVE-2021-4155 Important/Sec. perf-3.10.0-1160.59.1.el7.x86_64 CVE-2022-0330 Important/Sec. perf-3.10.0-1160.59.1.el7.x86_64 CVE-2022-22942 Important/Sec. perf-3.10.0-1160.59.1.el7.x86_64 CVE-2020-0465 Important/Sec. python-perf-3.10.0-1160.59.1.el7.x86_64 CVE-2020-0466 Important/Sec. python-perf-3.10.0-1160.59.1.el7.x86_64 CVE-2021-0920 Important/Sec. python-perf-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3564 Important/Sec. python-perf-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3573 Important/Sec. python-perf-3.10.0-1160.59.1.el7.x86_64 CVE-2021-3752 Important/Sec. python-perf-3.10.0-1160.59.1.el7.x86_64 CVE-2021-4155 Important/Sec. python-perf-3.10.0-1160.59.1.el7.x86_64 CVE-2022-0330 Important/Sec. python-perf-3.10.0-1160.59.1.el7.x86_64 CVE-2022-22942 Important/Sec. python-perf-3.10.0-1160.59.1.el7.x86_64 CVE-2022-22816 Important/Sec. python-pillow-2.0.0-23.gitd1c6db8.el7_9.x86_64 CVE-2022-22817 Important/Sec. python-pillow-2.0.0-23.gitd1c6db8.el7_9.x86_64
```

## 7.9.22.02.SP10

The security patch released in February 2022.

The 7.9.22.02.SP10 patch is based on RHEL 7.9, and it can only be installed on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x.

There is no need to install this patch on 1.0.7.8 as the same content is already applied with 1.0.7.8 upgrade.

The list of Red Hat CVEs patched in this release:

```plaintext
CVE-2021-45417 Important/Sec. aide-0.15.1-13.el7_9.1.x86_64 CVE-2020-5208 Important/Sec. ipmitool-1.8.18-9.el7_7.x86_64 CVE-2022-21248 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21282 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21283 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21293 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21294 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21296 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21299 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21305 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21340 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21341 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21360 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21365 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21248 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21282 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21283 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21293 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21294 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21296 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21299 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21305 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21340 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21341 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21360 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-21365 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.322.b06-1.el7_9.x86_64 CVE-2022-23302 Important/Sec. log4j-1.2.17-18.el7_4.noarch CVE-2022-23305 Important/Sec. log4j-1.2.17-18.el7_4.noarch CVE-2022-23307 Important/Sec. log4j-1.2.17-18.el7_4.noarch
```

## 7.9.22.01.SP9

The security patch released in February 2022.

The 7.9.22.01.SP9 patch is based on RHEL 7.9, and it can be installed only on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x.

The list of Red Hat CVEs patched in this release:

```plaintext
CVE-2020-25704 Moderate/Sec. kernel-3.10.0-1160.53.1.el7.x86_64 CVE-2020-36322 Moderate/Sec. kernel-3.10.0-1160.53.1.el7.x86_64 CVE-2021-42739 Moderate/Sec. kernel-3.10.0-1160.53.1.el7.x86_64 CVE-2020-25704 Moderate/Sec. kernel-devel-3.10.0-1160.53.1.el7.x86_64 CVE-2020-36322 Moderate/Sec. kernel-devel-3.10.0-1160.53.1.el7.x86_64 CVE-2021-42739 Moderate/Sec. kernel-devel-3.10.0-1160.53.1.el7.x86_64 CVE-2020-25704 Moderate/Sec. kernel-headers-3.10.0-1160.53.1.el7.x86_64 CVE-2020-36322 Moderate/Sec. kernel-headers-3.10.0-1160.53.1.el7.x86_64 CVE-2021-42739 Moderate/Sec. kernel-headers-3.10.0-1160.53.1.el7.x86_64 CVE-2020-25704 Moderate/Sec. kernel-tools-3.10.0-1160.53.1.el7.x86_64 CVE-2020-36322 Moderate/Sec. kernel-tools-3.10.0-1160.53.1.el7.x86_64 CVE-2021-42739 Moderate/Sec. kernel-tools-3.10.0-1160.53.1.el7.x86_64 CVE-2020-25704 Moderate/Sec. kernel-tools-libs-3.10.0-1160.53.1.el7.x86_64 CVE-2020-36322 Moderate/Sec. kernel-tools-libs-3.10.0-1160.53.1.el7.x86_64 CVE-2021-42739 Moderate/Sec. kernel-tools-libs-3.10.0-1160.53.1.el7.x86_64 CVE-2021-3712 Moderate/Sec. openssl-1:1.0.2k-23.el7_9.x86_64 CVE-2021-3712 Moderate/Sec. openssl-devel-1:1.0.2k-23.el7_9.x86_64 CVE-2021-3712 Moderate/Sec. openssl-libs-1:1.0.2k-23.el7_9.x86_64 CVE-2020-25704 Moderate/Sec. perf-3.10.0-1160.53.1.el7.x86_64 CVE-2020-36322 Moderate/Sec. perf-3.10.0-1160.53.1.el7.x86_64 CVE-2021-42739 Moderate/Sec. perf-3.10.0-1160.53.1.el7.x86_64 CVE-2020-25704 Moderate/Sec. python-perf-3.10.0-1160.53.1.el7.x86_64 CVE-2020-36322 Moderate/Sec. python-perf-3.10.0-1160.53.1.el7.x86_64 CVE-2021-42739 Moderate/Sec. python-perf-3.10.0-1160.53.1.el7.x86_64 CVE-2021-4034 Important/Sec. polkit-0.112-26.el7_9.1.x86_64 CVE-2021-44142 Critical/Sec. samba-client-libs-4.10.16-18.el7_9.x86_64 CVE-2021-44142 Critical/Sec. samba-common-tools-4.10.16-18.el7_9.x86_64 CVE-2021-44142 Critical/Sec. samba-python-4.10.16-18.el7_9.x86_64 CVE-2021-44142 Critical/Sec. samba-client-4.10.16-18.el7_9.x86_64 CVE-2021-44142 Critical/Sec. samba-common-libs-4.10.16-18.el7_9.x86_64 CVE-2021-44142 Critical/Sec. samba-winbind-modules-4.10.16-18.el7_9.x86_64 CVE-2021-44142 Critical/Sec. samba-libs-4.10.16-18.el7_9.x86_64 CVE-2021-44142 Critical/Sec. samba-winbind-4.10.16-18.el7_9.x86_64 CVE-2021-44142 Critical/Sec. samba-4.10.16-18.el7_9.x86_64 CVE-2021-44142 Critical/Sec. samba-common-4.10.16-18.el7_9.noarch CVE-2021-44142 Critical/Sec. libsmbclient-4.10.16-18.el7_9.x86_64.rpm CVE-2021-44142 Critical/Sec. libwbclient-4.10.16-18.el7_9.x86_64.rpm
```

## 7.9.21.12.SP8

The security patch released in January 2022.

The 7.9.21.12.SP8 patch is based on RHEL 7.9, and it can only be installed on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x.

The list of Red Hat CVEs patched in this release:

```plaintext
CVE-2020-5208 Important/Sec. ipmitool-1.8.18-9.el7_7.x86_64 CVE-2020-36385 Important/Sec. kernel-3.10.0-1160.49.1.el7.x86_64 CVE-2020-36385 Important/Sec. kernel-devel-3.10.0-1160.49.1.el7.x86_64 CVE-2020-36385 Important/Sec. kernel-headers-3.10.0-1160.49.1.el7.x86_64 CVE-2020-36385 Important/Sec. kernel-tools-3.10.0-1160.49.1.el7.x86_64 CVE-2020-36385 Important/Sec. kernel-tools-libs-3.10.0-1160.49.1.el7.x86_64 CVE-2021-37750 Moderate/Sec. krb5-devel-1.15.1-51.el7_9.x86_64 CVE-2021-37750 Moderate/Sec. krb5-libs-1.15.1-51.el7_9.x86_64 CVE-2021-37750 Moderate/Sec. krb5-pkinit-1.15.1-51.el7_9.x86_64 CVE-2021-37750 Moderate/Sec. krb5-server-1.15.1-51.el7_9.x86_64 CVE-2021-37750 Moderate/Sec. krb5-workstation-1.15.1-51.el7_9.x86_64 CVE-2021-37750 Moderate/Sec. libkadm5-1.15.1-51.el7_9.x86_64 CVE-2021-43527 Critical/Sec. nss-3.67.0-4.el7_9.x86_64 CVE-2021-43527 Critical/Sec. nss-sysinit-3.67.0-4.el7_9.x86_64 CVE-2021-43527 Critical/Sec. nss-tools-3.67.0-4.el7_9.x86_64 CVE-2021-41617 Moderate/Sec. openssh-7.4p1-22.el7_9.x86_64 CVE-2021-41617 Moderate/Sec. openssh-clients-7.4p1-22.el7_9.x86_64 CVE-2021-41617 Moderate/Sec. openssh-server-7.4p1-22.el7_9.x86_64 CVE-2020-36385 Important/Sec. perf-3.10.0-1160.49.1.el7.x86_64 CVE-2020-36385 Important/Sec. python-perf-3.10.0-1160.49.1.el7.x86_64 CVE-2021-20271 Moderate/Sec. rpm-4.11.3-48.el7_9.x86_64 CVE-2021-20271 Moderate/Sec. rpm-build-4.11.3-48.el7_9.x86_64 CVE-2021-20271 Moderate/Sec. rpm-build-libs-4.11.3-48.el7_9.x86_64 CVE-2021-20271 Moderate/Sec. rpm-devel-4.11.3-48.el7_9.x86_64 CVE-2021-20271 Moderate/Sec. rpm-libs-4.11.3-48.el7_9.x86_64 CVE-2021-20271 Moderate/Sec. rpm-python-4.11.3-48.el7_9.x86_64 CVE-2020-25719 Moderate/Sec. ipa-client-4.6.8-5.el7_9.10.x86_64 CVE-2020-25719 Moderate/Sec. ipa-client-common-4.6.8-5.el7_9.10.noarch CVE-2020-25719 Moderate/Sec. ipa-common-4.6.8-5.el7_9.10.noarch CVE-2020-25719 Moderate/Sec. ipa-python-compat-4.6.8-5.el7_9.10.noarch CVE-2020-25719 Moderate/Sec. ipa-server-4.6.8-5.el7_9.10.x86_64 CVE-2020-25719 Moderate/Sec. ipa-server-common-4.6.8-5.el7_9.10.noarch CVE-2020-25719 Moderate/Sec. ipa-server-dns-4.6.8-5.el7_9.10.noarch CVE-2020-25719 Moderate/Sec. ipa-server-trust-ad-4.6.8-5.el7_9.10.x86_64 CVE-2016-2124 Important/Sec. libsmbclient-4.10.16-17.el7_9.x86_64 CVE-2020-25717 Important/Sec. libsmbclient-4.10.16-17.el7_9.x86_64 CVE-2016-2124 Important/Sec. libwbclient-4.10.16-17.el7_9.x86_64 CVE-2020-25717 Important/Sec. libwbclient-4.10.16-17.el7_9.x86_64 CVE-2021-4104 Moderate/Sec. log4j-1.2.17-17.el7_4.noarch CVE-2020-25719 Moderate/Sec. python2-ipaclient-4.6.8-5.el7_9.10.noarch CVE-2020-25719 Moderate/Sec. python2-ipalib-4.6.8-5.el7_9.10.noarch CVE-2020-25719 Moderate/Sec. python2-ipaserver-4.6.8-5.el7_9.10.noarch CVE-2016-2124 Important/Sec. samba-4.10.16-17.el7_9.x86_64 CVE-2020-25717 Important/Sec. samba-4.10.16-17.el7_9.x86_64 CVE-2016-2124 Important/Sec. samba-client-4.10.16-17.el7_9.x86_64 CVE-2020-25717 Important/Sec. samba-client-4.10.16-17.el7_9.x86_64 CVE-2016-2124 Important/Sec. samba-client-libs-4.10.16-17.el7_9.x86_64 CVE-2020-25717 Important/Sec. samba-client-libs-4.10.16-17.el7_9.x86_64 CVE-2016-2124 Important/Sec. samba-common-4.10.16-17.el7_9.noarch CVE-2020-25717 Important/Sec. samba-common-4.10.16-17.el7_9.noarch CVE-2016-2124 Important/Sec. samba-common-libs-4.10.16-17.el7_9.x86_64 CVE-2020-25717 Important/Sec. samba-common-libs-4.10.16-17.el7_9.x86_64 CVE-2016-2124 Important/Sec. samba-common-tools-4.10.16-17.el7_9.x86_64 CVE-2020-25717 Important/Sec. samba-common-tools-4.10.16-17.el7_9.x86_64 CVE-2016-2124 Important/Sec. samba-libs-4.10.16-17.el7_9.x86_64 CVE-2020-25717 Important/Sec. samba-libs-4.10.16-17.el7_9.x86_64 CVE-2016-2124 Important/Sec. samba-python-4.10.16-17.el7_9.x86_64 CVE-2020-25717 Important/Sec. samba-python-4.10.16-17.el7_9.x86_64 CVE-2016-2124 Important/Sec. samba-winbind-4.10.16-17.el7_9.x86_64 CVE-2020-25717 Important/Sec. samba-winbind-4.10.16-17.el7_9.x86_64 CVE-2016-2124 Important/Sec. samba-winbind-modules-4.10.16-17.el7_9.x86_64 CVE-2020-25717 Important/Sec. samba-winbind-modules-4.10.16-17.el7_9.x86_64
```

## 7.9.21.11.SP7

Security patch released in December 2021.

The 7.9.21.11.SP7 patch is based on RHEL 7.9, and it can only be installed on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x.

The list of Red Hat CVEs patched in this release:

```plaintext
CVE-2021-3652 Low/Sec. 389-ds-base-1.3.10.2-13.el7_9.x86_64 CVE-2021-3652 Low/Sec. 389-ds-base-libs-1.3.10.2-13.el7_9.x86_64 CVE-2021-42574 Moderate/Sec. binutils-2.27-44.base.el7_9.1.x86_64 CVE-2021-40438 Important/Sec. httpd-2.4.6-97.el7_9.1.x86_64 CVE-2021-40438 Important/Sec. httpd-tools-2.4.6-97.el7_9.1.x86_64 CVE-2020-5208 Important/Sec. ipmitool-1.8.18-9.el7_7.x86_64 CVE-2021-35550 Important/Sec. java-1.8.0-openjdk-1:1.8.0.312.b07-1.el7_9.x86_64 CVE-2021-35556 Important/Sec. java-1.8.0-openjdk-1:1.8.0.312.b07-1.el7_9.x86_64 CVE-2021-35559 Important/Sec. java-1.8.0-openjdk-1:1.8.0.312.b07-1.el7_9.x86_64 CVE-2021-35561 Important/Sec. java-1.8.0-openjdk-1:1.8.0.312.b07-1.el7_9.x86_64 CVE-2021-35564 Important/Sec. java-1.8.0-openjdk-1:1.8.0.312.b07-1.el7_9.x86_64 CVE-2021-35565 Important/Sec. java-1.8.0-openjdk-1:1.8.0.312.b07-1.el7_9.x86_64 CVE-2021-35567 Important/Sec. java-1.8.0-openjdk-1:1.8.0.312.b07-1.el7_9.x86_64 CVE-2021-35578 Important/Sec. java-1.8.0-openjdk-1:1.8.0.312.b07-1.el7_9.x86_64 CVE-2021-35586 Important/Sec. java-1.8.0-openjdk-1:1.8.0.312.b07-1.el7_9.x86_64 CVE-2021-35588 Important/Sec. java-1.8.0-openjdk-1:1.8.0.312.b07-1.el7_9.x86_64 CVE-2021-35603 Important/Sec. java-1.8.0-openjdk-1:1.8.0.312.b07-1.el7_9.x86_64 CVE-2021-35550 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.312.b07-1.el7_9.x86_64 CVE-2021-35556 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.312.b07-1.el7_9.x86_64 CVE-2021-35559 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.312.b07-1.el7_9.x86_64 CVE-2021-35561 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.312.b07-1.el7_9.x86_64 CVE-2021-35564 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.312.b07-1.el7_9.x86_64 CVE-2021-35565 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.312.b07-1.el7_9.x86_64 CVE-2021-35567 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.312.b07-1.el7_9.x86_64 CVE-2021-35578 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.312.b07-1.el7_9.x86_64 CVE-2021-35586 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.312.b07-1.el7_9.x86_64 CVE-2021-35588 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.312.b07-1.el7_9.x86_64 CVE-2021-35603 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.312.b07-1.el7_9.x86_64 CVE-2021-3653 Important/Sec. kernel-3.10.0-1160.45.1.el7.x86_64 CVE-2021-3656 Important/Sec. kernel-3.10.0-1160.45.1.el7.x86_64 CVE-2021-22543 Important/Sec. kernel-3.10.0-1160.45.1.el7.x86_64 CVE-2021-37576 Important/Sec. kernel-3.10.0-1160.45.1.el7.x86_64 CVE-2021-3653 Important/Sec. kernel-devel-3.10.0-1160.45.1.el7.x86_64 CVE-2021-3656 Important/Sec. kernel-devel-3.10.0-1160.45.1.el7.x86_64 CVE-2021-22543 Important/Sec. kernel-devel-3.10.0-1160.45.1.el7.x86_64 CVE-2021-37576 Important/Sec. kernel-devel-3.10.0-1160.45.1.el7.x86_64 CVE-2021-3653 Important/Sec. kernel-headers-3.10.0-1160.45.1.el7.x86_64 CVE-2021-3656 Important/Sec. kernel-headers-3.10.0-1160.45.1.el7.x86_64 CVE-2021-22543 Important/Sec. kernel-headers-3.10.0-1160.45.1.el7.x86_64 CVE-2021-37576 Important/Sec. kernel-headers-3.10.0-1160.45.1.el7.x86_64 CVE-2021-3653 Important/Sec. kernel-tools-3.10.0-1160.45.1.el7.x86_64 CVE-2021-3656 Important/Sec. kernel-tools-3.10.0-1160.45.1.el7.x86_64 CVE-2021-22543 Important/Sec. kernel-tools-3.10.0-1160.45.1.el7.x86_64 CVE-2021-37576 Important/Sec. kernel-tools-3.10.0-1160.45.1.el7.x86_64 CVE-2021-3653 Important/Sec. kernel-tools-libs-3.10.0-1160.45.1.el7.x86_64 CVE-2021-3656 Important/Sec. kernel-tools-libs-3.10.0-1160.45.1.el7.x86_64 CVE-2021-22543 Important/Sec. kernel-tools-libs-3.10.0-1160.45.1.el7.x86_64 CVE-2021-37576 Important/Sec. kernel-tools-libs-3.10.0-1160.45.1.el7.x86_64 CVE-2016-4658 Moderate/Sec. libxml2-2.9.1-6.el7_9.6.x86_64 CVE-2016-4658 Moderate/Sec. libxml2-python-2.9.1-6.el7_9.6.x86_64 CVE-2021-40438 Important/Sec. mod_session-2.4.6-97.el7_9.1.x86_64 CVE-2021-23840 Moderate/Sec. openssl-1:1.0.2k-22.el7_9.x86_64 CVE-2021-23841 Moderate/Sec. openssl-1:1.0.2k-22.el7_9.x86_64 CVE-2021-23840 Moderate/Sec. openssl-devel-1:1.0.2k-22.el7_9.x86_64 CVE-2021-23841 Moderate/Sec. openssl-devel-1:1.0.2k-22.el7_9.x86_64 CVE-2021-23840 Moderate/Sec. openssl-libs-1:1.0.2k-22.el7_9.x86_64 CVE-2021-23841 Moderate/Sec. openssl-libs-1:1.0.2k-22.el7_9.x86_64 CVE-2021-3653 Important/Sec. perf-3.10.0-1160.45.1.el7.x86_64 CVE-2021-3656 Important/Sec. perf-3.10.0-1160.45.1.el7.x86_64 CVE-2021-22543 Important/Sec. perf-3.10.0-1160.45.1.el7.x86_64 CVE-2021-37576 Important/Sec. perf-3.10.0-1160.45.1.el7.x86_64 CVE-2021-3653 Important/Sec. python-perf-3.10.0-1160.45.1.el7.x86_64 CVE-2021-3656 Important/Sec. python-perf-3.10.0-1160.45.1.el7.x86_64 CVE-2021-22543 Important/Sec. python-perf-3.10.0-1160.45.1.el7.x86_64 CVE-2021-37576 Important/Sec. python-perf-3.10.0-1160.45.1.el7.x86_64
```

## 7.9.21.09.SP6

Security patch released in November 2021.

The 7.9.21.09.SP6 patch is based on RHEL 7.9, and it can only be installed on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x.

The list of Red Hat CVEs patched in this release:

```plaintext
CVE-2020-35518 Moderate/Sec. 389-ds-base-1.3.10.2-12.el7_9.x86_64 CVE-2020-35518 Moderate/Sec. 389-ds-base-libs-1.3.10.2-12.el7_9.x86_64 CVE-2021-25214 Moderate/Sec. bind-32:9.11.4-26.P2.el7_9.7.x86_64 CVE-2021-25214 Moderate/Sec. bind-export-libs-32:9.11.4-26.P2.el7_9.7.x86_64 CVE-2021-25214 Moderate/Sec. bind-libs-32:9.11.4-26.P2.el7_9.7.x86_64 CVE-2021-25214 Moderate/Sec. bind-libs-lite-32:9.11.4-26.P2.el7_9.7.x86_64 CVE-2021-25214 Moderate/Sec. bind-license-32:9.11.4-26.P2.el7_9.7.noarch CVE-2021-25214 Moderate/Sec. bind-pkcs11-32:9.11.4-26.P2.el7_9.7.x86_64 CVE-2021-25214 Moderate/Sec. bind-pkcs11-libs-32:9.11.4-26.P2.el7_9.7.x86_64 CVE-2021-25214 Moderate/Sec. bind-pkcs11-utils-32:9.11.4-26.P2.el7_9.7.x86_64 CVE-2021-25214 Moderate/Sec. bind-utils-32:9.11.4-26.P2.el7_9.7.x86_64 CVE-2021-3622 Low/Sec. hivex-1.3.10-6.12.el7_9.x86_64 CVE-2020-27777 Important/Sec. kernel-3.10.0-1160.41.1.el7.x86_64 CVE-2021-22555 Important/Sec. kernel-3.10.0-1160.41.1.el7.x86_64 CVE-2021-29154 Important/Sec. kernel-3.10.0-1160.41.1.el7.x86_64 CVE-2021-29650 Important/Sec. kernel-3.10.0-1160.41.1.el7.x86_64 CVE-2021-32399 Important/Sec. kernel-3.10.0-1160.41.1.el7.x86_64 CVE-2021-3715 Moderate/Sec. kernel-3.10.0-1160.42.2.el7.x86_64 CVE-2020-27777 Important/Sec. kernel-devel-3.10.0-1160.41.1.el7.x86_64 CVE-2021-22555 Important/Sec. kernel-devel-3.10.0-1160.41.1.el7.x86_64 CVE-2021-29154 Important/Sec. kernel-devel-3.10.0-1160.41.1.el7.x86_64 CVE-2021-29650 Important/Sec. kernel-devel-3.10.0-1160.41.1.el7.x86_64 CVE-2021-32399 Important/Sec. kernel-devel-3.10.0-1160.41.1.el7.x86_64 CVE-2021-3715 Moderate/Sec. kernel-devel-3.10.0-1160.42.2.el7.x86_64 CVE-2020-27777 Important/Sec. kernel-headers-3.10.0-1160.41.1.el7.x86_64 CVE-2021-22555 Important/Sec. kernel-headers-3.10.0-1160.41.1.el7.x86_64 CVE-2021-29154 Important/Sec. kernel-headers-3.10.0-1160.41.1.el7.x86_64 CVE-2021-29650 Important/Sec. kernel-headers-3.10.0-1160.41.1.el7.x86_64 CVE-2021-32399 Important/Sec. kernel-headers-3.10.0-1160.41.1.el7.x86_64 CVE-2021-3715 Moderate/Sec. kernel-headers-3.10.0-1160.42.2.el7.x86_64 CVE-2020-27777 Important/Sec. kernel-tools-3.10.0-1160.41.1.el7.x86_64 CVE-2021-22555 Important/Sec. kernel-tools-3.10.0-1160.41.1.el7.x86_64 CVE-2021-29154 Important/Sec. kernel-tools-3.10.0-1160.41.1.el7.x86_64 CVE-2021-29650 Important/Sec. kernel-tools-3.10.0-1160.41.1.el7.x86_64 CVE-2021-32399 Important/Sec. kernel-tools-3.10.0-1160.41.1.el7.x86_64 CVE-2021-3715 Moderate/Sec. kernel-tools-3.10.0-1160.42.2.el7.x86_64 CVE-2020-27777 Important/Sec. kernel-tools-libs-3.10.0-1160.41.1.el7.x86_64 CVE-2021-22555 Important/Sec. kernel-tools-libs-3.10.0-1160.41.1.el7.x86_64 CVE-2021-29154 Important/Sec. kernel-tools-libs-3.10.0-1160.41.1.el7.x86_64 CVE-2021-29650 Important/Sec. kernel-tools-libs-3.10.0-1160.41.1.el7.x86_64 CVE-2021-32399 Important/Sec. kernel-tools-libs-3.10.0-1160.41.1.el7.x86_64 CVE-2021-3715 Moderate/Sec. kernel-tools-libs-3.10.0-1160.42.2.el7.x86_64 CVE-2021-31535 Important/Sec. libX11-1.6.7-4.el7_9.x86_64 CVE-2021-31535 Important/Sec. libX11-common-1.6.7-4.el7_9.noarch CVE-2021-3621 Important/Sec. libipa_hbac-1.16.5-10.el7_9.10.x86_64 CVE-2021-3246 Important/Sec. libsndfile-1.0.25-12.el7_9.1.x86_64 CVE-2021-3621 Important/Sec. libsss_autofs-1.16.5-10.el7_9.10.x86_64 CVE-2021-3621 Important/Sec. libsss_certmap-1.16.5-10.el7_9.10.x86_64 CVE-2021-3621 Important/Sec. libsss_idmap-1.16.5-10.el7_9.10.x86_64 CVE-2021-3621 Important/Sec. libsss_nss_idmap-1.16.5-10.el7_9.10.x86_64 CVE-2021-3621 Important/Sec. libsss_simpleifp-1.16.5-10.el7_9.10.x86_64 CVE-2021-3621 Important/Sec. libsss_sudo-1.16.5-10.el7_9.10.x86_64 CVE-2020-27777 Important/Sec. perf-3.10.0-1160.41.1.el7.x86_64 CVE-2021-22555 Important/Sec. perf-3.10.0-1160.41.1.el7.x86_64 CVE-2021-29154 Important/Sec. perf-3.10.0-1160.41.1.el7.x86_64 CVE-2021-29650 Important/Sec. perf-3.10.0-1160.41.1.el7.x86_64 CVE-2021-32399 Important/Sec. perf-3.10.0-1160.41.1.el7.x86_64 CVE-2021-3715 Moderate/Sec. perf-3.10.0-1160.42.2.el7.x86_64 CVE-2021-3622 Low/Sec. perl-hivex-1.3.10-6.12.el7_9.x86_64 CVE-2021-3621 Important/Sec. python-libipa_hbac-1.16.5-10.el7_9.10.x86_64 CVE-2021-3621 Important/Sec. python-libsss_nss_idmap-1.16.5-10.el7_9.10.x86_64 CVE-2020-27777 Important/Sec. python-perf-3.10.0-1160.41.1.el7.x86_64 CVE-2021-22555 Important/Sec. python-perf-3.10.0-1160.41.1.el7.x86_64 CVE-2021-29154 Important/Sec. python-perf-3.10.0-1160.41.1.el7.x86_64 CVE-2021-29650 Important/Sec. python-perf-3.10.0-1160.41.1.el7.x86_64 CVE-2021-32399 Important/Sec. python-perf-3.10.0-1160.41.1.el7.x86_64 CVE-2021-3715 Moderate/Sec. python-perf-3.10.0-1160.42.2.el7.x86_64 CVE-2021-3621 Important/Sec. python-sss-1.16.5-10.el7_9.10.x86_64 CVE-2021-3621 Important/Sec. python-sss-murmur-1.16.5-10.el7_9.10.x86_64 CVE-2021-3621 Important/Sec. python-sssdconfig-1.16.5-10.el7_9.10.noarch CVE-2021-3621 Important/Sec. sssd-1.16.5-10.el7_9.10.x86_64 CVE-2021-3621 Important/Sec. sssd-ad-1.16.5-10.el7_9.10.x86_64 CVE-2021-3621 Important/Sec. sssd-client-1.16.5-10.el7_9.10.x86_64 CVE-2021-3621 Important/Sec. sssd-common-1.16.5-10.el7_9.10.x86_64 CVE-2021-3621 Important/Sec. sssd-common-pac-1.16.5-10.el7_9.10.x86_64 CVE-2021-3621 Important/Sec. sssd-dbus-1.16.5-10.el7_9.10.x86_64 CVE-2021-3621 Important/Sec. sssd-ipa-1.16.5-10.el7_9.10.x86_64 CVE-2021-3621 Important/Sec. sssd-krb5-1.16.5-10.el7_9.10.x86_64 CVE-2021-3621 Important/Sec. sssd-krb5-common-1.16.5-10.el7_9.10.x86_64 CVE-2021-3621 Important/Sec. sssd-ldap-1.16.5-10.el7_9.10.x86_64 CVE-2021-3621 Important/Sec. sssd-proxy-1.16.5-10.el7_9.10.x86_64 CVE-2021-3621 Important/Sec. sssd-tools-1.16.5-10.el7_9.10.x86_64
```

## 7.9.21.08.SP5

Security patch released in September 2021.

The 7.9.21.08.SP5 patch is based on RHEL 7.9, and it can only be installed on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x.

The list of Red Hat CVEs patched in this release:

```plaintext
CVE-2021-2341 Important/Sec. java-1.8.0-openjdk-1:1.8.0.302.b08-0.el7_9.x86_64 CVE-2021-2369 Important/Sec. java-1.8.0-openjdk-1:1.8.0.302.b08-0.el7_9.x86_64 CVE-2021-2388 Important/Sec. java-1.8.0-openjdk-1:1.8.0.302.b08-0.el7_9.x86_64 CVE-2021-2341 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.302.b08-0.el7_9.x86_64 CVE-2021-2369 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.302.b08-0.el7_9.x86_64 CVE-2021-2388 Important/Sec. java-1.8.0-openjdk-headless-1:1.8.0.302.b08-0.el7_9.x86_64 CVE-2019-20934 Important/Sec. kernel-3.10.0-1160.36.2.el7.x86_64 CVE-2020-11668 Important/Sec. kernel-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33033 Important/Sec. kernel-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33034 Important/Sec. kernel-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33909 Important/Sec. kernel-3.10.0-1160.36.2.el7.x86_64 CVE-2019-20934 Important/Sec. kernel-devel-3.10.0-1160.36.2.el7.x86_64 CVE-2020-11668 Important/Sec. kernel-devel-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33033 Important/Sec. kernel-devel-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33034 Important/Sec. kernel-devel-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33909 Important/Sec. kernel-devel-3.10.0-1160.36.2.el7.x86_64 CVE-2019-20934 Important/Sec. kernel-headers-3.10.0-1160.36.2.el7.x86_64 CVE-2020-11668 Important/Sec. kernel-headers-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33033 Important/Sec. kernel-headers-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33034 Important/Sec. kernel-headers-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33909 Important/Sec. kernel-headers-3.10.0-1160.36.2.el7.x86_64 CVE-2019-20934 Important/Sec. kernel-tools-3.10.0-1160.36.2.el7.x86_64 CVE-2020-11668 Important/Sec. kernel-tools-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33033 Important/Sec. kernel-tools-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33034 Important/Sec. kernel-tools-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33909 Important/Sec. kernel-tools-3.10.0-1160.36.2.el7.x86_64 CVE-2019-20934 Important/Sec. kernel-tools-libs-3.10.0-1160.36.2.el7.x86_64 CVE-2020-11668 Important/Sec. kernel-tools-libs-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33033 Important/Sec. kernel-tools-libs-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33034 Important/Sec. kernel-tools-libs-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33909 Important/Sec. kernel-tools-libs-3.10.0-1160.36.2.el7.x86_64 CVE-2019-20934 Important/Sec. perf-3.10.0-1160.36.2.el7.x86_64 CVE-2020-11668 Important/Sec. perf-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33033 Important/Sec. perf-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33034 Important/Sec. perf-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33909 Important/Sec. perf-3.10.0-1160.36.2.el7.x86_64 CVE-2019-20934 Important/Sec. python-perf-3.10.0-1160.36.2.el7.x86_64 CVE-2020-11668 Important/Sec. python-perf-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33033 Important/Sec. python-perf-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33034 Important/Sec. python-perf-3.10.0-1160.36.2.el7.x86_64 CVE-2021-33909 Important/Sec. python-perf-3.10.0-1160.36.2.el7.x86_64
```

## **7.9.21.05.SP3**

Security patch released in July 2021.

The 7.9.21.05.SP3 patch is based on RHEL 7.9, and it can only be installed on Cloud Pak for Data System version 1.0.7.6 and later 1.0.7.x.

The list of Red Hat CVEs patched in this release:

```plaintext
CVE-2021-25215 Important/Sec. bind-32:9.11.4-26.P2.el7_9.5.x86_64 CVE-2021-25215 Important/Sec. bind-export-libs-32:9.11.4-26.P2.el7_9.5.x86_64 CVE-2021-25215 Important/Sec. bind-libs-32:9.11.4-26.P2.el7_9.5.x86_64 CVE-2021-25215 Important/Sec. bind-libs-lite-32:9.11.4-26.P2.el7_9.5.x86_64 CVE-2021-25215 Important/Sec. bind-license-32:9.11.4-26.P2.el7_9.5.noarch CVE-2021-25215 Important/Sec. bind-pkcs11-32:9.11.4-26.P2.el7_9.5.x86_64 CVE-2021-25215 Important/Sec. bind-pkcs11-libs-32:9.11.4-26.P2.el7_9.5.x86_64 CVE-2021-25215 Important/Sec. bind-pkcs11-utils-32:9.11.4-26.P2.el7_9.5.x86_64 CVE-2021-25215 Important/Sec. bind-utils-32:9.11.4-26.P2.el7_9.5.x86_64 CVE-2021-2163 Moderate/Sec. java-1.8.0-openjdk-1:1.8.0.292.b10-1.el7_9.x86_64 CVE-2021-2163 Moderate/Sec. java-1.8.0-openjdk-headless-1:1.8.0.292.b10-1.el7_9.x86_64 CVE-2020-25648 Moderate/Sec. nss-3.53.1-7.el7_9.x86_64 CVE-2020-25648 Moderate/Sec. nss-sysinit-3.53.1-7.el7_9.x86_64 CVE-2020-25648 Moderate/Sec. nss-tools-3.53.1-7.el7_9.x86_64 CVE-2020-25692 Moderate/Sec. openldap-2.4.44-23.el7_9.x86_64 CVE-2020-25692 Moderate/Sec. openldap-clients-2.4.44-23.el7_9.x86_64 CVE-2021-3480 Important/Sec. slapi-nis-0.56.5-4.el7_9.x86_64
```

## 7.9.21.04.SP1

The security patch released in April 2021.

The 7.9.21.04.SP1 patch is based on RHEL 7.9, and it can only be installed on Cloud Pak for Data System version 1.0.7.6.

The list of Red Hat CVEs patched in this release:

```plaintext
CVE-2020-8625 Important/Sec. bind-32:9.11.4-26.P2.el7_9.4.x86_64 CVE-2020-8625 Important/Sec. bind-export-libs-32:9.11.4-26.P2.el7_9.4.x86_64 CVE-2020-8625 Important/Sec. bind-libs-32:9.11.4-26.P2.el7_9.4.x86_64 CVE-2020-8625 Important/Sec. bind-libs-lite-32:9.11.4-26.P2.el7_9.4.x86_64 CVE-2020-8625 Important/Sec. bind-license-32:9.11.4-26.P2.el7_9.4.noarch CVE-2020-8625 Important/Sec. bind-pkcs11-32:9.11.4-26.P2.el7_9.4.x86_64 CVE-2020-8625 Important/Sec. bind-pkcs11-libs-32:9.11.4-26.P2.el7_9.4.x86_64 CVE-2020-8625 Important/Sec. bind-pkcs11-utils-32:9.11.4-26.P2.el7_9.4.x86_64 CVE-2020-8625 Important/Sec. bind-utils-32:9.11.4-26.P2.el7_9.4.x86_64 CVE-2019-14866 Moderate/Sec. cpio-2.11-28.el7.x86_64 CVE-2017-18190 Moderate/Sec. cups-1:1.6.3-51.el7.x86_64 CVE-2019-8675 Moderate/Sec. cups-1:1.6.3-51.el7.x86_64 CVE-2019-8696 Moderate/Sec. cups-1:1.6.3-51.el7.x86_64 CVE-2017-18190 Moderate/Sec. cups-client-1:1.6.3-51.el7.x86_64 CVE-2019-8675 Moderate/Sec. cups-client-1:1.6.3-51.el7.x86_64 CVE-2019-8696 Moderate/Sec. cups-client-1:1.6.3-51.el7.x86_64 CVE-2017-18190 Moderate/Sec. cups-filesystem-1:1.6.3-51.el7.noarch CVE-2019-8675 Moderate/Sec. cups-filesystem-1:1.6.3-51.el7.noarch CVE-2019-8696 Moderate/Sec. cups-filesystem-1:1.6.3-51.el7.noarch CVE-2017-18190 Moderate/Sec. cups-libs-1:1.6.3-51.el7.x86_64 CVE-2019-8675 Moderate/Sec. cups-libs-1:1.6.3-51.el7.x86_64 CVE-2019-8696 Moderate/Sec. cups-libs-1:1.6.3-51.el7.x86_64 CVE-2019-12749 Moderate/Sec. dbus-1:1.10.24-15.el7.x86_64 CVE-2019-12749 Moderate/Sec. dbus-libs-1:1.10.24-15.el7.x86_64 CVE-2019-14834 Low/Sec. dnsmasq-2.76-16.el7.x86_64 CVE-2020-25684 Moderate/Sec. dnsmasq-2.76-16.el7_9.1.x86_64 CVE-2020-25685 Moderate/Sec. dnsmasq-2.76-16.el7_9.1.x86_64 CVE-2020-25686 Moderate/Sec. dnsmasq-2.76-16.el7_9.1.x86_64 CVE-2019-5094 Moderate/Sec. e2fsprogs-1.42.9-19.el7.x86_64 CVE-2019-5188 Moderate/Sec. e2fsprogs-1.42.9-19.el7.x86_64 CVE-2019-5094 Moderate/Sec. e2fsprogs-libs-1.42.9-19.el7.x86_64 CVE-2019-5188 Moderate/Sec. e2fsprogs-libs-1.42.9-19.el7.x86_64 CVE-2018-20843 Moderate/Sec. expat-2.1.0-12.el7.x86_64 CVE-2019-15903 Moderate/Sec. expat-2.1.0-12.el7.x86_64 CVE-2020-15999 Important/Sec. freetype-2.8-14.el7_9.1.x86_64 CVE-2019-19126 Low/Sec. glibc-2.17-317.el7.x86_64 CVE-2019-25013 Moderate/Sec. glibc-2.17-322.el7_9.x86_64 CVE-2020-10029 Moderate/Sec. glibc-2.17-322.el7_9.x86_64 CVE-2020-29573 Moderate/Sec. glibc-2.17-322.el7_9.x86_64 CVE-2019-19126 Low/Sec. glibc-common-2.17-317.el7.x86_64 CVE-2019-25013 Moderate/Sec. glibc-common-2.17-322.el7_9.x86_64 CVE-2020-10029 Moderate/Sec. glibc-common-2.17-322.el7_9.x86_64 CVE-2020-29573 Moderate/Sec. glibc-common-2.17-322.el7_9.x86_64 CVE-2019-19126 Low/Sec. glibc-devel-2.17-317.el7.x86_64 CVE-2019-25013 Moderate/Sec. glibc-devel-2.17-322.el7_9.x86_64 CVE-2020-10029 Moderate/Sec. glibc-devel-2.17-322.el7_9.x86_64 CVE-2020-29573 Moderate/Sec. glibc-devel-2.17-322.el7_9.x86_64 CVE-2019-19126 Low/Sec. glibc-headers-2.17-317.el7.x86_64 CVE-2019-25013 Moderate/Sec. glibc-headers-2.17-322.el7_9.x86_64 CVE-2020-10029 Moderate/Sec. glibc-headers-2.17-322.el7_9.x86_64 CVE-2020-29573 Moderate/Sec. glibc-headers-2.17-322.el7_9.x86_64 CVE-2020-14372 Moderate/Sec. grub2-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-25632 Moderate/Sec. grub2-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-25647 Moderate/Sec. grub2-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-27749 Moderate/Sec. grub2-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-27779 Moderate/Sec. grub2-1:2.02-0.87.el7_9.2.x86_64 CVE-2021-20225 Moderate/Sec. grub2-1:2.02-0.87.el7_9.2.x86_64 CVE-2021-20233 Moderate/Sec. grub2-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-14372 Moderate/Sec. grub2-common-1:2.02-0.87.el7_9.2.noarch CVE-2020-25632 Moderate/Sec. grub2-common-1:2.02-0.87.el7_9.2.noarch CVE-2020-25647 Moderate/Sec. grub2-common-1:2.02-0.87.el7_9.2.noarch CVE-2020-27749 Moderate/Sec. grub2-common-1:2.02-0.87.el7_9.2.noarch CVE-2020-27779 Moderate/Sec. grub2-common-1:2.02-0.87.el7_9.2.noarch CVE-2021-20225 Moderate/Sec. grub2-common-1:2.02-0.87.el7_9.2.noarch CVE-2021-20233 Moderate/Sec. grub2-common-1:2.02-0.87.el7_9.2.noarch CVE-2020-14372 Moderate/Sec. grub2-pc-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-25632 Moderate/Sec. grub2-pc-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-25647 Moderate/Sec. grub2-pc-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-27749 Moderate/Sec. grub2-pc-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-27779 Moderate/Sec. grub2-pc-1:2.02-0.87.el7_9.2.x86_64 CVE-2021-20225 Moderate/Sec. grub2-pc-1:2.02-0.87.el7_9.2.x86_64 CVE-2021-20233 Moderate/Sec. grub2-pc-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-14372 Moderate/Sec. grub2-pc-modules-1:2.02-0.87.el7_9.2.noarch CVE-2020-25632 Moderate/Sec. grub2-pc-modules-1:2.02-0.87.el7_9.2.noarch CVE-2020-25647 Moderate/Sec. grub2-pc-modules-1:2.02-0.87.el7_9.2.noarch CVE-2020-27749 Moderate/Sec. grub2-pc-modules-1:2.02-0.87.el7_9.2.noarch CVE-2020-27779 Moderate/Sec. grub2-pc-modules-1:2.02-0.87.el7_9.2.noarch CVE-2021-20225 Moderate/Sec. grub2-pc-modules-1:2.02-0.87.el7_9.2.noarch CVE-2021-20233 Moderate/Sec. grub2-pc-modules-1:2.02-0.87.el7_9.2.noarch CVE-2020-14372 Moderate/Sec. grub2-tools-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-25632 Moderate/Sec. grub2-tools-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-25647 Moderate/Sec. grub2-tools-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-27749 Moderate/Sec. grub2-tools-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-27779 Moderate/Sec. grub2-tools-1:2.02-0.87.el7_9.2.x86_64 CVE-2021-20225 Moderate/Sec. grub2-tools-1:2.02-0.87.el7_9.2.x86_64 CVE-2021-20233 Moderate/Sec. grub2-tools-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-14372 Moderate/Sec. grub2-tools-extra-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-25632 Moderate/Sec. grub2-tools-extra-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-25647 Moderate/Sec. grub2-tools-extra-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-27749 Moderate/Sec. grub2-tools-extra-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-27779 Moderate/Sec. grub2-tools-extra-1:2.02-0.87.el7_9.2.x86_64 CVE-2021-20225 Moderate/Sec. grub2-tools-extra-1:2.02-0.87.el7_9.2.x86_64 CVE-2021-20233 Moderate/Sec. grub2-tools-extra-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-14372 Moderate/Sec. grub2-tools-minimal-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-25632 Moderate/Sec. grub2-tools-minimal-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-25647 Moderate/Sec. grub2-tools-minimal-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-27749 Moderate/Sec. grub2-tools-minimal-1:2.02-0.87.el7_9.2.x86_64 CVE-2020-27779 Moderate/Sec. grub2-tools-minimal-1:2.02-0.87.el7_9.2.x86_64 CVE-2021-20225 Moderate/Sec. grub2-tools-minimal-1:2.02-0.87.el7_9.2.x86_64 CVE-2021-20233 Moderate/Sec. grub2-tools-minimal-1:2.02-0.87.el7_9.2.x86_64 CVE-2019-16707 Low/Sec. hunspell-1.3.2-16.el7.x86_64 CVE-2015-9251 Moderate/Sec. ipa-client-4.6.8-5.el7.x86_64 CVE-2016-10735 Moderate/Sec. ipa-client-4.6.8-5.el7.x86_64 CVE-2018-14040 Moderate/Sec. ipa-client-4.6.8-5.el7.x86_64 CVE-2018-14042 Moderate/Sec. ipa-client-4.6.8-5.el7.x86_64 CVE-2018-20676 Moderate/Sec. ipa-client-4.6.8-5.el7.x86_64 CVE-2018-20677 Moderate/Sec. ipa-client-4.6.8-5.el7.x86_64 CVE-2019-8331 Moderate/Sec. ipa-client-4.6.8-5.el7.x86_64 CVE-2019-11358 Moderate/Sec. ipa-client-4.6.8-5.el7.x86_64 CVE-2020-1722 Moderate/Sec. ipa-client-4.6.8-5.el7.x86_64 CVE-2020-11022 Moderate/Sec. ipa-client-4.6.8-5.el7.x86_64 CVE-2020-11023 Moderate/Sec. ipa-client-4.6.8-5.el7_9.4.x86_64 CVE-2015-9251 Moderate/Sec. ipa-client-common-4.6.8-5.el7.noarch CVE-2016-10735 Moderate/Sec. ipa-client-common-4.6.8-5.el7.noarch CVE-2018-14040 Moderate/Sec. ipa-client-common-4.6.8-5.el7.noarch CVE-2018-14042 Moderate/Sec. ipa-client-common-4.6.8-5.el7.noarch CVE-2018-20676 Moderate/Sec. ipa-client-common-4.6.8-5.el7.noarch CVE-2018-20677 Moderate/Sec. ipa-client-common-4.6.8-5.el7.noarch CVE-2019-8331 Moderate/Sec. ipa-client-common-4.6.8-5.el7.noarch CVE-2019-11358 Moderate/Sec. ipa-client-common-4.6.8-5.el7.noarch CVE-2020-1722 Moderate/Sec. ipa-client-common-4.6.8-5.el7.noarch CVE-2020-11022 Moderate/Sec. ipa-client-common-4.6.8-5.el7.noarch CVE-2020-11023 Moderate/Sec. ipa-client-common-4.6.8-5.el7_9.4.noarch CVE-2015-9251 Moderate/Sec. ipa-common-4.6.8-5.el7.noarch CVE-2016-10735 Moderate/Sec. ipa-common-4.6.8-5.el7.noarch CVE-2018-14040 Moderate/Sec. ipa-common-4.6.8-5.el7.noarch CVE-2018-14042 Moderate/Sec. ipa-common-4.6.8-5.el7.noarch CVE-2018-20676 Moderate/Sec. ipa-common-4.6.8-5.el7.noarch CVE-2018-20677 Moderate/Sec. ipa-common-4.6.8-5.el7.noarch CVE-2019-8331 Moderate/Sec. ipa-common-4.6.8-5.el7.noarch CVE-2019-11358 Moderate/Sec. ipa-common-4.6.8-5.el7.noarch CVE-2020-1722 Moderate/Sec. ipa-common-4.6.8-5.el7.noarch CVE-2020-11022 Moderate/Sec. ipa-common-4.6.8-5.el7.noarch CVE-2020-11023 Moderate/Sec. ipa-common-4.6.8-5.el7_9.4.noarch CVE-2015-9251 Moderate/Sec. ipa-server-4.6.8-5.el7.x86_64 CVE-2016-10735 Moderate/Sec. ipa-server-4.6.8-5.el7.x86_64 CVE-2018-14040 Moderate/Sec. ipa-server-4.6.8-5.el7.x86_64 CVE-2018-14042 Moderate/Sec. ipa-server-4.6.8-5.el7.x86_64 CVE-2018-20676 Moderate/Sec. ipa-server-4.6.8-5.el7.x86_64 CVE-2018-20677 Moderate/Sec. ipa-server-4.6.8-5.el7.x86_64 CVE-2019-8331 Moderate/Sec. ipa-server-4.6.8-5.el7.x86_64 CVE-2019-11358 Moderate/Sec. ipa-server-4.6.8-5.el7.x86_64 CVE-2020-1722 Moderate/Sec. ipa-server-4.6.8-5.el7.x86_64 CVE-2020-11022 Moderate/Sec. ipa-server-4.6.8-5.el7.x86_64 CVE-2020-11023 Moderate/Sec. ipa-server-4.6.8-5.el7_9.4.x86_64 CVE-2015-9251 Moderate/Sec. ipa-server-common-4.6.8-5.el7.noarch CVE-2016-10735 Moderate/Sec. ipa-server-common-4.6.8-5.el7.noarch CVE-2018-14040 Moderate/Sec. ipa-server-common-4.6.8-5.el7.noarch CVE-2018-14042 Moderate/Sec. ipa-server-common-4.6.8-5.el7.noarch CVE-2018-20676 Moderate/Sec. ipa-server-common-4.6.8-5.el7.noarch CVE-2018-20677 Moderate/Sec. ipa-server-common-4.6.8-5.el7.noarch CVE-2019-8331 Moderate/Sec. ipa-server-common-4.6.8-5.el7.noarch CVE-2019-11358 Moderate/Sec. ipa-server-common-4.6.8-5.el7.noarch CVE-2020-1722 Moderate/Sec. ipa-server-common-4.6.8-5.el7.noarch CVE-2020-11022 Moderate/Sec. ipa-server-common-4.6.8-5.el7.noarch CVE-2020-11023 Moderate/Sec. ipa-server-common-4.6.8-5.el7_9.4.noarch CVE-2015-9251 Moderate/Sec. ipa-server-dns-4.6.8-5.el7.noarch CVE-2016-10735 Moderate/Sec. ipa-server-dns-4.6.8-5.el7.noarch CVE-2018-14040 Moderate/Sec. ipa-server-dns-4.6.8-5.el7.noarch CVE-2018-14042 Moderate/Sec. ipa-server-dns-4.6.8-5.el7.noarch CVE-2018-20676 Moderate/Sec. ipa-server-dns-4.6.8-5.el7.noarch CVE-2018-20677 Moderate/Sec. ipa-server-dns-4.6.8-5.el7.noarch CVE-2019-8331 Moderate/Sec. ipa-server-dns-4.6.8-5.el7.noarch CVE-2019-11358 Moderate/Sec. ipa-server-dns-4.6.8-5.el7.noarch CVE-2020-1722 Moderate/Sec. ipa-server-dns-4.6.8-5.el7.noarch CVE-2020-11022 Moderate/Sec. ipa-server-dns-4.6.8-5.el7.noarch CVE-2020-11023 Moderate/Sec. ipa-server-dns-4.6.8-5.el7_9.4.noarch CVE-2015-9251 Moderate/Sec. ipa-server-trust-ad-4.6.8-5.el7.x86_64 CVE-2016-10735 Moderate/Sec. ipa-server-trust-ad-4.6.8-5.el7.x86_64 CVE-2018-14040 Moderate/Sec. ipa-server-trust-ad-4.6.8-5.el7.x86_64 CVE-2018-14042 Moderate/Sec. ipa-server-trust-ad-4.6.8-5.el7.x86_64 CVE-2018-20676 Moderate/Sec. ipa-server-trust-ad-4.6.8-5.el7.x86_64 CVE-2018-20677 Moderate/Sec. ipa-server-trust-ad-4.6.8-5.el7.x86_64 CVE-2019-8331 Moderate/Sec. ipa-server-trust-ad-4.6.8-5.el7.x86_64 CVE-2019-11358 Moderate/Sec. ipa-server-trust-ad-4.6.8-5.el7.x86_64 CVE-2020-1722 Moderate/Sec. ipa-server-trust-ad-4.6.8-5.el7.x86_64 CVE-2020-11022 Moderate/Sec. ipa-server-trust-ad-4.6.8-5.el7.x86_64 CVE-2020-11023 Moderate/Sec. ipa-server-trust-ad-4.6.8-5.el7_9.4.x86_64 CVE-2020-5208 Important/Sec. ipmitool-1.8.18-9.el7_7.x86_64 CVE-2020-12321 Important/Sec. iwl100-firmware-39.31.5.1-80.el7_9.noarch CVE-2020-12321 Important/Sec. iwl1000-firmware-1:39.31.5.1-80.el7_9.noarch CVE-2020-12321 Important/Sec. iwl105-firmware-18.168.6.1-80.el7_9.noarch CVE-2020-12321 Important/Sec. iwl135-firmware-18.168.6.1-80.el7_9.noarch CVE-2020-12321 Important/Sec. iwl2000-firmware-18.168.6.1-80.el7_9.noarch CVE-2020-12321 Important/Sec. iwl2030-firmware-18.168.6.1-80.el7_9.noarch CVE-2020-12321 Important/Sec. iwl3160-firmware-25.30.13.0-80.el7_9.noarch CVE-2020-12321 Important/Sec. iwl3945-firmware-15.32.2.9-80.el7_9.noarch CVE-2020-12321 Important/Sec. iwl4965-firmware-228.61.2.24-80.el7_9.noarch CVE-2020-12321 Important/Sec. iwl5000-firmware-8.83.5.1_1-80.el7_9.noarch CVE-2020-12321 Important/Sec. iwl5150-firmware-8.24.2.2-80.el7_9.noarch CVE-2020-12321 Important/Sec. iwl6000-firmware-9.221.4.1-80.el7_9.noarch CVE-2020-12321 Important/Sec. iwl6000g2a-firmware-18.168.6.1-80.el7_9.noarch CVE-2020-12321 Important/Sec. iwl6000g2b-firmware-18.168.6.1-80.el7_9.noarch CVE-2020-12321 Important/Sec. iwl6050-firmware-41.28.5.1-80.el7_9.noarch CVE-2020-12321 Important/Sec. iwl7260-firmware-25.30.13.0-80.el7_9.noarch CVE-2020-15436 Moderate/Sec. kernel-3.10.0-1160.15.2.el7.x86_64 CVE-2020-35513 Moderate/Sec. kernel-3.10.0-1160.15.2.el7.x86_64 CVE-2019-19532 Important/Sec. kernel-3.10.0-1160.21.1.el7.x86_64 CVE-2020-0427 Important/Sec. kernel-3.10.0-1160.21.1.el7.x86_64 CVE-2020-7053 Important/Sec. kernel-3.10.0-1160.21.1.el7.x86_64 CVE-2020-14351 Important/Sec. kernel-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25211 Important/Sec. kernel-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25645 Important/Sec. kernel-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25656 Important/Sec. kernel-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25705 Important/Sec. kernel-3.10.0-1160.21.1.el7.x86_64 CVE-2020-28374 Important/Sec. kernel-3.10.0-1160.21.1.el7.x86_64 CVE-2020-29661 Important/Sec. kernel-3.10.0-1160.21.1.el7.x86_64 CVE-2021-20265 Important/Sec. kernel-3.10.0-1160.21.1.el7.x86_64 CVE-2021-27363 Important/Sec. kernel-3.10.0-1160.24.1.el7.x86_64 CVE-2021-27364 Important/Sec. kernel-3.10.0-1160.24.1.el7.x86_64 CVE-2021-27365 Important/Sec. kernel-3.10.0-1160.24.1.el7.x86_64 CVE-2020-15436 Moderate/Sec. kernel-devel-3.10.0-1160.15.2.el7.x86_64 CVE-2020-35513 Moderate/Sec. kernel-devel-3.10.0-1160.15.2.el7.x86_64 CVE-2019-19532 Important/Sec. kernel-devel-3.10.0-1160.21.1.el7.x86_64 CVE-2020-0427 Important/Sec. kernel-devel-3.10.0-1160.21.1.el7.x86_64 CVE-2020-7053 Important/Sec. kernel-devel-3.10.0-1160.21.1.el7.x86_64 CVE-2020-14351 Important/Sec. kernel-devel-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25211 Important/Sec. kernel-devel-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25645 Important/Sec. kernel-devel-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25656 Important/Sec. kernel-devel-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25705 Important/Sec. kernel-devel-3.10.0-1160.21.1.el7.x86_64 CVE-2020-28374 Important/Sec. kernel-devel-3.10.0-1160.21.1.el7.x86_64 CVE-2020-29661 Important/Sec. kernel-devel-3.10.0-1160.21.1.el7.x86_64 CVE-2021-20265 Important/Sec. kernel-devel-3.10.0-1160.21.1.el7.x86_64 CVE-2021-27363 Important/Sec. kernel-devel-3.10.0-1160.24.1.el7.x86_64 CVE-2021-27364 Important/Sec. kernel-devel-3.10.0-1160.24.1.el7.x86_64 CVE-2021-27365 Important/Sec. kernel-devel-3.10.0-1160.24.1.el7.x86_64 CVE-2020-15436 Moderate/Sec. kernel-headers-3.10.0-1160.15.2.el7.x86_64 CVE-2020-35513 Moderate/Sec. kernel-headers-3.10.0-1160.15.2.el7.x86_64 CVE-2019-19532 Important/Sec. kernel-headers-3.10.0-1160.21.1.el7.x86_64 CVE-2020-0427 Important/Sec. kernel-headers-3.10.0-1160.21.1.el7.x86_64 CVE-2020-7053 Important/Sec. kernel-headers-3.10.0-1160.21.1.el7.x86_64 CVE-2020-14351 Important/Sec. kernel-headers-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25211 Important/Sec. kernel-headers-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25645 Important/Sec. kernel-headers-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25656 Important/Sec. kernel-headers-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25705 Important/Sec. kernel-headers-3.10.0-1160.21.1.el7.x86_64 CVE-2020-28374 Important/Sec. kernel-headers-3.10.0-1160.21.1.el7.x86_64 CVE-2020-29661 Important/Sec. kernel-headers-3.10.0-1160.21.1.el7.x86_64 CVE-2021-20265 Important/Sec. kernel-headers-3.10.0-1160.21.1.el7.x86_64 CVE-2021-27363 Important/Sec. kernel-headers-3.10.0-1160.24.1.el7.x86_64 CVE-2021-27364 Important/Sec. kernel-headers-3.10.0-1160.24.1.el7.x86_64 CVE-2021-27365 Important/Sec. kernel-headers-3.10.0-1160.24.1.el7.x86_64 CVE-2020-15436 Moderate/Sec. kernel-tools-3.10.0-1160.15.2.el7.x86_64 CVE-2020-35513 Moderate/Sec. kernel-tools-3.10.0-1160.15.2.el7.x86_64 CVE-2019-19532 Important/Sec. kernel-tools-3.10.0-1160.21.1.el7.x86_64 CVE-2020-0427 Important/Sec. kernel-tools-3.10.0-1160.21.1.el7.x86_64 CVE-2020-7053 Important/Sec. kernel-tools-3.10.0-1160.21.1.el7.x86_64 CVE-2020-14351 Important/Sec. kernel-tools-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25211 Important/Sec. kernel-tools-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25645 Important/Sec. kernel-tools-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25656 Important/Sec. kernel-tools-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25705 Important/Sec. kernel-tools-3.10.0-1160.21.1.el7.x86_64 CVE-2020-28374 Important/Sec. kernel-tools-3.10.0-1160.21.1.el7.x86_64 CVE-2020-29661 Important/Sec. kernel-tools-3.10.0-1160.21.1.el7.x86_64 CVE-2021-20265 Important/Sec. kernel-tools-3.10.0-1160.21.1.el7.x86_64 CVE-2021-27363 Important/Sec. kernel-tools-3.10.0-1160.24.1.el7.x86_64 CVE-2021-27364 Important/Sec. kernel-tools-3.10.0-1160.24.1.el7.x86_64 CVE-2021-27365 Important/Sec. kernel-tools-3.10.0-1160.24.1.el7.x86_64 CVE-2020-15436 Moderate/Sec. kernel-tools-libs-3.10.0-1160.15.2.el7.x86_64 CVE-2020-35513 Moderate/Sec. kernel-tools-libs-3.10.0-1160.15.2.el7.x86_64 CVE-2019-19532 Important/Sec. kernel-tools-libs-3.10.0-1160.21.1.el7.x86_64 CVE-2020-0427 Important/Sec. kernel-tools-libs-3.10.0-1160.21.1.el7.x86_64 CVE-2020-7053 Important/Sec. kernel-tools-libs-3.10.0-1160.21.1.el7.x86_64 CVE-2020-14351 Important/Sec. kernel-tools-libs-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25211 Important/Sec. kernel-tools-libs-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25645 Important/Sec. kernel-tools-libs-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25656 Important/Sec. kernel-tools-libs-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25705 Important/Sec. kernel-tools-libs-3.10.0-1160.21.1.el7.x86_64 CVE-2020-28374 Important/Sec. kernel-tools-libs-3.10.0-1160.21.1.el7.x86_64 CVE-2020-29661 Important/Sec. kernel-tools-libs-3.10.0-1160.21.1.el7.x86_64 CVE-2021-20265 Important/Sec. kernel-tools-libs-3.10.0-1160.21.1.el7.x86_64 CVE-2021-27363 Important/Sec. kernel-tools-libs-3.10.0-1160.24.1.el7.x86_64 CVE-2021-27364 Important/Sec. kernel-tools-libs-3.10.0-1160.24.1.el7.x86_64 CVE-2021-27365 Important/Sec. kernel-tools-libs-3.10.0-1160.24.1.el7.x86_64 CVE-2020-14363 Important/Sec. libX11-1.6.7-3.el7_9.x86_64 CVE-2020-14363 Important/Sec. libX11-common-1.6.7-3.el7_9.noarch CVE-2019-5094 Moderate/Sec. libcom_err-1.42.9-19.el7.x86_64 CVE-2019-5188 Moderate/Sec. libcom_err-1.42.9-19.el7.x86_64 CVE-2019-5094 Moderate/Sec. libcom_err-devel-1.42.9-19.el7.x86_64 CVE-2019-5188 Moderate/Sec. libcom_err-devel-1.42.9-19.el7.x86_64 CVE-2020-12825 Moderate/Sec. libcroco-0.6.12-6.el7_9.x86_64 CVE-2021-20277 Important/Sec. libldb-1.5.4-2.el7_9.x86_64 CVE-2017-12652 Low/Sec. libpng-2:1.5.13-8.el7.x86_64 CVE-2018-19662 Low/Sec. libsndfile-1.0.25-12.el7.x86_64 CVE-2019-5094 Moderate/Sec. libss-1.42.9-19.el7.x86_64 CVE-2019-5188 Moderate/Sec. libss-1.42.9-19.el7.x86_64 CVE-2019-17498 Moderate/Sec. libssh2-1.8.0-4.el7.x86_64 CVE-2019-14973 Moderate/Sec. libtiff-4.0.3-35.el7.x86_64 CVE-2019-17546 Moderate/Sec. libtiff-4.0.3-35.el7.x86_64 CVE-2017-0393 Moderate/Sec. libvpx-1.3.0-8.el7.x86_64 CVE-2019-9232 Moderate/Sec. libvpx-1.3.0-8.el7.x86_64 CVE-2019-9433 Moderate/Sec. libvpx-1.3.0-8.el7.x86_64 CVE-2020-0034 Moderate/Sec. libvpx-1.3.0-8.el7.x86_64 CVE-2019-3833 Moderate/Sec. libwsman1-2.6.3-7.git4391e5c.el7.x86_64 CVE-2019-19956 Moderate/Sec. libxml2-2.9.1-6.el7.5.x86_64 CVE-2019-20388 Moderate/Sec. libxml2-2.9.1-6.el7.5.x86_64 CVE-2020-7595 Moderate/Sec. libxml2-2.9.1-6.el7.5.x86_64 CVE-2019-19956 Moderate/Sec. libxml2-python-2.9.1-6.el7.5.x86_64 CVE-2019-20388 Moderate/Sec. libxml2-python-2.9.1-6.el7.5.x86_64 CVE-2020-7595 Moderate/Sec. libxml2-python-2.9.1-6.el7.5.x86_64 CVE-2019-11068 Moderate/Sec. libxslt-1.1.28-6.el7.x86_64 CVE-2019-18197 Moderate/Sec. libxslt-1.1.28-6.el7.x86_64 CVE-2020-12321 Important/Sec. linux-firmware-20200421-80.git78c0348.el7_9.noarch CVE-2019-2974 Moderate/Sec. mariadb-libs-1:5.5.68-1.el7.x86_64 CVE-2020-2574 Moderate/Sec. mariadb-libs-1:5.5.68-1.el7.x86_64 CVE-2020-2752 Moderate/Sec. mariadb-libs-1:5.5.68-1.el7.x86_64 CVE-2020-2780 Moderate/Sec. mariadb-libs-1:5.5.68-1.el7.x86_64 CVE-2020-2812 Moderate/Sec. mariadb-libs-1:5.5.68-1.el7.x86_64 CVE-2021-20305 Important/Sec. nettle-2.7.1-9.el7_9.x86_64 CVE-2019-19126 Low/Sec. nscd-2.17-317.el7.x86_64 CVE-2019-25013 Moderate/Sec. nscd-2.17-322.el7_9.x86_64 CVE-2020-10029 Moderate/Sec. nscd-2.17-322.el7_9.x86_64 CVE-2020-29573 Moderate/Sec. nscd-2.17-322.el7_9.x86_64 CVE-2020-12243 Moderate/Sec. openldap-2.4.44-22.el7.x86_64 CVE-2020-12243 Moderate/Sec. openldap-clients-2.4.44-22.el7.x86_64 CVE-2019-3833 Moderate/Sec. openwsman-python-2.6.3-7.git4391e5c.el7.x86_64 CVE-2020-15436 Moderate/Sec. perf-3.10.0-1160.15.2.el7.x86_64 CVE-2020-35513 Moderate/Sec. perf-3.10.0-1160.15.2.el7.x86_64 CVE-2019-19532 Important/Sec. perf-3.10.0-1160.21.1.el7.x86_64 CVE-2020-0427 Important/Sec. perf-3.10.0-1160.21.1.el7.x86_64 CVE-2020-7053 Important/Sec. perf-3.10.0-1160.21.1.el7.x86_64 CVE-2020-14351 Important/Sec. perf-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25211 Important/Sec. perf-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25645 Important/Sec. perf-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25656 Important/Sec. perf-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25705 Important/Sec. perf-3.10.0-1160.21.1.el7.x86_64 CVE-2020-28374 Important/Sec. perf-3.10.0-1160.21.1.el7.x86_64 CVE-2020-29661 Important/Sec. perf-3.10.0-1160.21.1.el7.x86_64 CVE-2021-20265 Important/Sec. perf-3.10.0-1160.21.1.el7.x86_64 CVE-2021-27363 Important/Sec. perf-3.10.0-1160.24.1.el7.x86_64 CVE-2021-27364 Important/Sec. perf-3.10.0-1160.24.1.el7.x86_64 CVE-2021-27365 Important/Sec. perf-3.10.0-1160.24.1.el7.x86_64 CVE-2020-10543 Moderate/Sec. perl-4:5.16.3-299.el7_9.x86_64 CVE-2020-10878 Moderate/Sec. perl-4:5.16.3-299.el7_9.x86_64 CVE-2020-12723 Moderate/Sec. perl-4:5.16.3-299.el7_9.x86_64 CVE-2020-10543 Moderate/Sec. perl-CPAN-1.9800-299.el7_9.noarch CVE-2020-10878 Moderate/Sec. perl-CPAN-1.9800-299.el7_9.noarch CVE-2020-12723 Moderate/Sec. perl-CPAN-1.9800-299.el7_9.noarch CVE-2020-10543 Moderate/Sec. perl-ExtUtils-Install-1.58-299.el7_9.noarch CVE-2020-10878 Moderate/Sec. perl-ExtUtils-Install-1.58-299.el7_9.noarch CVE-2020-12723 Moderate/Sec. perl-ExtUtils-Install-1.58-299.el7_9.noarch CVE-2020-10543 Moderate/Sec. perl-IO-Zlib-1:1.10-299.el7_9.noarch CVE-2020-10878 Moderate/Sec. perl-IO-Zlib-1:1.10-299.el7_9.noarch CVE-2020-12723 Moderate/Sec. perl-IO-Zlib-1:1.10-299.el7_9.noarch CVE-2020-10543 Moderate/Sec. perl-Package-Constants-1:0.02-299.el7_9.noarch CVE-2020-10878 Moderate/Sec. perl-Package-Constants-1:0.02-299.el7_9.noarch CVE-2020-12723 Moderate/Sec. perl-Package-Constants-1:0.02-299.el7_9.noarch CVE-2020-10543 Moderate/Sec. perl-Pod-Escapes-1:1.04-299.el7_9.noarch CVE-2020-10878 Moderate/Sec. perl-Pod-Escapes-1:1.04-299.el7_9.noarch CVE-2020-12723 Moderate/Sec. perl-Pod-Escapes-1:1.04-299.el7_9.noarch CVE-2020-10543 Moderate/Sec. perl-devel-4:5.16.3-299.el7_9.x86_64 CVE-2020-10878 Moderate/Sec. perl-devel-4:5.16.3-299.el7_9.x86_64 CVE-2020-12723 Moderate/Sec. perl-devel-4:5.16.3-299.el7_9.x86_64 CVE-2020-10543 Moderate/Sec. perl-libs-4:5.16.3-299.el7_9.x86_64 CVE-2020-10878 Moderate/Sec. perl-libs-4:5.16.3-299.el7_9.x86_64 CVE-2020-12723 Moderate/Sec. perl-libs-4:5.16.3-299.el7_9.x86_64 CVE-2020-10543 Moderate/Sec. perl-macros-4:5.16.3-299.el7_9.x86_64 CVE-2020-10878 Moderate/Sec. perl-macros-4:5.16.3-299.el7_9.x86_64 CVE-2020-12723 Moderate/Sec. perl-macros-4:5.16.3-299.el7_9.x86_64 CVE-2019-10146 Important/Sec. pki-base-10.5.18-12.el7_9.noarch CVE-2019-10179 Important/Sec. pki-base-10.5.18-12.el7_9.noarch CVE-2019-10221 Important/Sec. pki-base-10.5.18-12.el7_9.noarch CVE-2020-1721 Important/Sec. pki-base-10.5.18-12.el7_9.noarch CVE-2020-25715 Important/Sec. pki-base-10.5.18-12.el7_9.noarch CVE-2021-20179 Important/Sec. pki-base-10.5.18-12.el7_9.noarch CVE-2019-10146 Important/Sec. pki-base-java-10.5.18-12.el7_9.noarch CVE-2019-10179 Important/Sec. pki-base-java-10.5.18-12.el7_9.noarch CVE-2019-10221 Important/Sec. pki-base-java-10.5.18-12.el7_9.noarch CVE-2020-1721 Important/Sec. pki-base-java-10.5.18-12.el7_9.noarch CVE-2020-25715 Important/Sec. pki-base-java-10.5.18-12.el7_9.noarch CVE-2021-20179 Important/Sec. pki-base-java-10.5.18-12.el7_9.noarch CVE-2019-10146 Important/Sec. pki-ca-10.5.18-12.el7_9.noarch CVE-2019-10179 Important/Sec. pki-ca-10.5.18-12.el7_9.noarch CVE-2019-10221 Important/Sec. pki-ca-10.5.18-12.el7_9.noarch CVE-2020-1721 Important/Sec. pki-ca-10.5.18-12.el7_9.noarch CVE-2020-25715 Important/Sec. pki-ca-10.5.18-12.el7_9.noarch CVE-2021-20179 Important/Sec. pki-ca-10.5.18-12.el7_9.noarch CVE-2019-10146 Important/Sec. pki-kra-10.5.18-12.el7_9.noarch CVE-2019-10179 Important/Sec. pki-kra-10.5.18-12.el7_9.noarch CVE-2019-10221 Important/Sec. pki-kra-10.5.18-12.el7_9.noarch CVE-2020-1721 Important/Sec. pki-kra-10.5.18-12.el7_9.noarch CVE-2020-25715 Important/Sec. pki-kra-10.5.18-12.el7_9.noarch CVE-2021-20179 Important/Sec. pki-kra-10.5.18-12.el7_9.noarch CVE-2019-10146 Important/Sec. pki-server-10.5.18-12.el7_9.noarch CVE-2019-10179 Important/Sec. pki-server-10.5.18-12.el7_9.noarch CVE-2019-10221 Important/Sec. pki-server-10.5.18-12.el7_9.noarch CVE-2020-1721 Important/Sec. pki-server-10.5.18-12.el7_9.noarch CVE-2020-25715 Important/Sec. pki-server-10.5.18-12.el7_9.noarch CVE-2021-20179 Important/Sec. pki-server-10.5.18-12.el7_9.noarch CVE-2019-10146 Important/Sec. pki-tools-10.5.18-12.el7_9.x86_64 CVE-2019-10179 Important/Sec. pki-tools-10.5.18-12.el7_9.x86_64 CVE-2019-10221 Important/Sec. pki-tools-10.5.18-12.el7_9.x86_64 CVE-2020-1721 Important/Sec. pki-tools-10.5.18-12.el7_9.x86_64 CVE-2020-25715 Important/Sec. pki-tools-10.5.18-12.el7_9.x86_64 CVE-2021-20179 Important/Sec. pki-tools-10.5.18-12.el7_9.x86_64 CVE-2021-20277 Important/Sec. pyldb-1.5.4-2.el7_9.x86_64 CVE-2020-15436 Moderate/Sec. python-perf-3.10.0-1160.15.2.el7.x86_64 CVE-2020-35513 Moderate/Sec. python-perf-3.10.0-1160.15.2.el7.x86_64 CVE-2019-19532 Important/Sec. python-perf-3.10.0-1160.21.1.el7.x86_64 CVE-2020-0427 Important/Sec. python-perf-3.10.0-1160.21.1.el7.x86_64 CVE-2020-7053 Important/Sec. python-perf-3.10.0-1160.21.1.el7.x86_64 CVE-2020-14351 Important/Sec. python-perf-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25211 Important/Sec. python-perf-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25645 Important/Sec. python-perf-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25656 Important/Sec. python-perf-3.10.0-1160.21.1.el7.x86_64 CVE-2020-25705 Important/Sec. python-perf-3.10.0-1160.21.1.el7.x86_64 CVE-2020-28374 Important/Sec. python-perf-3.10.0-1160.21.1.el7.x86_64 CVE-2020-29661 Important/Sec. python-perf-3.10.0-1160.21.1.el7.x86_64 CVE-2021-20265 Important/Sec. python-perf-3.10.0-1160.21.1.el7.x86_64 CVE-2021-27363 Important/Sec. python-perf-3.10.0-1160.24.1.el7.x86_64 CVE-2021-27364 Important/Sec. python-perf-3.10.0-1160.24.1.el7.x86_64 CVE-2021-27365 Important/Sec. python-perf-3.10.0-1160.24.1.el7.x86_64 CVE-2020-5313 Moderate/Sec. python-pillow-2.0.0-21.gitd1c6db8.el7.x86_64 CVE-2015-9251 Moderate/Sec. python2-ipaclient-4.6.8-5.el7.noarch CVE-2016-10735 Moderate/Sec. python2-ipaclient-4.6.8-5.el7.noarch CVE-2018-14040 Moderate/Sec. python2-ipaclient-4.6.8-5.el7.noarch CVE-2018-14042 Moderate/Sec. python2-ipaclient-4.6.8-5.el7.noarch CVE-2018-20676 Moderate/Sec. python2-ipaclient-4.6.8-5.el7.noarch CVE-2018-20677 Moderate/Sec. python2-ipaclient-4.6.8-5.el7.noarch CVE-2019-8331 Moderate/Sec. python2-ipaclient-4.6.8-5.el7.noarch CVE-2019-11358 Moderate/Sec. python2-ipaclient-4.6.8-5.el7.noarch CVE-2020-1722 Moderate/Sec. python2-ipaclient-4.6.8-5.el7.noarch CVE-2020-11022 Moderate/Sec. python2-ipaclient-4.6.8-5.el7.noarch CVE-2020-11023 Moderate/Sec. python2-ipaclient-4.6.8-5.el7_9.4.noarch CVE-2015-9251 Moderate/Sec. python2-ipalib-4.6.8-5.el7.noarch CVE-2016-10735 Moderate/Sec. python2-ipalib-4.6.8-5.el7.noarch CVE-2018-14040 Moderate/Sec. python2-ipalib-4.6.8-5.el7.noarch CVE-2018-14042 Moderate/Sec. python2-ipalib-4.6.8-5.el7.noarch CVE-2018-20676 Moderate/Sec. python2-ipalib-4.6.8-5.el7.noarch CVE-2018-20677 Moderate/Sec. python2-ipalib-4.6.8-5.el7.noarch CVE-2019-8331 Moderate/Sec. python2-ipalib-4.6.8-5.el7.noarch CVE-2019-11358 Moderate/Sec. python2-ipalib-4.6.8-5.el7.noarch CVE-2020-1722 Moderate/Sec. python2-ipalib-4.6.8-5.el7.noarch CVE-2020-11022 Moderate/Sec. python2-ipalib-4.6.8-5.el7.noarch CVE-2020-11023 Moderate/Sec. python2-ipalib-4.6.8-5.el7_9.4.noarch CVE-2015-9251 Moderate/Sec. python2-ipaserver-4.6.8-5.el7.noarch CVE-2016-10735 Moderate/Sec. python2-ipaserver-4.6.8-5.el7.noarch CVE-2018-14040 Moderate/Sec. python2-ipaserver-4.6.8-5.el7.noarch CVE-2018-14042 Moderate/Sec. python2-ipaserver-4.6.8-5.el7.noarch CVE-2018-20676 Moderate/Sec. python2-ipaserver-4.6.8-5.el7.noarch CVE-2018-20677 Moderate/Sec. python2-ipaserver-4.6.8-5.el7.noarch CVE-2019-8331 Moderate/Sec. python2-ipaserver-4.6.8-5.el7.noarch CVE-2019-11358 Moderate/Sec. python2-ipaserver-4.6.8-5.el7.noarch CVE-2020-1722 Moderate/Sec. python2-ipaserver-4.6.8-5.el7.noarch CVE-2020-11022 Moderate/Sec. python2-ipaserver-4.6.8-5.el7.noarch CVE-2020-11023 Moderate/Sec. python2-ipaserver-4.6.8-5.el7_9.4.noarch CVE-2018-15746 Low/Sec. qemu-img-10:1.5.3-175.el7.x86_64 CVE-2019-20382 Low/Sec. qemu-img-10:1.5.3-175.el7.x86_64 CVE-2020-1983 Important/Sec. qemu-img-10:1.5.3-175.el7_9.1.x86_64 CVE-2020-14364 Important/Sec. qemu-img-10:1.5.3-175.el7_9.1.x86_64 CVE-2020-13765 Moderate/Sec. qemu-img-10:1.5.3-175.el7_9.3.x86_64 CVE-2020-16092 Moderate/Sec. qemu-img-10:1.5.3-175.el7_9.3.x86_64 CVE-2018-15746 Low/Sec. qemu-kvm-10:1.5.3-175.el7.x86_64 CVE-2019-20382 Low/Sec. qemu-kvm-10:1.5.3-175.el7.x86_64 CVE-2020-1983 Important/Sec. qemu-kvm-10:1.5.3-175.el7_9.1.x86_64 CVE-2020-14364 Important/Sec. qemu-kvm-10:1.5.3-175.el7_9.1.x86_64 CVE-2020-13765 Moderate/Sec. qemu-kvm-10:1.5.3-175.el7_9.3.x86_64 CVE-2020-16092 Moderate/Sec. qemu-kvm-10:1.5.3-175.el7_9.3.x86_64 CVE-2018-15746 Low/Sec. qemu-kvm-common-10:1.5.3-175.el7.x86_64 CVE-2019-20382 Low/Sec. qemu-kvm-common-10:1.5.3-175.el7.x86_64 CVE-2020-1983 Important/Sec. qemu-kvm-common-10:1.5.3-175.el7_9.1.x86_64 CVE-2020-14364 Important/Sec. qemu-kvm-common-10:1.5.3-175.el7_9.1.x86_64 CVE-2020-13765 Moderate/Sec. qemu-kvm-common-10:1.5.3-175.el7_9.3.x86_64 CVE-2020-16092 Moderate/Sec. qemu-kvm-common-10:1.5.3-175.el7_9.3.x86_64 CVE-2021-26937 Important/Sec. screen-4.1.0-0.27.20120314git3c2946.el7_9.x86_64 CVE-2020-14355 Important/Sec. spice-server-0.14.0-9.el7_9.1.x86_64 CVE-2018-11782 Moderate/Sec. subversion-1.7.14-16.el7.x86_64 CVE-2018-11782 Moderate/Sec. subversion-libs-1.7.14-16.el7.x86_64 CVE-2021-3156 Important/Sec. sudo-1.8.23-10.el7_9.1.x86_64 CVE-2021-27803 Important/Sec. wpa_supplicant-1:2.6-12.el7_9.2.x86_64
```

## 7.8.21.01.SP1

Security patch released in February 2021.

The 7.8.21.01.SP1 patch is based on RHEL 7.8, and it can only be installed on versions 1.0.7.4 and 1.0.7.5. **Do not apply the patch on earlier versions of the system.**

The list of Red Hat CVEs patched in this release:

```plaintext
CVE-2020-10713 Moderate/Sec. grub2-1:2.02-0.86.el7_8.x86_64 CVE-2020-14308 Moderate/Sec. grub2-1:2.02-0.86.el7_8.x86_64 CVE-2020-14309 Moderate/Sec. grub2-1:2.02-0.86.el7_8.x86_64 CVE-2020-14310 Moderate/Sec. grub2-1:2.02-0.86.el7_8.x86_64 CVE-2020-14311 Moderate/Sec. grub2-1:2.02-0.86.el7_8.x86_64 CVE-2020-15705 Moderate/Sec. grub2-1:2.02-0.86.el7_8.x86_64 CVE-2020-15706 Moderate/Sec. grub2-1:2.02-0.86.el7_8.x86_64 CVE-2020-15707 Moderate/Sec. grub2-1:2.02-0.86.el7_8.x86_64 CVE-2020-10713 Moderate/Sec. grub2-common-1:2.02-0.86.el7_8.noarch CVE-2020-14308 Moderate/Sec. grub2-common-1:2.02-0.86.el7_8.noarch CVE-2020-14309 Moderate/Sec. grub2-common-1:2.02-0.86.el7_8.noarch CVE-2020-14310 Moderate/Sec. grub2-common-1:2.02-0.86.el7_8.noarch CVE-2020-14311 Moderate/Sec. grub2-common-1:2.02-0.86.el7_8.noarch CVE-2020-15705 Moderate/Sec. grub2-common-1:2.02-0.86.el7_8.noarch CVE-2020-15706 Moderate/Sec. grub2-common-1:2.02-0.86.el7_8.noarch CVE-2020-15707 Moderate/Sec. grub2-common-1:2.02-0.86.el7_8.noarch CVE-2020-10713 Moderate/Sec. grub2-pc-1:2.02-0.86.el7_8.x86_64 CVE-2020-14308 Moderate/Sec. grub2-pc-1:2.02-0.86.el7_8.x86_64 CVE-2020-14309 Moderate/Sec. grub2-pc-1:2.02-0.86.el7_8.x86_64 CVE-2020-14310 Moderate/Sec. grub2-pc-1:2.02-0.86.el7_8.x86_64 CVE-2020-14311 Moderate/Sec. grub2-pc-1:2.02-0.86.el7_8.x86_64 CVE-2020-15705 Moderate/Sec. grub2-pc-1:2.02-0.86.el7_8.x86_64 CVE-2020-15706 Moderate/Sec. grub2-pc-1:2.02-0.86.el7_8.x86_64 CVE-2020-15707 Moderate/Sec. grub2-pc-1:2.02-0.86.el7_8.x86_64 CVE-2020-10713 Moderate/Sec. grub2-pc-modules-1:2.02-0.86.el7_8.noarch CVE-2020-14308 Moderate/Sec. grub2-pc-modules-1:2.02-0.86.el7_8.noarch CVE-2020-14309 Moderate/Sec. grub2-pc-modules-1:2.02-0.86.el7_8.noarch CVE-2020-14310 Moderate/Sec. grub2-pc-modules-1:2.02-0.86.el7_8.noarch CVE-2020-14311 Moderate/Sec. grub2-pc-modules-1:2.02-0.86.el7_8.noarch CVE-2020-15705 Moderate/Sec. grub2-pc-modules-1:2.02-0.86.el7_8.noarch CVE-2020-15706 Moderate/Sec. grub2-pc-modules-1:2.02-0.86.el7_8.noarch CVE-2020-15707 Moderate/Sec. grub2-pc-modules-1:2.02-0.86.el7_8.noarch CVE-2020-10713 Moderate/Sec. grub2-tools-1:2.02-0.86.el7_8.x86_64 CVE-2020-14308 Moderate/Sec. grub2-tools-1:2.02-0.86.el7_8.x86_64 CVE-2020-14309 Moderate/Sec. grub2-tools-1:2.02-0.86.el7_8.x86_64 CVE-2020-14310 Moderate/Sec. grub2-tools-1:2.02-0.86.el7_8.x86_64 CVE-2020-14311 Moderate/Sec. grub2-tools-1:2.02-0.86.el7_8.x86_64 CVE-2020-15705 Moderate/Sec. grub2-tools-1:2.02-0.86.el7_8.x86_64 CVE-2020-15706 Moderate/Sec. grub2-tools-1:2.02-0.86.el7_8.x86_64 CVE-2020-15707 Moderate/Sec. grub2-tools-1:2.02-0.86.el7_8.x86_64 CVE-2020-10713 Moderate/Sec. grub2-tools-extra-1:2.02-0.86.el7_8.x86_64 CVE-2020-14308 Moderate/Sec. grub2-tools-extra-1:2.02-0.86.el7_8.x86_64 CVE-2020-14309 Moderate/Sec. grub2-tools-extra-1:2.02-0.86.el7_8.x86_64 CVE-2020-14310 Moderate/Sec. grub2-tools-extra-1:2.02-0.86.el7_8.x86_64 CVE-2020-14311 Moderate/Sec. grub2-tools-extra-1:2.02-0.86.el7_8.x86_64 CVE-2020-15705 Moderate/Sec. grub2-tools-extra-1:2.02-0.86.el7_8.x86_64 CVE-2020-15706 Moderate/Sec. grub2-tools-extra-1:2.02-0.86.el7_8.x86_64 CVE-2020-15707 Moderate/Sec. grub2-tools-extra-1:2.02-0.86.el7_8.x86_64 CVE-2020-10713 Moderate/Sec. grub2-tools-minimal-1:2.02-0.86.el7_8.x86_64 CVE-2020-14308 Moderate/Sec. grub2-tools-minimal-1:2.02-0.86.el7_8.x86_64 CVE-2020-14309 Moderate/Sec. grub2-tools-minimal-1:2.02-0.86.el7_8.x86_64 CVE-2020-14310 Moderate/Sec. grub2-tools-minimal-1:2.02-0.86.el7_8.x86_64 CVE-2020-14311 Moderate/Sec. grub2-tools-minimal-1:2.02-0.86.el7_8.x86_64 CVE-2020-15705 Moderate/Sec. grub2-tools-minimal-1:2.02-0.86.el7_8.x86_64 CVE-2020-15706 Moderate/Sec. grub2-tools-minimal-1:2.02-0.86.el7_8.x86_64 CVE-2020-15707 Moderate/Sec. grub2-tools-minimal-1:2.02-0.86.el7_8.x86_64
```