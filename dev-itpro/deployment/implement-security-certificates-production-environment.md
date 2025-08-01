---
title: Using Security Certificates with Business Central on-premises
description: Learn how to use security certificates to help secure connections with Business Central.
ms.custom:
  - bap-template
  - evergreen
ms.date: 12/20/2024
ms.update-cycle: 1095-days
ms.service: dynamics-365-op
ms.topic: how-to
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
---
# Using security certificates with Business Central on-premises

You use certificates to help secure connections over a wide area network \(WAN\), such as connections from the [!INCLUDE[webserver](../developer/includes/webserver.md)], [!INCLUDE[nav_windows_md](../developer/includes/nav_windows_md.md)], and web services to the [!INCLUDE[server](../developer/includes/server.md)]. Implementing security certificates on your deployment environment requires modifications to various components, like the [!INCLUDE[server](../developer/includes/server.md)], [!INCLUDE[webserver](../developer/includes/webserver.md)], and clients.

## About security certificates

A certificate is a file that [!INCLUDE[server](../developer/includes/server.md)] uses to prove its identity and establish a trusted connection with the client that is trying to connect. [!INCLUDE[prod_short](../developer/includes/prod_short.md)] can support the following configurations:  
  
- *Chain trust*, which specifies that each certificate must belong to a hierarchy of certificates that ends in a root authority at the top of the chain.  
- *Peer trust*, which specifies that both self-issued certificates and certificates in a trusted chain are accepted.  
  
The implementation in this section describes the chain trust configuration, which is the more secure option.  

<!--   
> [!NOTE]  
>  This implementation does not use *Secure Sockets Layer \(SSL\)*. Although these implementations do use the public and private key infrastructure of SSL and SSL certificates, they use Windows Communication Foundation \(WCF\) transport-level security \(TLS\) over the TCP/IP protocol instead of https. This means that these are not strict SSL implementations.
-->  
> [!NOTE]  
> An instance of [!INCLUDE[server](../developer/includes/server.md)] that has been configured for secure WAN communication always prompts users for authentication when they start the client, even when the client computer is in the same domain as [!INCLUDE[server](../developer/includes/server.md)].
  
### Certificates for production
  
In a production environment, you should obtain a certificate from a certification authority or trusted provider. Some large organizations might have their own certification authorities, and other organizations can request a certificate from a third-party organization.
  
###  <a name="AboutProdCerts"></a> Obtaining certificates

You implement chain trust by obtaining X.509 service certificates from a trusted provider. These certificates and their root certification authority \(CA\) certificates must be installed in the certificates store on the computer that is running [!INCLUDE[server](../developer/includes/server.md)]. The CA certificate must also be installed in the certificate store on computers that are running the [!INCLUDE[webserver](../developer/includes/webserver.md)] so that clients can validate the server.  
  
Most enterprises and hosting providers have their own infrastructure for issuing and managing certificates. You can also use these certificate infrastructures. The only requirement is that the service certificates must be set up for key exchange and therefore must contain both private and public keys. Additionally, the service certificates that are installed on [!INCLUDE[server](../developer/includes/server.md)] instances must have the Service Authentication and Client Authentication certificate purposes enabled.  

> [!IMPORTANT]
> Microsoft recommends against using wildcard SSL certificates in [!INCLUDE[prod_short](../developer/includes/prod_short.md)] installations. Wildcard certificates pose security risks because if one server or sub-domain is compromised, all sub-domains may be compromised. Wildcard certificates also introduce a new style of impersonation attack. In this attack, the victim is lured to a fraudulent resource in the certified domain through phishing. Conventional certificates detect this attack, because the user’s browser checks that the private key is hosted on a server whose name matches the one displayed in the browser’s address window. 
  
## Run the certificates snap-in for Microsoft Management Console
  
Some of the following procedures use the Certificates snap-in for Microsoft Management Console \(MMC\). If you don't already have this snap-in installed, you can add it to the MMC. Learn more at [Add the Certificates Snap-in to an MMC](/dotnet/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in).  
  
## Install and configure the certificates
  
You install the security certificates on the computers running [!INCLUDE[server](../developer/includes/server.md)], [!INCLUDE[webserver](../developer/includes/webserver.md)], and [!INCLUDE[nav_windows](../developer/includes/nav_windows_md.md)]. The root CA certificate and the service certificate are used in the configuration, but client certificates aren't.  

### Install certificates on components 

1. Follow the installation instructions that are available from your certificate provider to install the root CA and service certificates on the following computers:  
  
    - Install the root CA on the computer that is running [!INCLUDE[server](../developer/includes/server.md)] and all computers that are running [!INCLUDE[webserver](../developer/includes/webserver.md)] instances and [!INCLUDE[nav_windows](../developer/includes/nav_windows_md.md)].  
    - Install the service certificate on the computer that is running [!INCLUDE[server](../developer/includes/server.md)] only.  
  
