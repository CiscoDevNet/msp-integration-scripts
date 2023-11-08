# Cisco Umbrella Roaming Client Deployment

## Introduction

Cisco Umbrella provides install and uninstall scripts, as well as agent procedures, for Managed Service Providers (MSPs) to deploy the Cisco Umbrella Roaming client using Kaseya VSA and ConnectWise Automate. These scripts allow MSPs to import, set up system variables, and install the Umbrella Roaming client easily.

## Scripts Overview

### Install Script

The install script enables you to configure the appearance and behavior of the roaming client on Windows devices using both required and optional parameters. When running the script, you will be prompted to enter the necessary parameters, which will then be appended to the `msiexec` command and executed using the shell command.

#### Required Parameters

The install script requires the following parameters. You need to provide these values during runtime or scheduled execution. You can find the required deployment parameters in the MSP console on the Customer Management page by expanding the customer card:

- Organization Fingerprint
- Organization ID
- User ID

#### Optional Parameters

The install script also supports optional parameters that allow you to customize the appearance and behavior of the roaming client on the device. These parameters control various aspects of the client related to the internal domains configured in the Cisco Umbrella dashboard. Here are the optional parameters:

- `HIDE_UI`: Hide the roaming client's tray icon from the system tray of the Windows device, reducing end-user awareness of the roaming client.
  - Values:
    - 0: Show system tray icon (default)
    - 1: Hide system tray icon

- `HIDE_ARP`: Hide the roaming client from the Add/Remove Programs list in Windows, preventing removal by an end-user with admin rights.
  - Values:
    - 0: Show in list (default)
    - 1: Omit from list

- `NO_AUTOSUFFIX` (To be determined): Do not add domains present in the DNS Suffixes settings in network adapters and networking properties to the Internal Domains list. This parameter enhances the roaming client's awareness of local resources/domains on foreign networks.
  - Values:
    - 0: Add the domains (default)
    - 1: Do not add the domains

- `NO_NXDOMAIN` (To be determined): If a DNS query sent to Umbrella returns an NXDOMAIN, query the local DNS servers before giving up.
  - Values:
    - 0: Query local DNS servers (default)
    - 1: Do not query local DNS servers

### Uninstall Script

The uninstall script provides a simple automated approach to remove the Cisco Umbrella Roaming Client. It executes the shell command `wmic product where name='Umbrella Roaming Client' call uninstall`. This method was sourced from Umbrella Support (https://support.umbrella.com/hc/en-us/articles/230901028-Umbrella-Roaming-Client-Uninstalling).