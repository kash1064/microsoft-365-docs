---
title: Device health and compliance report in Microsoft Defender for Endpoint
description: Use the device health and compliance report to track device health, antivirus status and versions, OS platforms, and Windows 10 versions.
keywords: health state, antivirus, os platform, windows 10 version, version, health, compliance, state
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
ms.date: 09/01/2022 
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
---

# Device health and compliance report in Microsoft Defender for Endpoint

**Applies to:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Business](../defender-business/mdb-overview.md)

> Want to experience Microsoft Defender for Endpoint? [Sign up for a free trial.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

The devices status report provides high-level information about the devices in your organization. The report includes trending information showing the sensor health state, antivirus status, OS platforms, and Windows 10 versions.

> [!IMPORTANT]
> For Windows&nbsp;Server&nbsp;2012&nbsp;R2 and Windows&nbsp;Server&nbsp;2016 to appear in device health reports, these devices must be onboarded using the modern unified solution package. For more information, see [New functionality in the modern unified solution for Windows Server 2012 R2 and 2016](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution).

In the Microsoft 365 Security dashboard navigation panel, select **Reports**, and then open **Device health and compliance**.
The Device health and compliance dashboard is structured in two tabs:

- The [**Sensor health & OS** tab](#sensor-health--os-tab) provides general operating system information, divided into three cards that display the following device attributes:
  - [Sensor health card](#sensor-health-card)
  - [Operating systems and platforms card](#operating-systems-and-platforms-card)
  - [Windows 10 versions card](#windows-10-versions-card)

- The [**Microsoft Defender Antivirus health** tab](#microsoft-defender-antivirus-health-tab) has eight cards that report on aspects of Microsoft Defender Antivirus:
  - [Antivirus mode card](#antivirus-mode-card)
  - [Antivirus engine version card](#antivirus-engine-version-card)
  - [Antivirus security intelligence version card](#antivirus-security-intelligence-version-card)
  - [Antivirus platform version card](#antivirus-platform-version-card)
  - [Recent antivirus scan results card](#recent-antivirus-scan-results-card)
  - [Antivirus engine updates card](#antivirus-engine-updates-card)
  - [Security intelligence updates card](#security-intelligence-updates-card)
  - [Antivirus platform updates card](#antivirus-platform-updates-card)

## Report access permissions

To access the Device health and antivirus compliance report in the Microsoft 365 Security dashboard, the following permissions are required:

| Permission name | Permission type |
|:---|:---|
| View Data | Threat and vulnerability management (TVM) |

To Assign these permissions:

1. Sign in to <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> using account with Security administrator or Global administrator role assigned.
1. In the navigation pane, select **Settings** \> **Endpoints** \> **Roles** (under **Permissions**).
1. Select the role you'd like to edit.
1. Select **Edit**.
1. In **Edit role**, on the **General** tab, in **Role name**, type a name for the role.
1. In **Description** type a brief summary of the role.
1. In **Permissions**, select **View Data**, and under **View Data** select **Threat and vulnerability management** (TVM).

For more information about user role management, see [Create and manage roles for role-based access control](user-roles.md).

## Sensor health & OS tab

Sensor health and OS cards report on general operating system health, which includes detection sensor health, up-to-date versus out-of-date operating systems, and Windows 10 versions.

>:::image type="content" source="images/device-health-sensor-health-os-tab.png" alt-text="Shows Sensor health and Operating system information." lightbox="images/device-health-sensor-health-os-tab.png":::

Each of the three cards on the **Sensor health** tab has two reporting sections, _Current state_ and _device trends_, presented as graphs:

### Current state graph

In each card, the Current state (referred to in some documentation as _Device summary_) is the top, horizontal bar graph. Current state is a snapshot that shows information collected about devices in your organization, scoped to the current day. This graph represents the distribution of devices across your organization that report status or are detected to be in a specific state.

>:::image type="content" source="images/device-health-sensor-health-os-current-state-graph.png" alt-text="Shows the current state graph." lightbox="images/device-health-sensor-health-os-current-state-graph.png":::

### Device trends graph

The lower graph on each of the three cards isn't named, but is commonly known as _device trends_. The device trends graph depicts the collection of devices across your organization, throughout the time span indicated directly above the graph.
By default, the device trends graph displays device information from the 30-day period, ending in the latest full day. To gain a better perspective about trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown. To adjust the time period, open the filter and select a start day and end day.

>:::image type="content" source="images/device-health-sensor-health-os-device-trends-graph.png" alt-text="Shows the Device Health versions trends graph." lightbox="images/device-health-sensor-health-os-device-trends-graph.png":::

### Filtering data

Use the provided filters to include or exclude devices with certain attributes. You can select multiple filters to apply from the device attributes. When applied, filters apply to all three cards in the report.

For example, to show data about Windows 10 devices with Active sensor health state:

1. Under **Filters** > **Sensor health state** > **Active**.
2. Then select **OS platforms** > **Windows 10**.
3. Select **Apply**.

### Sensor health card

The Sensor health card displays information about the sensor state on devices. Sensor health provides an aggregate view of devices that are:

- active
- inactive
- experiencing impaired communications
- or where no sensor data is reported

Devices that are either experiencing impaired communications, or devices from which no sensor data is detected could expose your organization to risks, and warrant investigation. Likewise, devices that are inactive for extended periods of time could expose your organization to threats due to out-of-date software. Devices that are inactive for long periods of time also warrant investigation.

> [!NOTE]
>
> In a small percentage of cases, the numbers and distributions reported when clicking on the horizontal Sensor health bar graph will be out of synch with the values shown in the **Device inventory** page. The disparity in values can occur because the Sensor Health Reports has a different refresh cadence than the Device Inventory page.

### Operating systems and platforms card

This card shows the distribution of operating systems and platforms that exist within your organization.
_OS systems and platforms_ can give useful insights into whether devices in your organization are running current or outdated operating systems. When new operating systems are introduced, security enhancements are frequently included that improve your organization's posture against security threats.

For example, Secure Boot (introduced in Windows 8) practically eliminated the threat from some of the most harmful types of malware. Improvements in Windows 10 provide PC manufacturers the option to prevent users from disabling Secure Boot. Preventing users from disabling Secure Boot removes almost any chance of malicious rootkits or other low-level malware from infecting the boot process.

Ideally, the “Current state” graph shows that the number of operating systems is weighted in favor of more current OS over older versions. Otherwise, the trends graph indicates that new systems are being adopted and/or older systems are being updated or replaced.

### Windows 10 versions card

The Windows 10 versions card shows the distribution of Windows devices and their versions in your organization.
In the same way that an upgrade from Windows 8 to Windows 10 improves security in your organization, changing from early releases of Windows to more current versions improves your posture against possible threats.

The Windows version trend graph can help you quickly determine whether your organization is keeping current by updating to the most recent, most secure versions of Windows 10.

## Microsoft Defender Antivirus health tab  

The Microsoft Defender Antivirus health tab contains eight cards that report on several aspects of Microsoft Defender Antivirus in your organization:

Two cards, [Antivirus mode card](#antivirus-mode-card) and [Recent antivirus scan results card](#recent-antivirus-scan-results-card), report about Microsoft Defender Antivirus functions.

The remaining six cards report about the Microsoft Defender Antivirus status for devices in your organization:

| _version_ cards: | _update_ cards{<a id="fn1">1</a>} |
|:---|:---|
| [Antivirus engine version card](#antivirus-engine-version-card) <br> [Antivirus security intelligence version card](#antivirus-security-intelligence-version-card) <br> [Antivirus platform version card](#antivirus-platform-version-card) | [Antivirus engine updates card](#antivirus-engine-updates-card) <br> [Security intelligence updates card](#security-intelligence-updates-card) <br> [Antivirus platform updates card](#antivirus-platform-updates-card) |
| The three version cards provide flyout reports that provide additional information, and enable further exploration. | The three up-to-date reporting cards provide links to resources to learn more. |

<sup>{[1](#fn1)}</sup> For the three _updates_ cards (also known as up-to-date reporting cards), "**No data available**" (or "Unknown" value) indicates devices that aren't reporting update status. Devices that aren't reporting update status can be due to various reasons, such as:

- Computer is disconnected from the network
- Computer is powered down or in a hibernation state
- Microsoft Defender Antivirus is disabled
- Device is a non-Windows (Mac or Linux) device
- Cloud protection isn't enabled
- Device does not meet pre-requisites for Antivirus engine or platform version

### Prerequisites

Up to date reporting generates information for devices that meet the following criteria:

- Engine version: 1.1.19300.2+
- Platform version: 4.18.2202.1+
- Cloud protection enabled
- Windows OS*

*Currently up to date reporting is only available for windows devices. Cross platform devices such as Mac and Linux are listed under “no data available”

>:::image type="content" source="images/device-health-defender-antivirus-health-tab.png" alt-text="Shows the Microsoft Defender Antivirus Health tab." lightbox="images/device-health-defender-antivirus-health-tab.png":::

### Card functionality

The functionality is essentially the same for all cards. By clicking on a numbered bar in any of the cards, the **Microsoft Defender Antivirus details** flyout opens enabling you to review information about all the devices configured with the version number of an aspect on that card.

>:::image type="content" source="images/device-health-defender-antivirus-health-antivirus-details.png" alt-text="Shows the Microsoft Defender Antivirus details flyout." lightbox="images/device-health-defender-antivirus-health-antivirus-details.png":::

If the version number that you clicked on is:

- A current version, then **Remediation required** and **Security recommendation** aren't present
- An outdated version, a notification at the top of the report is present, indicating **Remediation required**, and a **Security recommendation** link is present. Select the security recommendation link to navigate to the threat and vulnerability management console, which can recommend appropriate antivirus updates.

To add or remove specific types of information on the **Microsoft Defender Antivirus details** flyout,  select **Customize Columns**. In **Customize Columns**, select or clear items to specify what you want included in the Microsoft Defender Antivirus details report.

>:::image type="content" source="images/device-health-defender-antivirus-engine-version-details-custom-columns.png" alt-text="Shows custom column options for Microsoft Defender Antivirus health reporting." lightbox="images/device-health-defender-antivirus-engine-version-details-custom-columns.png":::

#### New Microsoft Defender Antivirus filter definitions

The following table contains a list of terms that are new to Microsoft Defender Antivirus reporting.

| Column name | Description |
|:---|:---|
| Security intel publish time  | Indicates Microsoft’s release date of the security intelligence update version on the device. Devices with a security intelligence publish time greater than 7 days are considered out of date in the reports. |
| Last seen | Indicates date when device last had connection. |
| Data refresh timestamp  | Indicates when client events were last received for reporting on AV mode, AV engine version,  AV platform version, AV security intelligence version, and scan information. |
| Signature refresh time | Indicates when client events were last received for reporting on engine, platform, and signature up to date status. |

Within the flyout: clicking on the name of the device will redirect you to the "Device page" for that device, where you can access detailed reports.

#### Export report

There are two levels of reports that you can export:

##### Top level export

There are two different export csv functionalities through the portal:

- **Top-level export** You can use the top level **Export** button  to gather an all-up Microsoft Defender Antivirus health report (500K limit).

>:::image type="content" source="images/device-health-defender-antivirus-health-tab-export.png" alt-text="Shows the top-level export report button" lightbox="images/device-health-defender-antivirus-health-tab-export.png":::

- **Flyout level export** You can use the **Export** button within the flyouts to export a report to an Excel spreadsheet (100K limit).

Exported reports capture information based on your entry-point into the details report and which filters or customized columns you have set.

For information on exporting using API, see the following articles:

- [Export device antivirus health report](device-health-export-antivirus-health-report-api.md)
- [Export device antivirus health details API methods and properties](device-health-api-methods-properties.md)

> [!IMPORTANT]
>
> Currently, only the **Antivirus Health JSON Response** is generally available. **Antivirus Health API via files** is currently only available in public preview.
>
> **Advanced Hunting custom query** is currently only available in public preview, even if the queries are still visible.

### Microsoft Defender Antivirus version and update cards functionality

Following are descriptions for the six cards that report about the _version_ and _update_ information for Microsoft Defender Antivirus engine, security intelligence, and platform components:

#### Full report

In any of the three _version_ cards, select **View full report** to display the nine most recent Microsoft Defender Antivirus _version_ reports for each of the three device types: Windows, Mac, and Linux; if fewer than nine exist, they're all shown. An **Other** category captures recent antivirus engine versions ranking tenth and below, if detected.

>:::image type="content" source="images/device-health-defender-antivirus-health-view-full-report.png" alt-text="Shows the distribution of the top nine operating systems of each type" lightbox="images/device-health-defender-antivirus-health-view-full-report.png":::

A primary benefit of the three _version_ cards is that they provide quick indicators as to whether the most current versions of the antivirus engines, platforms, and security intelligence are being utilized. Coupled with the detailed information that is linked to the card, the versions cards become a powerful tool to check if versions are up to date and to gather information about individual computers, or groups of computers.
Ideally, when you run these reports, they'll indicate that the most current antivirus versions are installed, as opposed to older versions.
Use these reports to determine whether your organization is taking full advantage of the most current versions.

>:::image type="content" source="images/device-health-defender-antivirus-health-antivirus-details-up-to-date.png" alt-text="Shows Microsoft Defender Antivirus version details" lightbox="images/device-health-defender-antivirus-health-antivirus-details-up-to-date.png":::

To help ensure your anti-malware solution detects the latest threats, get updates automatically as part of Windows Update.

For more details on the current versions and how to update the different Microsoft Defender Antivirus components, visit [Microsoft Defender Antivirus platform support](manage-updates-baselines-microsoft-defender-antivirus.md).

### Card descriptions

Following are brief summaries of the collected information reported in each of the _Antivirus version_ cards:

#### Antivirus mode card

Reports on how many devices in your organization – on the date indicated on the card – are in any of the following Microsoft Defender Antivirus modes:

| value | mode |
|---|---|
| 0 | Active |
| 1 | Passive |
| 2 | Disabled (uninstalled, disabled, or SideBySidePassive {also known as Low Periodic Scan}) |
| 3 | Others (Not running, Unknown) |
| 4 | EDRBlocked |

>:::image type="content" source="images/device-health-defender-antivirus-health-antivirus-mode.png" alt-text="Shows filtering Microsoft Defender Antivirus modes" lightbox="images/device-health-defender-antivirus-health-antivirus-mode.png":::

Following are descriptions for each mode:

- **Active** mode - In active mode, Microsoft Defender Antivirus is used as the primary antivirus app on the device. Files are scanned, threats are remediated, and detected threats are listed in your organization's security reports and in your Windows Security app.
- **Passive** mode - In passive mode, Microsoft Defender Antivirus isn't used as the primary antivirus app on the device. Files are scanned, and detected threats are reported, but threats aren't remediated by Microsoft Defender Antivirus. IMPORTANT: Microsoft Defender Antivirus can run in passive mode only on endpoints that are onboarded to Microsoft Defender for Endpoint. See [Requirements for Microsoft Defender Antivirus to run in passive mode](microsoft-defender-antivirus-compatibility.md#requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode).
- **Disabled** mode  - synonymous with: uninstalled, disabled, sideBySidePassive, and Low Periodic Scan. When disabled, Microsoft Defender Antivirus isn't used. Files aren't scanned, and threats aren't remediated. In general, Microsoft doesn't recommend disabling or uninstalling Microsoft Defender Antivirus.
- **Others** mode - Not running, Unknown
- **EDR in Block** mode - In endpoint detection and response (EDR) blocked mode. See [Endpoint detection and response in block mode](edr-in-block-mode.md)

Devices that are in either passive, LPS, or Off present a potential security risk and should be investigated.

For details about LPS, see [Use limited periodic scanning in Microsoft Defender Antivirus](limited-periodic-scanning-microsoft-defender-antivirus.md).

#### Recent antivirus scan results card

This card has two bars graphs showing all-up results for quick scans and full scans. In both graphs, the first bar indicates the completion rate for scans, and indicate **Completed**, **Canceled**, or **Failed**. The second bar in each section provides the error codes for failed scans.
By scanning the **Mode** and **Recent scan results** columns, you can quickly identify devices that aren't in active antivirus scan mode, and devices that have failed or canceled recent antivirus scans. You can return to the report with this information and gather more details and security recommendations. If any error codes are reported in this card, there will be a link to learn more about error codes.

For more details on the current Microsoft Defender Antivirus versions and how to update the different Microsoft Defender Antivirus components, visit [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).

#### Antivirus engine version card

Shows the real-time results of the most current Microsoft Defender Antivirus engine versions installed across Windows Devices, Mac devices, and Linux devices in your organization. Microsoft Defender Antivirus engine is updated monthly.
For more information on the current versions and how to update the different Microsoft Defender Antivirus components, see [Microsoft Defender Antivirus platform support](manage-updates-baselines-microsoft-defender-antivirus.md).

#### Antivirus security intelligence version card

Lists the most common _Microsoft Defender Antivirus security intelligence_ versions installed on devices on your network.
Microsoft continually updates Microsoft Defender security intelligence to address the latest threats, and to refine detection logic. These refinements to security intelligence enhance Microsoft Defender Antivirus’ (and other Microsoft anti-malware solutions’) ability to accurately identify potential threats. This security intelligence works directly with cloud-based protection to deliver AI-enhanced, next-generation protection that is fast and powerful.

##### Antivirus platform version card

Shows the real-time results of the most current Microsoft Defender Antivirus platform versions installed across versions of Windows, Mac, and Linux devices in your organization. Microsoft Defender Antivirus platform is updated monthly.
For more information on the current versions and how to update the different Microsoft Defender Antivirus components, see [Microsoft Defender Antivirus platform support](manage-updates-baselines-microsoft-defender-antivirus.md)

#### Up-to-date cards

The up-to-date cards show the up-to-date status for **Antivirus engine**, **Antivirus platform**, and **Security intelligence** update versions. There are three possible states: _Up to date_ (‘True’), _out of date_ (‘False’), and _no data available_ (‘Unknown’).

Definitions for _up-to-date_, _out-of-date_, and _no_data_available_ are provided for each card below.

Microsoft Defender Antivirus (MDAV) makes up-to-date reports and determinations based on the following criteria:

- **For engine & platform updates**: the time client events were last received for up to date reports (“Signature Refresh time”) and Security Intelligence Publish Time (security intelligence VDMs are also used to determine engine & platform versions)
- **For security intelligence updates**: the time client events were last received for up to date reports (“Signature Refresh time”), Security Intelligence Publish Time, and the last up-to-date status communicated from client

For more information about the aforementioned terms, refer back to the section: [New Microsoft Defender Antivirus filter definitions](#new-microsoft-defender-antivirus-filter-definitions)

> [!NOTE]
>
> Up to date reporting **prerequisites**
>
> Up to date reporting generates information for devices that meet the following criteria:
>
> - Engine version: 1.1.19300.2+
> - Platform version: 4.18.2202.1+
> - Cloud protection enabled
> - Windows OS*
>
>*Currently up to date reporting is only available for windows devices. Cross platform devices such as Mac and Linux are listed under “no data available”
>

##### Up-to-date definitions

Following are up-to-date definitions for engine and platform:

| The engine/platform on the device is considered: | If: |
|:---|:---|
| **up-to-date** | the device communicated with the Defender report event (‘Signature refresh time’) within last 7 days and has a security intelligence publish time within last 7 days and the Engine or Platform version build time is within last 60 days. |
| **out-of-date** | the device communicated with the Defender report event (‘Signature refresh time’) within last 7 days and has a security intelligence publish time within last 7 but Engine or Platform version build time is older than 60 days. |
| **unknown (no data available)** | the device has not communicated with the report event (‘Signature refresh time’) for more than 7 days, or the security intelligence publish time is greater than 7 days. |

Following are up-to-date definitions for security intelligence:

| The security intelligence update is considered | If: |
|:---|:---|
|Up-to date | the security intelligence version on the device was written in the past 7 days and the device has communicated with the report event in past 7 days. |

For more information on these, see:

- [Antivirus engine updates card](#antivirus-engine-updates-card)
- [Security intelligence updates card](#security-intelligence-updates-card)
- [Antivirus platform updates card](#antivirus-platform-updates-card)

##### Antivirus engine updates card

This card identifies devices that have antivirus engine versions that are up to date versus out of date.

**The general definition of ‘_Up to date_’** - the engine version on the device is the most recent engine release (the Engine is _usually_ released monthly, via Windows Update (WU)). There's a three-day grace period from the day when Windows Update (WU) is released.

The following table lays out the possible values for up to date reports for **Antivirus Engine**. Reported Status is based on the last time reporting event was received, and security intelligence publish time.  

| Event’s Last Refresh Time (aka “Signature Refresh Time” in reports) | Security Intelligence Publish Time | _Reported Status_: |
|:----|:----|:----|
| < 7 days (new) | < 7 days (new) | _Up to date <br/> Out of date <br/> Unknown (whatever client reports)_ |
| > 7 days (old) | > 7 days (old) | _Unknown_ |
| < 7 days (new) | > 7 days (old) | _Unknown_ |
| > 7 days (old) | < 7 days (new) | _Unknown_ |

For information about Manage Microsoft Defender Antivirus update versions, see: [Monthly platform and engine versions](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

#### Antivirus platform updates card

This card identifies devices that have Antivirus platform versions that are up to date versus out of date.

**The general definition of ‘Up to date’** The platform version on the device is the most recent platform release (Platform is usually released monthly, via Windows Update). There's a three-day grace period from the day when WU is released.

The following table lays out the possible up to date report values for **Antivirus Platform**. Reported values are based on the last time reporting event was received, and security intelligence publish time.

| Event’s Last Refresh Time (aka “Signature Refresh Time” in reports) | Security Intelligence Publish Time | _Reported Status_: |
|:----|:----|:----|
| < 7 days (new) | < 7 days (new) | _Up to date <br/> Out of date <br/> Unknown (whatever client reports)_ |
| > 7 days (old) | > 7 days (old) | _Unknown_ |
| < 7 days (new) | > 7 days (old) | _Unknown_ |
| > 7 days (old) | < 7 days (new) | _Unknown_ |

For information about Manage Microsoft Defender Antivirus update versions, see: [Monthly platform and engine versions](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

##### Security intelligence updates card

This card identifies devices that have security intelligence versions that are up to date versus out of date.

**The general definition of ‘Up to date’** – the security intelligence version on the device was written in the past 7 days.

The following table lays out the possible up to date report values for **Security Intelligence** updates. Reported values are based on the last time reporting event was received, and security intelligence publish time.

| Event’s Last Refresh Time <br/> (aka “Signature Refresh Time” in reports) | Security Intelligence Publish Time | Last status received from client | _Reported Status_: |
|:----|:----|:----|:----|
| >7 days (old) | >7 days (old) | Up to date | _Unknown_ |
| <7 days (new) | >7 days (old) | Up to date | _Unknown_ |
| >7 days (old) | <7 days (new) | Up to date |  _Unknown_ |
| <7 days (new) | <7 days (new) | Unknown | _Unknown_|
| <7 days (new) | <7 days (new) | Up to date | _Up to date_ |
| >7 days (old) | <7 days (new) | Out of date | _Out of date_ |
| >7 days (old) | >7 days (old) | Out of date | _Out of date_ |
| <7 days (new) | >7 days (old) | Out of date | _Out of date_ |

## See also

- [Export device antivirus health details API methods and properties](device-health-api-methods-properties.md)
- [Export device antivirus health report](device-health-api-methods-properties.md)
- [Threat protection report](threat-protection-reports.md)

> [!TIP]
> For antivirus-related information for other platforms, see:
>
> - [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md)
> - [Microsoft Defender for Endpoint on Mac](microsoft-defender-endpoint-mac.md)
> - [macOS Antivirus policy settings for Microsoft Defender Antivirus for Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Set preferences for Microsoft Defender for Endpoint on Linux](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [Configure Defender for Endpoint on Android features](android-configure.md)
> - [Configure Microsoft Defender for Endpoint on iOS features](ios-configure-features.md)