2. Make sure that the **Server Authentication** and **Client Authentication** certificate purposes are enabled for the service certificate.  
  
    A certificate can be enabled for several different purposes. The **Server Authentication** and **Client Authentication** purposes must be enabled. You can enable or disable other purposes to suit your requirements.  
  
    You enable certificate purposes by using the Certificates Snap-in for MMC. For more information, see [Modify the Properties of a Certificate](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725909(v=ws.11)).  

### Grant access to the [!INCLUDE[server](../developer/includes/server.md)] service account

After you install the root CA and the service certificate on the [!INCLUDE[server](../developer/includes/server.md)] computer, grant access to the service account, so the account can access the service certificate's private key.

1. In the left pane of MMC, expand the **Certificates \(Local Computer\)** node, expand the **Personal** node, and then select the **Certificates** subfolder.  
  
2. In the right pane, right-click the certificate, select **All Tasks**, and then choose **Manage Private Keys**.  
  
3. In the **Permissions** dialog box for the certificate, choose **Add**.  
  
4. In the **Select Users, Computers, Service Accounts, or Groups** dialog box, enter the name of the dedicated domain user account that is associated with [!INCLUDE[server](../developer/includes/server.md)], and then choose the **OK** button.  
  
5. In the **Full Control** field, select **Allow**, and then choose the **OK** button.  
  
6. In the right pane, select the certificate.  
  
7. In the **Certificate** dialog box, choose the **Details** tab, and then select the **Thumbprint** field.  
  
