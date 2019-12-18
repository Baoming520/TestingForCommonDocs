# <a id="_Toc468453825"></a><a id="OLE_LINK11"></a><a id="OLE_LINK12"></a><a id="OLE_LINK30"></a><a id="OLE_LINK31"></a>__SQL Server Test Suite Common Deployment Guide__

Microsoft Corporation<a id="_Toc208205921"></a><a id="_Toc208205702"></a><a id="_Toc208137753"></a><a id="_Toc204576606"></a><a id="_Toc204053363"></a><a id="_Toc202286173"></a><a id="_Toc202285991"></a><a id="_Toc202285051"></a><a id="_Toc191231917"></a><a id="_Toc174967732"></a><a id="_Toc208222224"></a>

Published: 12 December 2019

# <a id="_Toc208039941"></a><a id="_Toc468453826"></a>__Abstract__

This document provides an overview and step\-by\-step graphical interpretation to setup the basic test environment for deploying protocol test suite\.

![](./md_doc_images/img_0.jpg)

[SQL Server Test Suite Common Deployment Guide	1](#_Toc468453825)

[Abstract	1](#_Toc468453826)

[1	Operation System Configuration	4](#_Toc468453827)

[1\.1	How to install Active Directory Domain Services on Windows 2012 R2	4](#_Toc468453828)

[1\.2	How to join a domain	21](#_Toc468453829)

[1\.3	How to Create a Domain User Account on DC	25](#_Toc468453830)

[1\.4	How to turn off Windows Firewall	27](#_Toc468453831)

[1\.5	How to install Powershell 2\.0	29](#_Toc468453832)

[1\.6	How to configure the PowerShell policy	31](#_Toc468453833)

[1\.7	How to configure Static IP Address	34](#_Toc468453834)

[1\.8	How to configure Windows Remote Management	39](#_Toc468453835)

[2	SQL Server Installation	40](#_Toc468453836)

[2\.1	How to install Microsoft SQL Server 2008 Enterprise SP1	40](#_Toc468453837)

[2\.2	How to install Microsoft SQL 2008 Enterprise R2	65](#_Toc468453838)

[2\.3	How to install SQL Server Denali CTP3	85](#_Toc468453839)

[2\.4	How to install Microsoft SQL Server 2012 RC0	106](#_Toc468453840)

[2\.5	How to install Microsoft SQL Server 2016 RC3	130](#_Toc468453841)

[3	SQL Server Configuration	151](#_Toc468453842)

[3\.1	Configure the MSSQLSERVER Properties	151](#_Toc468453843)

[4	Protocol Test Suite Tools Installation	155](#_Toc468453844)

[4\.1	How to install Visual Studio Team System 2008	155](#_Toc468453845)

[4\.2	How to Install Visual Studio	158](#_Toc468453846)

[4\.3	How to install \.NET Framework	165](#_Toc468453847)

[4\.4	How to install Microsoft Network Monitor 3\.4	172](#_Toc468453848)

[4\.5	How to Install Protocol Test Framework	179](#_Toc468453849)

[4\.6	How to Install Protocol Test Suites Library	182](#_Toc468453850)

[4\.7	How to Install Spec Explorer	184](#_Toc468453851)

[4\.8	How to replace Protocol Test Framework Reference Assemblies	186](#_Toc468453852)

[4\.9	How to install Microsoft SharePoint Server 2010 SP1 for Farm Installation	196](#_Toc468453853)

[4\.10	How to Install Message Analyzer	204](#_Toc468453854)

# <a id="_How_to_install_4"></a><a id="_How_to_install_8"></a><a id="_Toc468453827"></a><a id="_Toc199851846"></a><a id="_Toc202285078"></a><a id="_Toc204053386"></a><a id="_Toc205352703"></a><a id="_Toc208137788"></a><a id="_Toc208205715"></a><a id="_Toc208205934"></a><a id="_Toc208222243"></a><a id="_Toc221709628"></a>Operation System Configuration

The section lists some common configuration about the operation System\. 

## <a id="_Toc468453828"></a>How to install Active Directory Domain Services on Windows 2012 R2

1. Click __Add roles and features __of Dashboard on Server Manager\.

![](./md_doc_images/img_1.jpg)

1. Click __Next__\.

![](./md_doc_images/img_2.jpg)

1. Keep the default selection and click __Next__\.![](./md_doc_images/img_3.jpg)
2. Click __Next__\.

![](./md_doc_images/img_4.jpg)

1. Select Server roles __Active Directory Domain Services\.__

![](./md_doc_images/img_5.jpg)

1. Click __Add Features__\.![](./md_doc_images/img_6.jpg)
2. Click __Next__\.![](./md_doc_images/img_7.jpg)
3. Click __Next__\. ![](./md_doc_images/img_8.jpg)
4. Click __Next__\. ![](./md_doc_images/img_9.jpg)
5. Click __Install __to start the installation\. ![](./md_doc_images/img_10.jpg)
6. After installing finished, click the warning icon on the Server Manager Dashboard\. Then click __Promote the server to a domain Controller__\. ![](./md_doc_images/img_11.jpg)
7. Select __Add a new forest__, type the FQDN of the forest root domain name \(For example: __Contoso\.com__\)\. Click __Next__\. ![](./md_doc_images/img_12.jpg)
8. Type password \(For example: __Password01\!__\) and click __Next__\.![](./md_doc_images/img_13.jpg)
9. Click __Next __\(ignore the warning\)\.![](./md_doc_images/img_14.jpg)
10. Click __Next__\.![](./md_doc_images/img_15.jpg)
11. Use the default folders\. Click __Next__\.![](./md_doc_images/img_16.jpg)
12. Click __Next__\.![](./md_doc_images/img_17.jpg)
13. Click __Install__\.![](./md_doc_images/img_18.jpg)
14. Restart the computer after finished\.

## <a id="_Toc468453829"></a>How to join a domain

Below process uses the Windows 2008 R2 as an example, Windows 7 is the same steps\.

1. Type __Win\+X__, Click __Y__, open computer system information page\.

![](./md_doc_images/img_19.jpg)

1. Under __Computer name, domain, and workgroup settings__, click __Change settings__\.

![](./md_doc_images/img_20.jpg)

1. Click __Change…__\.

![](./md_doc_images/img_21.jpg)

1. Select __Domain__, type the domain name you want to join, click __OK__\.

![](./md_doc_images/img_22.jpg)

1. Type an existent domain user credential, click __OK__\.

![](./md_doc_images/img_23.jpg)

1. Click __OK__ and then restart computer to apply the change\.

![](./md_doc_images/img_24.jpg)

## <a id="_Toc295725368"></a><a id="_Toc468453830"></a>How to Create a Domain User Account on DC

1. Click__ Start__\->__Administrative Tools__\->__Active Directory User and Computers__ and then __new__ a user to contoso\.com\(Domain name depends on actual value\)

__![](./md_doc_images/img_25.jpg)__

1. __New__ the user name as “User\_name”  \(Note: Valid User logon name should be the name circled as below\)

![](./md_doc_images/img_26.jpg)

1. Click __next__ and then input the password as needed and Check __Password never expire__, click __OK__ when a new dialog is opened\.

![](./md_doc_images/img_27.jpg)

1. Click __Next__ and then click __Finish__ to complete\.

![](./md_doc_images/img_28.jpg)

## <a id="_Toc468453831"></a>How to turn off Windows Firewall

Below process uses the Windows 2008 R2 as an example, the same steps apply to Windows 7\.

1. Click __Start__ Menu, and click __Run\.\.\.__\.
2. Enter __firewall\.cpl__ in __Run__ dialog box and click __OK__ to open the __Windows Firewall __window\.

![](./md_doc_images/img_29.jpg)

1. Click __Turn Windows firewall on or off__\.

![](./md_doc_images/img_30.jpg)

1. Please select __Turn off Windows Firewall \(not recommended\)__, then click__ OK__\.

![](./md_doc_images/img_31.jpg)<a id="_How_to_join"></a><a id="_4.2_How_to"></a>

## <a id="_Toc295725373"></a><a id="_Toc468453832"></a>How to install Powershell 2\.0

1. Double click __PowerShell\_Setup\.msi__\.
2. Click __Next__\.

![](./md_doc_images/img_32.jpg)

1. Please read the following license agreement carefully, if you accept the license agreement, please choose __I accept the terms in the license agreement__, and then click __Next__\. \(If you select __I do not accept the terms in the license agreement__, Windows PowerShell Setup Wizard will be ended and you will not able to install it successfully\.\)

![](./md_doc_images/img_33.jpg)

1. Click __Install__\.

![](./md_doc_images/img_34.jpg)

1. Click __Finish__\.

![](./md_doc_images/img_35.jpg)

__Notice:__

- On Windows Server 2008, install a package \(KB968930\) after complete Power Shell installation\.
- Get the package from:
- Windows6\.0\-KB968930\-x86\.msu for 32\-bit Operating System

[http://www\.microsoft\.com/downloads/details\.aspx?FamilyId=863e7d01\-fb1b\-4d3e\-b07d\-766a0a2def0b&displaylang=en](http://www.microsoft.com/downloads/details.aspx?FamilyId=863e7d01-fb1b-4d3e-b07d-766a0a2def0b&displaylang=en)

- Windows6\.0\-KB968930\-x64\.msu for 64\-bit Operating System

[http://www\.microsoft\.com/downloads/details\.aspx?familyid=D37E25CF\-DB05\-4B23\-A852\-CDF865D81B82&displaylang=en](http://www.microsoft.com/downloads/details.aspx?familyid=D37E25CF-DB05-4B23-A852-CDF865D81B82&displaylang=en) 

-  After you install this item, you may have to restart your computer\.

## <a id="_Toc468453833"></a>How to <a id="_Hlk499816636"></a>configure the PowerShell policy

1. Click __Start__\->__All Programs__\.

__![](./md_doc_images/img_36.jpg)__

1. Click __Accessories__\->__Windows PowerShell__\.

__![](./md_doc_images/img_37.jpg)__

1. Right\-click __Windows PowerShell \(x86\) __console, click __Run as administrator__\. 

__NOTE: __If server machine is x64, choose __Windows PowerShell \(x86\) __console\.

__![](./md_doc_images/img_38.jpg)__

1. Type two commands in __Windows PowerShell \(x86\)__ console:
2. __Set\-ExecutionPolicy RemoteSigned__
3. __Enable\-PSRemoting__

![](./md_doc_images/img_39.jpg)

1. Follow above steps to configure the __Windows PowerShell__ console__\.__
2. Type the command in __Windows PowerShell \(x86\)__ console:
3. __Set\-Item WSMan:\\localhost\\Shell\\MaxMemoryPerShellMB 500__

![](./md_doc_images/img_40.jpg)

1. Follow above step to increase the __default allocated memory for Windows PowerShell __to__ 500M\.__

## <a id="_Toc468453834"></a>How to configure Static IP Address

1. Click __Start__, and then click __Control Panel__\. 
2. In __Control Panel__, verify that __Small icons__ is selected, and then click __Network and Sharing Center__\.

![](./md_doc_images/img_41.jpg)

1. In __Network and Sharing Center,__ click __Local Area Connections__\.

![](./md_doc_images/img_42.jpg)

1. In __Local Area Connections Status__, click __Properties__\.

![](./md_doc_images/img_43.jpg)

1. In __Local Area Connection Properties__, in __This connection uses the following items__, select __Internet Protocol Version 4 \(TCP/IPv4\)__, and then click __Properties__\. The __Internet Protocol Version 4 \(TCP/IPv4\) Properties__ dialog box opens\.

![](./md_doc_images/img_44.jpg)

1. In __Internet Protocol Version 4 \(TCP/IPv4\) Properties__, on the __General__ tab, click __Use the following IP address__\. In __IP address__, type the IP address that you want to use\. Press tab to place the cursor in __Subnet mask__\. A default value for subnet mask is entered automatically\. Either accept the default subnet mask, or type the subnet mask that you want to use\. In __Default gateway__, type the IP address of your default gateway\. In __Preferred DNS server__, type the IP address of your DNS server\. If you plan to use the local computer as the preferred DNS server, type the IP address of the local computer\. In __Alternate DNS Server__, type the IP address of your alternate DNS server, if any\. If you plan to use the local computer as an alternate DNS server, type the IP address of the local computer\. Click __OK__, and then click __Close__\.

![](./md_doc_images/img_45.jpg)

1. Back to __step 5__, In __Local Area Connection Properties__, select __Internet Protocol Version 6 \(TCP/IPv6\)__, and then click __Properties__\. The __Internet Protocol Version 6 \(TCP/IPv6\)__ __Properties__ dialog box opens\.
2. In __Internet Protocol Version 6 \(TCP/IPv6\) Properties__, on the __General__ tab, click __Use the following IPv6 address__\. In __IPv6 address__, type the IPv6 address that you want to use\. Press tab to place the cursor in __Subnet prefix length__\. A default value for subnet mask is entered automatically\. Either accept the default subnet prefix length, or type the prefix length that you want to use\. In __Default gateway__, type the IP address of your default gateway\. In __Preferred DNS server__, type the IP address of your DNS server\. If you plan to use the local computer as the preferred DNS server, type the IP address of the local computer\. In __Alternate DNS Server__, type the IP address of your alternate DNS server, if any\. If you plan to use the local computer as an alternate DNS server, type the IP address of the local computer\. Click __OK__, and then click __Close__\.

![](./md_doc_images/img_46.jpg)

## <a id="_Toc295725374"></a><a id="_Toc468453835"></a>How to configure Windows Remote Management

1. Click __Start\->Accessories\-> Command Prompt__\.
2. Type command: __winrm quickconfig\.__

![](./md_doc_images/img_47.jpg)

1. Then type __Y\.__

![](./md_doc_images/img_48.jpg)

<a id="_How_to_install_1"></a><a id="_How_to_install"></a>

# <a id="_Toc468453836"></a>SQL Server Installation

The section lists four installation methods against four SQL Servers on Windows 2008 R2, please click the below hyperlinks to see the detailed subsection\.

__Products__

__Operating System__

__Installation Type__

Microsoft SQL Server 2008 Enterprise SP1

Windows Server 2008 Enterprise R2 x64

[Basic Installation](#_How_to_install_13)

Microsoft SQL Server 2008  Enterprise R2

Windows Server 2008 Enterprise R2 x64

[Basic Installation](#_How_to_install_14)

Microsoft SQL Server Denali CTP3

Windows Server 2008 Enterprise R2 x64

[Basic Installation](#_How_to_install_15)

## <a id="_How_to_install_7"></a><a id="_How_to_install_10"></a><a id="_How_to_install_11"></a><a id="_How_to_install_12"></a><a id="_How_to_install_13"></a><a id="_Toc281571835"></a><a id="_Toc468453837"></a>How to install Microsoft SQL Server 2008 Enterprise SP1

### Install \.NET Framework 3\.5\.1 

1. Go to __Start__\->__All Programs__\->__Administrative Tools__\->__Server Manager__\->__Features__\->__Add Features__\.

![](./md_doc_images/img_49.jpg)

1. Select __\.NET Framework 3\.5\.1__ __Features__ dialog box\.

![](./md_doc_images/img_50.jpg)

1. Click __Add Required Roles Services __in pop\-up window\.

![](./md_doc_images/img_51.jpg)

1. Click __Next __in __Add Features Wizard__ dialog box\.

![](./md_doc_images/img_52.jpg)

1. Click __Next__\.

![](./md_doc_images/img_53.jpg)

1. Click __Next\.__

![](./md_doc_images/img_54.jpg)

1. Click __Install\.__

![](./md_doc_images/img_55.jpg)

1. Click __Close __to finish installation\.

![](./md_doc_images/img_56.jpg)

### Install Web Server \(IIS7\.0\) role

1. Click __Start__\->__Administrative Tools__\->__Server Manager__\->__Roles__\->__Add Roles__, select __Web Server \(IIS\) __in __Select Server Roles __dialog box, Click __Next__\.

![](./md_doc_images/img_57.jpg)

1. Click __Next__\.

![](./md_doc_images/img_58.jpg)

1. Select __Web Server \(IIS\)__\.

![](./md_doc_images/img_59.jpg)

1. Click __Next __in __Web Server \(IIS\)__ dialog box\.

![](./md_doc_images/img_60.jpg)

1. Select __all components __in __Select__ __Role Services __dialog box, click __Next\.__![](./md_doc_images/img_61.jpg)
2. Click __Install\.__

![](./md_doc_images/img_62.jpg)

1. Click __Close __to finish installation\.![](./md_doc_images/img_63.jpg)

### Install Microsoft SQL Server 2008 Enterprise

__Note__: There are two patches for Microsoft SQL Server 2008: SQLServer2008SP1\-KB968369\-x64\-ENU and SQLServer2008\-KB970315\-x64\.

1. Double click __setup\.exe __to start installation\.
2. Click __Installation\-> New SQL Server stand\-alone installation or add features to an existing installation__\.

![](./md_doc_images/img_64.jpg)

1. Click __OK__ in the __Setup Support Rules__ dialog box\.

![](./md_doc_images/img_65.jpg)

1. Enter the __Product Key__ and click __Next__ in the __Product Key__ dialog box\.

![](./md_doc_images/img_66.jpg)

1. Choose __I accept the license terms__ and click __Next __in the__ License Terms __dialog box\.

![](./md_doc_images/img_67.jpg)

1. Click __Install __in the__ Setup Support Files __dialog box\.

![](./md_doc_images/img_68.jpg)

1. Click __Next __in the__ Setup Support Roles __dialog box__\.__

![](./md_doc_images/img_69.jpg)

1. Click __Select All__ button, and click __next __in the __Feature Selection __dialog box\.

![](./md_doc_images/img_70.jpg)

1. Click __Next__ in the __Instance Configuration__ dialog box\.

![](./md_doc_images/img_71.jpg)

1. Click __Next__ in the __Disk Space Requirements__ dialog box\.

![](./md_doc_images/img_72.jpg)

1. Type __Account Name__ and __Password__ and click Next\.

![](./md_doc_images/img_73.jpg)

1. Select Mixed Mode \(SQL Server authentication and Windows authentication\), type password\. Click Add Current User and click Next\.

![](./md_doc_images/img_74.jpg)

1. Click Add Current User and click Next\.

![](./md_doc_images/img_75.jpg)

1. Click __Next__ in the __Reporting Services Configuration__ dialog box\.

![](./md_doc_images/img_76.jpg)

1. Click __Next__ in the __Error and Usage Reporting__ dialog box\.

![](./md_doc_images/img_77.jpg)

1. Click __Next__ in the __Installation Rules__ dialog box\.

![](./md_doc_images/img_78.jpg)

1. Click __Install__ in the __Ready to Install__ dialog box\.

![](./md_doc_images/img_79.jpg)

1. Click __Next__ in the __Installation Progress__ dialog box\.

![](./md_doc_images/img_80.jpg)

1. Click __Close__ in the __Complete__ dialog box\.

![](./md_doc_images/img_81.jpg)

### <a id="_Toc281571837"></a>How to install Microsoft SQL Server 2008 Enterprise sp1

1. Click __Setup__ to install SQL Server 2008 Service Pack1

![](./md_doc_images/img_82.jpg)

1. Select __I accept the license terms__ and click __Next__\.

![](./md_doc_images/img_83.jpg)

1. __Select All__ and click __Next__\.

![](./md_doc_images/img_84.jpg)

1. Click __Next __in__ __the__ Check Files In Use __page\.

![](./md_doc_images/img_85.jpg)

1. Click __Update__\.

![](./md_doc_images/img_86.jpg)

1. Click Next\.

![](./md_doc_images/img_87.jpg)

1. Click __Close__\.

![](./md_doc_images/img_88.jpg)

### <a id="_Toc281571838"></a>How to Install the Update for SQL Server 2008 Enterprise

1. Click __setup__ to install the update for SQL Server 2008\.

![](./md_doc_images/img_89.jpg)

1. Select __I accept the license terms__ and click __Next__\.

![](./md_doc_images/img_90.jpg)

1. __Select All__ and click __Next__\.

![](./md_doc_images/img_91.jpg)

1. Click __Next__\.

![](./md_doc_images/img_92.jpg)

1. Click __Update__\.

![](./md_doc_images/img_93.jpg)

1. Click Next\.

![](./md_doc_images/img_94.jpg)

1. Click __Close__

![](./md_doc_images/img_95.jpg)

## <a id="_How_to_install_14"></a><a id="_Toc468453838"></a>How to install Microsoft SQL 2008 Enterprise R2

### Install Web Server \(IIS7\.0\) role

1. Click __Start__\->__Administrative Tools__\->__Server Manager__\->__Roles__\->__Add Roles__, select __Web Server \(IIS\) __in __Select Server Roles __dialog box, Click __Next__\.

![](./md_doc_images/img_96.jpg)

1. Click __Next__\.

![](./md_doc_images/img_97.jpg)

1. Select __Web Server \(IIS\)__\.

![](./md_doc_images/img_98.jpg)

1. Click __Next __in __Web Server \(IIS\)__ dialog box\.

![](./md_doc_images/img_99.jpg)

1. Select __all components __in __Select__ __Role Services __dialog box, click __Next\.__![](./md_doc_images/img_100.jpg)
2. Click __Install\.__

![](./md_doc_images/img_101.jpg)

1. Click __Close __to finish installation\.![](./md_doc_images/img_102.jpg)

### Install \.NET Framework 3\.5\.1 

1. Go to __Start__\->__All Programs__\->__Administrative Tools__\->__Server Manager__\->__Features__\->__Add Features__\.

![](./md_doc_images/img_103.jpg)

1. Select __\.NET Framework 3\.5\.1__ __Features__ dialog box\.

![](./md_doc_images/img_104.jpg)

1. Click __Add Required Roles Services __in pop\-up window\.

![](./md_doc_images/img_105.jpg)

1. Click __Next __in __Add Features Wizard__ dialog box\.

![](./md_doc_images/img_106.jpg)

1. Click __Next__\.

![](./md_doc_images/img_107.jpg)

1. Click __Next\.__

![](./md_doc_images/img_108.jpg)

1. Click __Install\.__

![](./md_doc_images/img_109.jpg)

1. Click __Close __to finish installation\.

![](./md_doc_images/img_110.jpg)

### <a id="_Toc279169097"></a>Install Microsoft SQL Server 2008 R2

1. Double click __setup\.exe __to start installation\.
2. Click the __Installation__ in the left panel, and then click __New installation or add features to an existing installation__ in the right panel\.

![](./md_doc_images/img_111.jpg)

1. Click __OK__\.

![](./md_doc_images/img_112.jpg)

1. Click __Install__ to install the Setup Support Files\.

![](./md_doc_images/img_113.jpg)

1. Check if there is rule failed\. If yes, repro the sections before; if not, click __Next__\.

![](./md_doc_images/img_114.jpg)

1. Select __Specify a free edition__ and click __Next__\.

![](./md_doc_images/img_115.jpg)

1. Check the license terms and select __I accept the license terms__ and click __Next__\.

![](./md_doc_images/img_116.jpg)

1. Select __SQL Server Feature Installation__, and click __Next__\.

![](./md_doc_images/img_117.jpg)

1. Click __Select All__ and click __Next__\.

![](./md_doc_images/img_118.jpg)

1. Click __Next\.__

![](./md_doc_images/img_119.jpg)

1. Click __Next __for the __Instance Configuration__\.

![](./md_doc_images/img_120.jpg)

1. Click __Next__ for the __Desk Space Requirements__\.

![](./md_doc_images/img_121.jpg)

1. For __workgroup__ environment type __administrator__ as account name and __Password01\!__ as password and click __Next__\.

![](./md_doc_images/img_122.jpg)

For __domain__ environment type __contoso\\administrator__ as account name and __Password01\!__ as password and click __Next__\.

![](./md_doc_images/img_123.jpg)

1. Select __Mixed Mode \(SQL Server authentication and windows authentication\)__, type in __Password01\!__ in __Enter password__ and __Confirm password__, click __Add Current User__ and then click __Next__\.

![](./md_doc_images/img_124.jpg)

1. Click __Add Current User__ and click __Next__\.

![](./md_doc_images/img_125.jpg)

1. Select __Install the native mode default configuration__ or __Install the SharePoint integrated mode default configuration__ according to the test environment in __Reporting Services Configuration__ page and click __Next__\.

![](./md_doc_images/img_126.jpg)

1. Click __Next__\.

![](./md_doc_images/img_127.jpg)

1. Click __Next__\.

![](./md_doc_images/img_128.jpg)

1. Click __Install__ to finish the installation\.

![](./md_doc_images/img_129.jpg)

## <a id="_How_to_install_15"></a><a id="_Toc468453839"></a>How to install SQL Server Denali CTP3

### Install Web Server \(IIS7\.0\) role

1. Click __Start__\->__Administrative Tools__\->__Server Manager__\->__Roles__\->__Add Roles__, select __Web Server \(IIS\) __in __Select Server Roles __dialog box, Click __Next__\.

![](./md_doc_images/img_130.jpg)

1. Click __Next__\.

![](./md_doc_images/img_131.jpg)

1. Select __Web Server \(IIS\)__\.

![](./md_doc_images/img_132.jpg)

1. Click __Next __in __Web Server \(IIS\)__ dialog box\.

![](./md_doc_images/img_133.jpg)

1. Select __all components __in __Select__ __Role Services __dialog box, click __Next\.__![](./md_doc_images/img_134.jpg)
2. Click __Install\.__

![](./md_doc_images/img_135.jpg)

1. Click __Close __to finish installation\.![](./md_doc_images/img_136.jpg)

### Install \.NET Framework 3\.5\.1 

1. Go to __Start__\->__All Programs__\->__Administrative Tools__\->__Server Manager__\->__Features__\->__Add Features__\.

![](./md_doc_images/img_137.jpg)

1. Select __\.NET Framework 3\.5\.1__ __Features__ dialog box\.

![](./md_doc_images/img_138.jpg)

1. Click __Add Required Roles Services __in pop\-up window\.

![](./md_doc_images/img_139.jpg)

1. Click __Next __in __Add Features Wizard__ dialog box\.

![](./md_doc_images/img_140.jpg)

1. Click __Next__\.

![](./md_doc_images/img_141.jpg)

1. Click __Next\.__

![](./md_doc_images/img_142.jpg)

1. Click __Install\.__

![](./md_doc_images/img_143.jpg)

1. Click __Close __to finish installation\.

![](./md_doc_images/img_144.jpg)

### Install SQL Server Denali CTP3

1. Double click __setup\.exe __to start installation\.
2. Click __Installation\-> New SQL Server stand\-alone installation or add features to an existing installation__\.

![](./md_doc_images/img_145.jpg)

1. Click __OK__ in the __Setup Support Rules__ dialog box\.

![](./md_doc_images/img_146.jpg)

1. Click __Next__ in the __Product Key__ dialog box\.

![](./md_doc_images/img_147.jpg)

1. Choose __I accept the license terms__ and click __Next __in the__ License Terms __dialog box\.

![](./md_doc_images/img_148.jpg)

1. Click __Next __in the__ Product Updates __dialog box\.

![](./md_doc_images/img_149.jpg)

1. Wait some minute when __SQL Server Setup files are being installed on the system\.__

![](./md_doc_images/img_150.jpg)

1. Click __Next __in the__ Setup Support Rules __dialog box__\.__

![](./md_doc_images/img_151.jpg)

1. Click __Next __in the__ Setup Role __dialog box__\.__

![](./md_doc_images/img_152.jpg)

1. Click __Select All__ button, and click __next __in the __Feature Selection __dialog box\. Also you can only select the features which you want to install\.

![](./md_doc_images/img_153.jpg)

1. Click __Next__ in the __Installation Rules__ dialog box\.

![](./md_doc_images/img_154.jpg)

1. Click __Next__ in the __Instance Configuration__ dialog box\.

![](./md_doc_images/img_155.jpg)

1. Click __Next__ in the __Disk Space Requirements__ dialog box\.

![](./md_doc_images/img_156.jpg)

1. For __workgroup__ environment type __administrator__ as account name and its password then click __Next__\.

![](./md_doc_images/img_157.jpg)

For __domain__ environment type __contoso\\administrator__ as account name its password and click __Next__\.

![](./md_doc_images/img_158.jpg)

1. Select __Mixed Mode \(SQL Server authentication and windows authentication\)__, type in password in __Enter password__ and __Confirm password__, click __Add Current User__ and then click __Next __in the __Database Engine Configuration __dialog box

![](./md_doc_images/img_159.jpg)

1. Click __Add Current User__, and click __Nex__t in the __Analysis Services Configuration__ dialog box\.

![](./md_doc_images/img_160.jpg)

1. Click __Next__ in the __Reporting Services Configuration__ dialog box\.

![](./md_doc_images/img_161.jpg)

1. Click __Add Current User__, and click __Nex__t in the __Distributed Replay Controller__ dialog box\.

![](./md_doc_images/img_162.jpg)

1. Type a Controller Name and click __Nex__t in the __Distributed Replay Client__ dialog box\.

![](./md_doc_images/img_163.jpg)

1. Click __Next__ in the __Error Reporting__ dialog box\.

![](./md_doc_images/img_164.jpg)

1. Click __Next__ in the __Installation Configuration Rules__ dialog box\.

![](./md_doc_images/img_165.jpg)

1. Click __Install__ in the __Ready to Install__ dialog box\.

![](./md_doc_images/img_166.jpg)

1. Click __Close__ in the __Complete__ dialog box\.

![](./md_doc_images/img_167.jpg)

## <a id="_Toc468453840"></a>How to install Microsoft SQL Server 2012 RC0

### Install Web Server \(IIS7\.0\) role

1. Click __Start__\->__Administrative Tools__\->__Server Manager__\->__Roles__\->__Add Roles__; select __Web Server \(IIS\) __in __Select Server Roles __dialog box, Click __Next__\.

![](./md_doc_images/img_168.jpg)

1. Click __Next__\.

![](./md_doc_images/img_169.jpg)

1. Select __Web Server \(IIS\)__\.

![](./md_doc_images/img_170.jpg)

1. Click __Next __in __Web Server \(IIS\)__ dialog box\.

![](./md_doc_images/img_171.jpg)

1. Select __all components __in __Select__ __Role Services __dialog box, click __Next\.__![](./md_doc_images/img_172.jpg)
2. Click __Install\.__

![](./md_doc_images/img_173.jpg)

1. Click __Close __to finish installation\.![](./md_doc_images/img_174.jpg)

### Install \.NET Framework 3\.5\.1 

1. Go to __Start__\->__All Programs__\->__Administrative Tools__\->__Server Manager__\->__Features__\->__Add Features__\.

![](./md_doc_images/img_175.jpg)

1. Select __\.NET Framework 3\.5\.1__ __Features__ dialog box\.

![](./md_doc_images/img_176.jpg)

1. Click __Add Required Roles Services __in pop\-up window\.

![](./md_doc_images/img_177.jpg)

1. Click __Next __in __Add Features Wizard__ dialog box\.

![](./md_doc_images/img_178.jpg)

1. Click __Next__\.

![](./md_doc_images/img_179.jpg)

1. Click __Next\.__

![](./md_doc_images/img_180.jpg)

1. Click __Install\.__

![](./md_doc_images/img_181.jpg)

1. Click __Close __to finish installation\.

![](./md_doc_images/img_182.jpg)

### Install Microsoft SQL Server 2012 RC0

1. Double click __setup\.exe __to start installation\.
2. Click __Installation\-> New SQL Server stand\-alone installation or add features to an existing installation__\.

![](./md_doc_images/img_183.jpg)

1. Click __OK__ in the __Setup Support Rules__ dialog box\.

![](./md_doc_images/img_184.jpg)

1. Unselect __Include SQL Server Product updates__ and click __Next __in the__ Product Updates __dialog box\.

![](./md_doc_images/img_185.jpg)

1. Wait some minute when __SQL Server Setup files are being installed on the system\.__

![](./md_doc_images/img_186.jpg)

1. Click __Next __in the__ Setup Support Rules __dialog box\.

![](./md_doc_images/img_187.jpg)

1. Select __Specify a free edition__ and click __Next__ in the __Product Key__ dialog box\.

![](./md_doc_images/img_188.jpg)

1. Choose __I accept the license terms__ and click __Next __in the__ License Terms __dialog box\.

![](./md_doc_images/img_189.jpg)

1. Choose __SQL Server Feature Installation__ as default, click __Next __in the__ Setup Role __dialog box__\.__

![](./md_doc_images/img_190.jpg)

1. Click __Select All__ button, and click __next __in the __Feature Selection __dialog box\. Also you can only select the features which you want to install\.

![](./md_doc_images/img_191.jpg)

1. Click __Next__ in the __Installation Rules__ dialog box\.

![](./md_doc_images/img_192.jpg)

1. Click __Next__ in the __Instance Configuration__ dialog box\.

![](./md_doc_images/img_193.jpg)

1. Click __Next__ in the __Disk Space Requirements__ dialog box\.

![](./md_doc_images/img_194.jpg)

1. For __workgroup__ environment type __administrator__ as account name and its password then click __Next__\.

![](./md_doc_images/img_195.jpg)

For __domain__ environment type __contoso\\administrator__ as account name its password and click __Next__\.

![](./md_doc_images/img_196.jpg)

1. Select __Mixed Mode \(SQL Server authentication and windows authentication\)__, type in password in __Enter password__ and __Confirm password__, click __Add Current User__ and then click __Next __in the __Database Engine Configuration __dialog box\.

![](./md_doc_images/img_197.jpg)

1. Click __Add Current User__, and click __Nex__t in the __Analysis Services Configuration__ dialog box\.

![](./md_doc_images/img_198.jpg)

1. Click __Next__ in the __Reporting Services Configuration__ dialog box\.

![](./md_doc_images/img_199.jpg)

1. Click __Add Current User__, and click __Nex__t in the __Distributed Replay Controller__ dialog box\.

![](./md_doc_images/img_200.jpg)

1. Type a Controller Name and click __Nex__t in the __Distributed Replay Client__ dialog box\.

![](./md_doc_images/img_201.jpg)

1. Click __Next__ in the __Error Reporting__ dialog box\.

![](./md_doc_images/img_202.jpg)

1. Click __Next__ in the __Installation Configuration Rules__ dialog box\.

![](./md_doc_images/img_203.jpg)

1. Click __Install__ in the __Ready to Install__ dialog box\.

![](./md_doc_images/img_204.jpg)

1. Click __Close__ in the __Complete__ dialog box\.

![](./md_doc_images/img_205.jpg)

1. Click __OK__ and restart the computer to complete the installation\. 

![](./md_doc_images/img_206.jpg)

## <a id="_Toc468453841"></a>How to install Microsoft SQL Server 2016 RC3

### Install \.NET Framework4\.6\.1

1. Double click __NDP461\-DevPack\-KB3105179\-ENU\.exe__, select the check box, Click __Install\.__ ![](./md_doc_images/img_207.jpg)
2. Click __Restart __after__ __setup successfully\. ![](./md_doc_images/img_208.jpg)

### Install Microsoft SQL Server 2016 RC3 

#### Preinstall for Microsoft SQL Server 2016 RC3

1. Preinstall [KB316398](D:\\Git Source\\MS-SSAS-T\\Docs\\Internal\\httpssupport.microsoft.comen-uskb3138367)\. Double click __vcredist\_x64\.exe__, select the check box and click __install__\.![](./md_doc_images/img_209.jpg)
2. Click __Close__\. 

![](./md_doc_images/img_210.jpg)

#### Install Microsoft SQL Server 2016 RC3

1. Double click __setup\.exe __to start installation\.
2. Click __Installation\-> New SQL Server stand\-alone installation or add features to an existing installation__\.

![](./md_doc_images/img_211.jpg)

1. Click __Next__\.

![](./md_doc_images/img_212.jpg)

1. Wait a few minutes and make sure all rules check passed, Click __Next__\.

![](./md_doc_images/img_213.jpg)

1. Select __Evaluation __edition, apply your product key at [MsKeys](https://mskeys.microsoft.com/) , then enter your key\. Click __Next__\.![](./md_doc_images/img_214.jpg) 
2. Select the check, click __Next__\.![](./md_doc_images/img_215.jpg) 
3. Click __Select All__, except for __PolyBase Query Service for External Data__\. Click __Next__\.![](./md_doc_images/img_216.jpg)
4. Keep default value, click __Next__\.![](./md_doc_images/img_217.jpg)
5. Type the domain administrator user’s name and password \(For example: __contoso\\administrator__, __Password01\!__\)\. Wait a few minutes and make sure all rules check passed, Click __Next__

![](./md_doc_images/img_218.jpg)

1. Select __Mixed__ __Mode__ type password for __sa__ \(For example: __Password01\!__\), Click __Next__\.

![](./md_doc_images/img_219.jpg) 

1. Select __Multidimensional and data Mining Mode,__ click __Add Current User__, then click __Next__\.

![](./md_doc_images/img_220.jpg)

1. Click __Next__\.

![](./md_doc_images/img_221.jpg)

1. Click __Add Current User__, then click Next\. ![](./md_doc_images/img_222.jpg)
2. Type Controller Name \(For example: __Controller01__\), then click __Next__\.

![](./md_doc_images/img_223.jpg)

1. Click __Accept__ button, then click __Next__\.![](./md_doc_images/img_224.jpg) 
2. Click __Install__\.![](./md_doc_images/img_225.jpg) 
3. Wait until install complete and succeeded\. Click __Close__\.![](./md_doc_images/img_226.jpg)

#### Install SQL Server Management Studio

1. Click __Install SQL Server Management Tools__ on SQL Server Installation Center\. Download __SSMS\-Setup\-ENU\.exe__\.![](./md_doc_images/img_227.jpg)
2. Double click __SSMS\-Setup\-ENU\.exe__ to start installation, click __Install__\.![](./md_doc_images/img_228.jpg)
3. Click __Close__

![](./md_doc_images/img_229.jpg)

## How to install Microsoft SQL Server 2017 Standard RTM Retail

### Install \.NET Framework4\.6\.1

1. Double click __NDP461\-DevPack\-KB3105179\-ENU\.exe__, select the check box, Click __Install\.__ ![](./md_doc_images/img_230.jpg)
2. Click __Restart __after__ __setup successfully\. ![](./md_doc_images/img_231.jpg)

### Install Microsoft SQL Server 2017 Standard RTM Retail 

#### Preinstall for Microsoft SQL Server 2017 Standard RTM Retail

1. Preinstall [KB316398](D:\\Git Source\\MS-SSAS-T\\Docs\\Internal\\httpssupport.microsoft.comen-uskb3138367)\. Double click __vcredist\_x64\.exe__, select the check box and click __install__\.![](./md_doc_images/img_232.jpg)
2. Click __Close__\. 

![](./md_doc_images/img_233.jpg)

#### Install Microsoft SQL Server 2017 Standard RTM Retail

1. Double click __setup\.exe __to start installation\.
2. Click __Installation\-> New SQL Server stand\-alone installation or add features to an existing installation__\.

![](./md_doc_images/img_234.jpg)

1. Click __Next__\. 
2. Select __Evaluation __edition, apply your product key at [MsKeys](https://mskeys.microsoft.com/) , then enter your key\. Click __Next__\. ![](./md_doc_images/img_235.jpg) 
3. Select the check, click __Next__\. ![](./md_doc_images/img_236.jpg) 
4. Select the check, click __Next__\.

![](./md_doc_images/img_237.jpg)

1. Wait a few minutes and make sure all rules check passed, Click __Next__\.

![](./md_doc_images/img_238.jpg)

1. Click __Select All__, except for __PolyBase Query Service for External Data__\. Click __Next__\. ![](./md_doc_images/img_239.jpg)
2. Keep default value, click __Next__\. ![](./md_doc_images/img_240.jpg)
3. Type the domain administrator user’s name and password \(For example: __contoso\\administrator__, __Password01\!__\)\. Wait a few minutes and make sure all rules check passed, Click __Next__

![](./md_doc_images/img_241.jpg)

1. Select __Mixed__ __Mode__ type password for __sa__ \(For example: __Password01\!__\), Click __Next__\.

![](./md_doc_images/img_242.jpg) 

1. Select __Multidimensional and data Mining Mode,__ click __Add Current User__, then click __Next__\.

![](./md_doc_images/img_243.jpg)

1. Click __Next__\.

![](./md_doc_images/img_244.jpg)

1. Click __Add Current User__, then click Next\. ![](./md_doc_images/img_245.jpg)
2. Type Controller Name \(For example: __Controller01__\), then click __Next__\.

![](./md_doc_images/img_246.jpg)

1. Click __Accept__ button, then click __Next__\. ![](./md_doc_images/img_247.jpg) 
2. Click __Accept__ button, then click __Next__\. 

![](./md_doc_images/img_248.jpg)

1. Click __Install__\. ![](./md_doc_images/img_249.jpg) 
2. Wait until install complete and succeeded\. Click __Close__\. ![](./md_doc_images/img_250.jpg)

#### Install SQL Server Management Studio

1. Click __Install SQL Server Management Tools__ on SQL Server Installation Center\. Download __SSMS\-Setup\-ENU\.exe__\. ![](./md_doc_images/img_251.jpg)
2. Double click __SSMS\-Setup\-ENU\.exe__ to start installation, click __Install__\. ![](./md_doc_images/img_252.jpg)
3. Click __Close__

![](./md_doc_images/img_253.jpg)

## How to install Microsoft SQL Server 2019 GA

### Install Microsoft SQL Server 2019 GA

1. Double click setup\.exe to start installation\.
2. Click __Installation __\-> __New SQL Server stand\-alone installation or add features to an existing installation__\.

![](./md_doc_images/img_254.jpg)

1. Select Evaluation edition, or apply your product key at [MsKeys](https://mskeys.microsoft.com/), then enter your key\. Click __Next__\.

![](./md_doc_images/img_255.jpg)1. Select the check, click __Next__\.

![](./md_doc_images/img_256.jpg)1. Wait a few minutes and make sure all rules check passed, Click __Next__\.

![](./md_doc_images/img_257.jpg)1. Click __Select All__, except for __PolyBase Query Service for External Data__\. Click __Next__\.

![](./md_doc_images/img_258.jpg)1. Keep default value, click __Next__\.

![](./md_doc_images/img_259.jpg)1. Type the domain administrator user’s name and password \(For example: __contoso\\administrator__, __Password01\!__\)\. Wait a few minutes and make sure all rules check passed, Click __Next__\.

![](./md_doc_images/img_260.jpg)1. Select __Mixed__ __Mode__ type password for __sa__ \(For example: __Password01\!__\), Click __Next__\.

![](./md_doc_images/img_261.jpg)1. Select __Multidimensional and data Mining Mode,__ click __Add Current User__, then click __Next__\.

![](./md_doc_images/img_262.jpg)1. Click __Next__\.

![](./md_doc_images/img_263.jpg)1. Click __Next__\.

![](./md_doc_images/img_264.jpg)1. Click __Add Current User__, then click __Next__\.

![](./md_doc_images/img_265.jpg)1. Type Controller Name \(For example: __Controller01__\), then click __Next__\.

![](./md_doc_images/img_266.jpg)1. Click __Accept__ button, then click __Next__\.

![](./md_doc_images/img_267.jpg)1. Click __Accept__ button, then click __Next__\.

![](./md_doc_images/img_268.jpg)1. Click __Install__\.

![](./md_doc_images/img_269.jpg)### Install Microsoft SQL Server 2019 GA on Ubuntu 16\.04

Please refer to the following link to complete the installation:

[https://docs\.microsoft\.com/zh\-cn/sql/linux/quickstart\-install\-connect\-ubuntu?view=sql\-server\-ver15](https://docs.microsoft.com/zh-cn/sql/linux/quickstart-install-connect-ubuntu?view=sql-server-ver15)

# <a id="_Toc468453842"></a>SQL Server Configuration

The section lists the common SQL Server Configuration for Protocol Test Suite\. 

## <a id="_Toc468453843"></a>Configure the MSSQLSERVER Properties

Below process uses the SQL Server 2012 RC0 as an example, the same steps apply to SQL Server 2008 SP1, SQL Server 2008 R2 SP1 and SQL Server Denali CTP3\.

1. Click __Start__ menu, click __All Programs__, expand __Microsoft SQL Server 2012 RC0__\-> __Configuration Tools__, and click __SQL Server Configuration Manager__\.

![](./md_doc_images/img_270.jpg)

1. Expand __SQL Server Configuration Manager \(Local\)__ \-> __SQL Server Network Configuration__ \-> __Protocols for MSSQLSERVER__, double\-click __Named Pipes__ in the right panel\.![](./md_doc_images/img_271.jpg)
2. Double\-click __Named Pipes__, select __Yes__ for Enable and click __OK__, in the pop\-up window click __OK__\.

![](./md_doc_images/img_272.jpg)

1. Expand __SQL Server Configuration Manager \(Local\)__ \-> __SQL Native Client 11\.0 Configuration \(32bit\)__ \-> __Client Protocols__, check if the __Named Pipes__ are __Enabled__ in the right panel, if not, double\-click __Named Pipes__ and changed the __Enable__ to __Yes__\.

![](./md_doc_images/img_273.jpg)

1. Expand __SQL Server Configuration Manager \(Local\)__ \-> __SQL Native Client 11\.0 Configuration__ \-> __Client Protocols__, check if the __Named Pipes__ are __Enabled__ in the right panel, if not, double\-click __Named Pipes__ and changed the __Enable__ to __Yes__\.

![](./md_doc_images/img_274.jpg)

1. Click __Start__ menu and type __services\.msc__ in __Run__ and press __Enter__\.

![](./md_doc_images/img_275.jpg)

1. Find __SQL Server \(MSSQLSERVER\)__, and __restart__ the service\.

![](./md_doc_images/img_276.jpg)

# <a id="_Toc468453844"></a>Protocol Test Suite Tools Installation

The section lists some tools installation methods which may be used for the protocol test suite\.

## <a id="_Toc468453845"></a>How to install Visual Studio Team System 2008

1. Double click __setup\.exe __to start installation\.
2. Click __Install Visual Studio 2008__\.

![](./md_doc_images/img_277.jpg)

1. Click __Next__\.

![](./md_doc_images/img_278.jpg)

1. Select __I have read and accept the license terms__, and click __Next__\.

![](./md_doc_images/img_279.jpg)

1. Select __Default__, and click __Next__\.

![](./md_doc_images/img_280.jpg)

1. Click __Finish__\.

![](./md_doc_images/img_281.jpg)

## <a id="_Toc468453846"></a><a id="_Toc291609536"></a><a id="_Toc295725394"></a>How to Install Visual Studio 

### How to Install Visual Studio 2010 Ultimate

1. Double click __setup\.exe __to start installation\.
2. Click __Install Microsoft Visual Studio 2010\.  
__![](./md_doc_images/img_282.jpg)
3. Click __Next__\.  
![](./md_doc_images/img_283.jpg)
4. Select __I have read and accept the license terms__, and click __Next\.__![](./md_doc_images/img_284.jpg)
5. Select __Full__, and click __Install\.__![](./md_doc_images/img_285.jpg)
6. When the following figure is shown, click __Restart Now __to restart the computer\.![](./md_doc_images/img_286.jpg)
7. After the computer is restarted, the installation will go on automatically\.![](./md_doc_images/img_287.jpg)
8. When the following figure is shown, click __Finish__\.![](./md_doc_images/img_288.jpg)

### How to Install Visual Studio 2015 Enterprise

1. Select __Custom__ to customize the features for the installation\. Click __Next__\.![](./md_doc_images/img_289.jpg) 
2. Click __Select All__ to select all features\. Click __Next__\.![](./md_doc_images/img_290.jpg) 
3. Click __Install __to start the installation\.

![](./md_doc_images/img_291.jpg)

1. Click __Finish__\.

### How to Install Visual Studio 2017 Enterprise

1. Download

<a id="_Hlk478396914"></a>Go to [https://www\.visualstudio\.com/downloads](https://www.visualstudio.com/downloads) and download the Visual Studio product\. Note, Visual Studio no longer has an ISO or language packs\. All languages are built into the product\. To achieve similar functionality to an ISO, follow the step in 2b\.

1. Install

# <a id="_Hlk478397233"></a>Run the installer from the download location, OR

# To do an offline layout install, follow the instructions at [https://docs\.microsoft\.com/en\-us/visualstudio/install/create\-an\-offline\-installation\-of\-visual\-studio](https://docs.microsoft.com/en-us/visualstudio/install/create-an-offline-installation-of-visual-studio)  

Once you’ve completed your install, you will receive upgrade notifications in Visual Studio and in the VS installer as they become available, so there is no need to download and re\-install\. 

1. Get a key
2. If you have installed Enterprise or Professional, you will need to activate it with a key or subscription \(Community does not require activation\)
3. If you have a Visual Studio Subscription account \(formerly MSDN Subscription\) linked to your FTE account, you can sign into Visual Studio using this and it will work in the place of a key\.
4. If you haven’t linked your account, or aren’t a Microsoft FTE, go to [https://mskeys\.microsoft\.com/](https://mskeys.microsoft.com/) to acquire a key\. Click “Order Keys” and follow the prompts\. Please note that sometimes the “submit” button will still be grayed out even after filling in all the fields\. This is a bug with the webpage – please re\-select your product edition and you should see an active “submit” button\.

## <a id="_Toc468453847"></a>How to install \.NET Framework

### How to Install Microsoft \.NET Framework 3\.5\.1 

1. Go to __Start__\->__All Programs__\->__Administrative Tools__\->__Server Manager__\->__Features__\->__Add Features__\.

![](./md_doc_images/img_292.jpg)

1. Select __\.NET Framework 3\.5\.1__ __Features__ dialog box\.

![](./md_doc_images/img_293.jpg)

1. Click __Add Required Roles Services __in pop\-up window\.

![](./md_doc_images/img_294.jpg)

1. Click __Next __in __Add Features Wizard__ dialog box\.

![](./md_doc_images/img_295.jpg)

1. Click __Next__\.

![](./md_doc_images/img_296.jpg)

1. Click __Next\.__

![](./md_doc_images/img_297.jpg)

1. Click __Install\.__

![](./md_doc_images/img_298.jpg)

1. Click __Close __to finish installation\.

![](./md_doc_images/img_299.jpg)

### <a id="_How_to_install_9"></a><a id="_Toc192064896"></a><a id="_Toc197937840"></a><a id="_Toc198118796"></a><a id="_Toc202285082"></a><a id="_Toc204053389"></a><a id="_Toc205352707"></a><a id="_Toc225224631"></a><a id="_Toc240357689"></a>How to install Microsoft \.NET Framework 4\.0

Note: \.NET Framework 4\.0 will be installed during the installation of SQL Server Denali CTP3 or Visual Studio 2010 Ultimate\.  So if you have installed SQL Server Denali CTP3 or Visual Studio 2010 Ultimate you don’t need to install \.NET Framework 4\.0 separately\.

1. Double click __dotNetFx40\_Full\_x86\_x64\.exe __and extract files\. Please choose “__I have read and accept the license terms”__, and then click “__Install”__\.

![](./md_doc_images/img_300.jpg)

1. Wait for some minutes\.

![](./md_doc_images/img_301.jpg)

1. Click “__Finish”__\.

![](./md_doc_images/img_302.jpg)

1. When the figure below is shown, click “__Restart Now” __to restart the computer\.

![](./md_doc_images/img_303.jpg)

## <a id="_Toc468453848"></a>How to install Microsoft Network Monitor 3\.4

### How to install Microsoft Network Monitor 3\.4

1. Double\-click the __netmon\.msi__\.
2. Click __Next__\.

![](./md_doc_images/img_304.jpg)

1. Choose __I accept the terms in the License Agreement__, and then click __Next__\.

![](./md_doc_images/img_305.jpg)

1. Choose __Use Microsoft Update when I check for updates \(recommended\), __and then click __Next__\.

![](./md_doc_images/img_306.jpg)

1. Click __Typical__\.

![](./md_doc_images/img_307.jpg)

1. Click __Install__\.

![](./md_doc_images/img_308.jpg)

1. Click __Finish__\.

![](./md_doc_images/img_309.jpg)

### <a id="_How_to_install_2"></a><a id="_How_to_install_3"></a><a id="_Toc232424470"></a><a id="_Toc233704022"></a><a id="_Toc234309826"></a><a id="OLE_LINK15"></a><a id="OLE_LINK16"></a><a id="_Toc204053390"></a><a id="_Toc205352708"></a><a id="_Toc208137793"></a><a id="_Toc208205719"></a><a id="_Toc208205938"></a><a id="_Toc208222248"></a><a id="_Toc221709633"></a>How to install Microsoft Network Monitor Parsers

1. Double\-click the __Microsoft\_ Parsers\.exe__\.
2. Click __Next__\.

![](./md_doc_images/img_310.jpg)

1. Please read the following license agreement carefully, if you accept the license agreement, please choose __I accept the terms in the License Agreement__, and then click __Next__\. \(If you select __I do not accept the license terms__ __in the License Agreement__, Microsoft Network Monitor 3\.4 Installation Wizard will be ended and you will not able to install it successfully\.\)

![](./md_doc_images/img_311.jpg)

1. Select __Yes__, click __Next__\.

![](./md_doc_images/img_312.jpg)

1. Click __Typical__\.

![](./md_doc_images/img_313.jpg)

1. Click __Install__\.

![](./md_doc_images/img_314.jpg)

1. Click __Finish__\.

![](./md_doc_images/img_315.jpg)

## <a id="_Toc310940925"></a><a id="_Toc468453849"></a>How to Install Protocol Test Framework

1. Double\-click the __ProtocolTestFramework\.msi\.__
2. Click __Next__\.

![](./md_doc_images/img_316.jpg)

1. Choose __I accept the terms in the License Agreement__, and then click __Next__\.

![](./md_doc_images/img_317.jpg)

1. Click __Install the Software__\.

![](./md_doc_images/img_318.jpg)

1. Click __Next__\.

![](./md_doc_images/img_319.jpg)

1. Click__ Install__\.

![](./md_doc_images/img_320.jpg)

1. Click __Finish__\.

![](./md_doc_images/img_321.jpg)

## <a id="_Toc198118797"></a><a id="_Toc202285083"></a><a id="_Toc204053391"></a><a id="_Toc205352709"></a><a id="_Toc208137794"></a><a id="_Toc208205720"></a><a id="_Toc208205939"></a><a id="_Toc208222249"></a><a id="_Toc221709634"></a><a id="_Toc295725396"></a><a id="_Toc468453850"></a>How to Install Protocol Test Suites Library

1. <a id="OLE_LINK7"></a><a id="OLE_LINK8"></a>Double\-click the __ProtocolTestSuitesLibrary\.msi__\.
2. <a id="OLE_LINK5"></a><a id="OLE_LINK6"></a>Click __Next__\.

![](./md_doc_images/img_322.jpg)

1. Choose __I accept the terms in the License Agreement__, and then click __Next__\.

![](./md_doc_images/img_323.jpg)

1. Click __Next__\.

![](./md_doc_images/img_324.jpg)

1. Click __Install__\.

![](./md_doc_images/img_325.jpg)

1. Click __Finish__\.

<a id="_How_to_install_5"></a>![](./md_doc_images/img_326.jpg)

## <a id="_Toc295725397"></a><a id="_Toc468453851"></a>How to Install Spec Explorer 

1. Double\-click the __SpecExplorer\.msi__\.
2. Choose __I accept the terms in the License Agreement__, and then click __Install__\.

![](./md_doc_images/img_327.jpg)

1. The installation will go on automatically\.

![](./md_doc_images/img_328.jpg)

1. Click __Finish\.__

![](./md_doc_images/img_329.jpg)

## <a id="_How_to_Install_6"></a><a id="_Toc468453852"></a>How to replace Protocol Test Framework Reference Assemblies

### Uninstall old version Protocol Test Framework

1. Close Visual Studio if it is open\.
2. Click __Start\->Control Panel\->Uninstall a program__\.

![](./md_doc_images/img_330.jpg)

1. Select __Protocol Test Framework__ and click __Uninstall__\.

![](./md_doc_images/img_331.jpg)

1. Click __Yes__\.

![](./md_doc_images/img_332.jpg)

### Install new version Protocol Test Framework

1. Double\-click the __ProtocolTestFramework\.msi__\.
2. Click __Next__\.

![](./md_doc_images/img_333.jpg)

1. Choose __I accept the terms in the License Agreement__, and then click __Next__\.

![](./md_doc_images/img_334.jpg)

1. Click __Next__\.

![](./md_doc_images/img_335.jpg)

1. Click __Install__\.

![](./md_doc_images/img_336.jpg)

1. Click __Finish__\.

![](./md_doc_images/img_337.jpg)

### Remove the Reference Assemblies of old version Protocol Test Framework

1. Double click \.sln file\.
2. Unfold __References__ in __ServerAdapter__ project\. Right click __Micorsoft\.Protocols\.TestTools__ and click __Remove__\.

![](./md_doc_images/img_338.jpg)

1. Unfold __References__ in __ServerTestSuite__ project\. Right click __Micorsoft\.Protocols\.TestTools__ and click __Remove__\.

![](./md_doc_images/img_339.jpg)

1. Unfold __References__ in __ServerTestSuite__ project\. Right click __Micorsoft\.Protocols\.TestTools\.VSTS__ and click __Remove__\.

![](./md_doc_images/img_340.jpg)

### Add the Reference Assemblies of new version Protocol Test Framework

1. Right click __References__ in __ServerAdapter__ click __Add Reference__\. 

![](./md_doc_images/img_341.jpg)

1. Select __Microsoft\.Protocols\.TestTools__ and click __OK__\.

![](./md_doc_images/img_342.jpg)

1. Right click __References__ in __ServerTestSuite__ click __Add Reference__\.

![](./md_doc_images/img_343.jpg)

1. Select __Microsoft\.Protocols\.TestTools__ and click __OK__\.

![](./md_doc_images/img_344.jpg)

1. Right click __References__ in __ServerTestSuite__ click __Add Reference__\.

![](./md_doc_images/img_345.jpg)

1. Select __Microsoft\.Protocols\.TestTools\.VSTS__ and click __OK__\.

![](./md_doc_images/img_346.jpg)

## <a id="_Toc468453853"></a>How to install Microsoft SharePoint Server 2010 SP1 for Farm Installation

### Run Microsoft SharePoint Products and Technologies 2010 Preparation Tool

1. On the __Start __page, click Install software prerequisites\. 

![](./md_doc_images/img_347.jpg)

1. On the __Welcome to the Microsoft SharePoint Products and Technologies 2010 Preparation Tool__ page, click Next\.

![](./md_doc_images/img_348.jpg)

1. Select __I accept the terms of the License Agreement\(s\) __and click __Next__\.

![](./md_doc_images/img_349.jpg)

1. On __the Installation Complete__ page, click Finish\.

![](./md_doc_images/img_350.jpg)

### Install Microsoft SharePoint Server 2010 SP1

1. On the Start page, click Install Office SharePoint Server\. 

![](./md_doc_images/img_351.jpg)

1. On the __Enter your Product Key__ page, Enter your __Product Key__ and click __Continue__\.

![](./md_doc_images/img_352.jpg)

1.  On the __Read the Microsoft Software License Terms__ page, review the terms, select __I accept the terms of this agreement__ check box, and then click __Continue__\.

![](./md_doc_images/img_353.jpg)

1. On the __Choose the installation you want__ page, click __Server Farm__\. 

![](./md_doc_images/img_354.jpg)

1. On the __Server Type__ tab, select __Complete, __click__ Install Now\.__

![](./md_doc_images/img_355.jpg)

1. When Setup finishes, unselect __Run the SharePoint Products and Technologies Configuration Wizard now__, click __Close__\.

![](./md_doc_images/img_356.jpg)

## <a id="_Toc468453854"></a>How to Install Message Analyzer 

1. Double\-click the __MessageAnalyzer64\.msi__\.
2. Click __Next__\.

![](./md_doc_images/img_357.jpg)

1. Select the check box to accept all the license, click __Next__\.

![](./md_doc_images/img_358.jpg)

1. Select __Yes__ and click __Next__\.![](./md_doc_images/img_359.jpg)
2. Click __Install__ to start\.![](./md_doc_images/img_360.jpg)
3. Click __Finish__\.![](./md_doc_images/img_361.jpg)