8. Copy the value of **Thumbprint** field.

    For example, copy the hexadecimal characters to text editor, such as Notepad. Delete all spaces from the thumbprint string. If the thumbprint is `c0 d0 f2 70 95 b0 3d 43 17 e2 19 84 10 24 32 8c ef 24 87 79`, then change it to `c0d0f27095b03d4317e219841024328cef248779`.

    > [!TIP] 
    > It is important that the thumbprint does not contain any invisible extra characters; otherwise you will experience problems when using it later. Learn more at [Certificate thumbprint displayed in MMC certificate snap-in has extra invisible unicode character](https://support.microsoft.com/en-au/help/2023835/certificate-thumbprint-displayed-in-mmc-certificate-snap-in-has-extra). 

## Configure the [!INCLUDE[server](../developer/includes/server.md)] instance
  
The [!INCLUDE[server](../developer/includes/server.md)] instance configuration includes several settings for certificates and enabling remote logins. You can modify a server instance by using [!INCLUDE[admintool](../developer/includes/admintool.md)] (version 20 and earlier only) or [!INCLUDE[adminshell](../developer/includes/adminshell.md)]. Learn more about how to modify a server instance in [Configuring Business Central Server](../administration/configure-server-instance.md). 

### Using [!INCLUDE[adminshell](../developer/includes/adminshell.md)]

1. Run the [!INCLUDE[adminshell](../developer/includes/adminshell.md)] as an administrator. Learn more in [Administration Shell](../administration/administration-shell.md).
2. At the prompt, run the following command to specify the certificate thumbprint:

    ```powershell
    Set-NAVServerConfiguration -ServerInstance <BC server instance> -KeyName ServicesCertificateThumbprint -KeyValue <thumbprint>
    ```

    Substitute `<BC server instance>` with name of your server instance, like `BC240`.
3. Run the following command to specify SSL between the web client and [!INCLUDE[server](../developer/includes/server.md)]:

    ```powershell
    Set-NAVServerConfiguration -ServerInstance <BC server instance> -KeyName ClientServicesSSLEnabled -KeyValue true
    ```

    > [!NOTE]
    > This step is only for version 21 and later.

4. Run the following commands to secure SOAP and OData web services:

    ```powershell
    Set-NAVServerConfiguration -ServerInstance <BC server instance> -KeyName SOAPServicesSSLEnabled -KeyValue true
    ```

    ```powershell
    Set-NAVServerConfiguration -ServerInstance <BC server instance> -KeyName ODataServicesSSLEnabled -KeyValue true
    ```

### Using [!INCLUDE[admintool](../developer/includes/admintool.md)]

The [!INCLUDE[admintool](../developer/includes/admintool.md)] is only available for version 20 and earlier.

1. Run the [!INCLUDE[admintool](../developer/includes/admintool.md)].
2. Under **General**, change the following settings for the [!INCLUDE[server](../developer/includes/server.md)] instance.  
  
    |Setting|New value|Description|  
    |---------|---------------|-----------------|  
    |Credential Type|`Windows`, `NavUserPassword`, `Username`, or `AccessControlService`|The default value is `Windows`. When you change it to `NavUserPassword`, `Username`, or `AccessControlService`, client users who connect to the server are prompted for user name and password credentials.|  
    |Certificate Thumbprint|Value of the **Thumbprint** field in the previous procedure.|Remove any leading or trailing spaces in the thumbprint.|  

3. If you want to use secure web services, then under **SOAP Services** and **OData Services**, select the **Enable SSL** check box.

4. Save and the new values for the server instance.
  
5. Restart the [!INCLUDE[server](../developer/includes/server.md)] instance.  
  
    If there's a problem, see Windows Event Viewer.  
  
## Configure the [!INCLUDE[webserver](../developer/includes/webserver.md)]

The chain trust configuration allows client users to sign in instances of [!INCLUDE[server](../developer/includes/server.md)] as long as their login credentials are associated with user accounts in [!INCLUDE[prod_short](../developer/includes/prod_short.md)]. The client validates that the server certificate is signed with the root CA.  
  
After you install the root CA on the computer running the [!INCLUDE[webserver](../developer/includes/webserver.md)], modify the client configuration file.
  
### Modify the [!INCLUDE[nav_web](../developer/includes/nav_web_md.md)] configuration file  

To configure the [!INCLUDE[webserver](../developer/includes/webserver.md)], you need the subject name, also known as the common name \(CN\), of the certificate that is used on the computer that is running [!INCLUDE[server](../developer/includes/server.md)].

You can configure the [!INCLUDE[webserver](../developer/includes/webserver.md)] using the [!INCLUDE[adminshell](../developer/includes/adminshell.md)] or changing the navsettings.json file manually.

#### Using [!INCLUDE[adminshell](../developer/includes/adminshell.md)] 

1. Run the [!INCLUDE[adminshell](../developer/includes/adminshell.md)] as an administrator. For more information, see [Administration Shell](../administration/administration-shell.md).
2. At the prompt, run the following commands:

    ```powershell
    Set-NAVWebServerInstanceConfiguration -WebServerInstance <web server instance> -KeyName DnsIdentity -KeyValue <certificate subject name or common name>
    ```

    This following command is only required for version 21 and later:

    ```powershell
    Set-NAVWebServerInstanceConfiguration -WebServerInstance <web server instance> -KeyName ServerHttps -KeyValue true
    ```

    Substitute `<web server instance>` with name of your web server instance, like `BC240`.

#### Manually changing the navsettings.json

1. On the computer where the [!INCLUDE[webserver](../developer/includes/webserver.md)] is installed, open the [navsetting.json configuration file](../administration/configure-web-server.md#WebClientSettingsFile) in a text editor, such as Notepad.
  
2. Change the following settings:  
  
    |Key|New value|Description|  
    |---------|---------------|-----------------|  
    |ClientServicesCredentialType|`Windows`, `NavUserPassword`, `Username`, or `AccessControlService`|The default value is `Windows`. When you change it to `NavUserPassword`, `Username`, or `AccessControlService`, client users who connect to the server are prompted for user name and password credentials.|  
    |DnsIdentity|The subject name of the service certificate|The default value is \<identity>. Replace this value with the subject name or common name \(CN\) of the certificate that is used on the computer that is running [!INCLUDE[server](../developer/includes/server.md)].|
    |ServerHttps|`true`|The default value is `false`. This key is only available in version 21 and later, so it doesn't need to be set in earlier versions.|   

3. Save the navsettings.json configuration file.  
  
## Configure [!INCLUDE[nav_windows](../developer/includes/nav_windows_md.md)]

> [!NOTE]
> This section only applies to Business Central Spring 2019, version 14. [!INCLUDE[nav_windows](../developer/includes/nav_windows_md.md)] isn't supported in later versions.
 
After you install the root CA on the computer running the [!INCLUDE[nav_windows](../developer/includes/nav_windows_md.md)], you must modify the client configuration file.
  
### Modify the [!INCLUDE[nav_windows](../developer/includes/nav_windows_md.md)] configuration file  
  
1. Open the ClientUserSettings.config configuration file.  
  
     The location of this file is *Users\\\<*username*>\\AppData\\RoamingLocal\\Microsoft\\[!INCLUDE[prod_long](../developer/includes/prod_long.md)]\\\<version>*.
  
     By default, this file is hidden. Therefore, you might have to change your folder options in Windows Explorer to view hidden files.  
  
    > [!NOTE]  
    >  If you want to change default [!INCLUDE[nav_windows](../developer/includes/nav_windows_md.md)] settings for all future users, edit the default ClientUserSettings.config file&mdash;that is, the one in [!INCLUDE[prodx86installpath](../developer/includes/prodx86installpath.md)]. Be sure that you run your text editor with Administrator privileges when you do so.  
  
2. Modify the following settings.  
  
    |Key|New value|Description|  
    |---------|---------------|-----------------|  
    |ClientServicesCredentialType|`NavUserPassword`, `Username`, or `AccessControlService`|The default value is `Windows`. When you change it to `NavUserPassword`, `Username`, or `AccessControlService`, client users are prompted for user name and password credentials.|  
    |DnsIdentity|The subject name of the service certificate.|The default value is \<identity>. Replace this value with the subject name or common name \(CN\) of the certificate that is used on the computer that is running [!INCLUDE[server](../developer/includes/server.md)].|  
  
3. Save and close the ClientUserSettings.config file.  
  
When users start the [!INCLUDE[nav_windows](../developer/includes/nav_windows_md.md)], they're prompted for a valid user name and password.

## Related information

[Authentication and User Credential Types](../administration/users-credential-types.md)
