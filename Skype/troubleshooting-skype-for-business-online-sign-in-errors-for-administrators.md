---
title: Troubleshooting Skype for Business Online sign-in errors for administrators
ms.prod: LYNC
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
---


# Troubleshooting Skype for Business Online sign-in errors for administrators

To troubleshoot Lync sign-in errors, start by eliminating the most common causes of sign-in difficulty. If necessary, you can then follow specific resolution steps based on the type of error. If the user still cannot sign in, collect additional information, and then seek additional help. 
  
    
    


## What do you want to do?
<a name="__top"> </a>



  
    
    
>  [Check for common causes of Lync sign-in errors ](troubleshooting-skype-for-business-online-sign-in-errors-for-administrators.md#__toc323194094)
    
  

  
    
    
>  [Follow resolution steps for a specific error (Enterprise only)](troubleshooting-skype-for-business-online-sign-in-errors-for-administrators.md#__toc325626440)
    

  
    
    
>  [Add a firewall entry for msoidsvc.exe to your proxy server](troubleshooting-skype-for-business-online-sign-in-errors-for-administrators.md#__add_a_firewall)
    
  

  
    
    
>  [Update DNS settings](troubleshooting-skype-for-business-online-sign-in-errors-for-administrators.md#__update_dns_service)
    
  

  
    
    
>  [Install a third-party SSL certificate on your ADFS server](troubleshooting-skype-for-business-online-sign-in-errors-for-administrators.md#__verify_upn_and)
    
  

  
    
    
>  [Update security credentials](troubleshooting-skype-for-business-online-sign-in-errors-for-administrators.md#__update_security_credentials_1)
    
  

  
    
    
>  [Modify TrustModelData registry keys](troubleshooting-skype-for-business-online-sign-in-errors-for-administrators.md#__modify_trustmodeldata_registry)
    
  

  
    
    
>  [Update user settings in Active Directory](troubleshooting-skype-for-business-online-sign-in-errors-for-administrators.md#__update_user_settings_1)
    
  

  
    
    
>  [Use the Microsoft Support troubleshooting guide](troubleshooting-skype-for-business-online-sign-in-errors-for-administrators.md#__toc325626447)
    
  

  
    
    
>  [Collect more information and seek additional help ](troubleshooting-skype-for-business-online-sign-in-errors-for-administrators.md#__collect_more_information_1)
    
  

## Check for common causes of Lync sign-in errors
<a name="__toc323194094"> </a>

Most Lync sign-in issues can be traced to a small number of causes, and many of these are easy to correct. The table below lists some common causes of sign-in errors and some steps you or the users can take to resolve them.
  
    
    


|**Possible Cause**|**Resolution**|
|:-----|:-----|
|During sign-in, a dialog box appears that contains the following phrase: **Lync cannot verify that the server is trusted for your sign-in address. Connect anyway?** <br/> |Verify that the domain name in the dialog box is a trusted server in your organization—for example, **domainName.contoso.com**. Ask the user to select the **Always trust this server** check box, and then click **Connect**. <br/> Enterprise customers can prevent this message from appearing when a user signs in for the first time by modifying the Windows registry on each user's computer. For details, see  [Modify TrustModelData registry keys](troubleshooting-skype-for-business-online-sign-in-errors-for-administrators.md#__modify_trustmodeldata_registry).  <br/> |
|Mistyped sign-in address, user name, or password  <br/> | Confirm that the user's sign-in name and password are correct. <br/>  Verify that the user's sign-in name is formatted as follows: **bobk@contoso.com**. This may be different from the format you use to sign in to your organization's network.  <br/>  Ask the user to try signing in to Lync again. <br/> |
|Forgotten password  <br/> |Reset the user's password and notify him or her of the new temporary password.  <br/> |
|Not licensed to use Lync Online  <br/> |Confirm that the user is registered as a Lync user. If not, register the user, and then ask him or her to sign in to Lync again.  <br/> |
|Wrong version of Lync installed  <br/> |This issue is usually associated with an error message that contains the following phrase: **the authentication service may be incompatible with this version of the program**.  <br/> Ask the user to uninstall and reinstall Lync from the Office 365 Portal.  <br/> |
|Problem acquiring a personal certificate that is required to sign in  <br/> |If the user's sign address has recently changed, they may need to delete cached sign-in data. Ask users to sign out, click the Delete my sign-in info link on the sign-in screen, and then try again.  <br/> |
|You set up a custom domain name, and the changes may not have finished propagating through the system.  <br/> |First, ensure that you have modified the Domain Name Service (DNS) records to reflect the change. For details, see  [Update DNS Service (SRV) Records](troubleshooting-skype-for-business-online-sign-in-errors-for-administrators.md#__update_dns_settings).  <br/> If you have already made the necessary DNS changes, advise the user to try logging in later. DNS changes can take up to 72 hours to be reflected throughout the system.  <br/> |
|System clock out of sync with server clock  <br/> |Ensure that your network domain controller is synchronizing with a reliable external time source. For details, see the Microsoft Knowledge Base article 816042,  [How to configure an authoritative time server in Windows Server](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042).  <br/> |
   
 [To troubleshoot Lync sign-in errors, start by eliminating the most common causes of sign-in difficulty. If necessary, you can then follow specific resolution steps based on the type of error. If the user still cannot sign in, collect additional information, and then seek additional help. ](troubleshooting-skype-for-business-online-sign-in-errors-for-administrators.md#__top)
  
    
    

## Follow resolution steps for a specific error (Enterprise only)
<a name="__toc325626440"> </a>


> [!IMPORTANT]
>  These instructions are intended primarily for Microsoft Office 365 Plan E customers. If you are an Office 365 Plan P customer, continue to the following section, [Collect more information and seek additional help ](troubleshooting-skype-for-business-online-sign-in-errors-for-administrators.md#__collect_more_information_1). 
  
    
    

If the user cannot sign in after you have tried the suggestions in the previous section, then you can do additional troubleshooting based on the type of error. The table below lists the most common error messages and possible causes. Following the table are detailed procedures to address each issue.
  
    
    


|**Error message**|**Possible cause**|**Resolution**|
|:-----|:-----|:-----|
|Sign-in address not found  <br/> |Sign-in requests from the Microsoft Online Services Sign-On Assistant (msoidsvc.exe) are not going through your external firewall, or proxy server.  <br/> | [Add a firewall entry for msoidsvc.exe to your proxy server](troubleshooting-skype-for-business-online-sign-in-errors-for-administrators.md#__add_a_firewall) <br/> |
|Server is temporarily unavailable  <br/> |If your organization has a custom domain, the necessary Domain Name System (DNS) settings may be missing or incorrect.  <br/> | [Update DNS settings](troubleshooting-skype-for-business-online-sign-in-errors-for-administrators.md#__update_dns_service) <br/> |
|Server is temporarily unavailable  <br/> |If your organization is using single sign-on with Active Directory Federation Services (ADFS), you may have used a self-signed Secure Socket Layer (SSL) certificate rather than one from a third-party certification authority.  <br/> | [Install a third-party SSL certificate on your ADFS server](troubleshooting-skype-for-business-online-sign-in-errors-for-administrators.md#__verify_upn_and) <br/> |
|Problem acquiring a personal certificate that is required to sign in  <br/> |If you've already removed the cached server data used by Lync to sign in and the error continues to appear, the user's security credentials may be corrupted, or an RSA folder on the user's computer may be blocking authentication.  <br/> | [Update security credentials](troubleshooting-skype-for-business-online-sign-in-errors-for-administrators.md#__update_security_credentials_1) <br/> |
|A certificate trust dialog box appears when a user signs in for the first time.  <br/> |This dialog box appears if your Lync server is not yet listed in the **TrustModelData** registry key. <br/> | [Modify TrustModelData registry keys](troubleshooting-skype-for-business-online-sign-in-errors-for-administrators.md#__modify_trustmodeldata_registry) <br/> |
|User is not SIP enabled  <br/> |If your organization had a previous installation of Microsoft Office Communications Server or Microsoft Lync Server 2010, you may not have deleted your users from the server before decommissioning it. As a result, the **msRTCSIP-UserEnabled** attribute is still set to **FALSE** in Active Directory Domain Services. <br/> | [Update user settings in Active Directory](troubleshooting-skype-for-business-online-sign-in-errors-for-administrators.md#__update_user_settings_1) <br/> |
   

### Add a firewall entry for msoidsvc.exe to your proxy server
<a name="__add_a_firewall"> </a>

This procedure is a possible fix for the following error message: **Sign-in address not found**.
  
    
    
 **NOTE**: The following steps assume you are using Microsoft Forefront Threat Management Gateway (TMG) 2010. If you have a different web gateway solution, use the settings described in step 4 below.
  
    
    
To create an application entry for Msoidsvc.exe in Forefront TMG 2010, follow these steps:
  
    
    

1. In the Forefront left pane, click **Networking**.
    
  
2. Click the **Network** tab. Under the **Tasks** tab in the right pane, click **Configure Forefront TMG Client Settings**.
    
  
3. In the **Forefront TMG Client Settings** dialog box, click **New**.
    
  
4. In the **Application Entry Setting** dialog box, configure the following rules:
    
  


|****Application****|****Key****|****Value****|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |Disable  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |
   
For details, see the Microsoft Knowledge Base article 2409256,  [You cannot connect to Skype for Business (Lync) Online because an on-premises firewall blocks the connection](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256).
  
    
    

### Update DNS settings
<a name="__update_dns_service"> </a>

If your organization has a custom domain, this procedure is a possible fix for the following error message: **Server is temporarily unavailable**.
  
    
    

- Contact your domain name registrar for information on how to add the following CNAME record to your domain:
    
  - **DNS record type**: CNAME 
    
  
  - **Name**: sip
    
  
  - **Value/Destination**: sipdir.online.microsoft.com
    
  
For details, see the Microsoft Knowledge Base article 2566790,  [Unable to sign in to Skype for Business (Lync) Online because the server is temporarily unavailable](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790), and the Office 365 Wiki article,  [Ensuring your network works with Skype for Business (Lync) Online](https://go.microsoft.com/fwlink/?linkid=231156).
  
    
    

### Install a third-party SSL certificate on your ADFS server
<a name="__verify_upn_and"> </a>

To install a third-party SSL certificate on your Active Domain Federation Services (ADFS) server, follow these steps:
  
    
    

1. Obtain an SSL certificate from a third-party certification authority such as VeriSign or Thawte.
    
  
2. Install the certificate on your ADFS server by using the ADFS management console. For details, see  [Plan for and deploy Active Directory Federation Services 2.0 for use with single sign-on](https://go.microsoft.com/fwlink/?linkid=231164).
    
  

### Update security credentials
<a name="__update_security_credentials_1"> </a>

This procedure is a possible fix for the error message **Problem acquiring a personal certificate required to sign in**.
  
    
    
To eliminate possible certificate or credential problems, first renew the user's certificate in Windows Certificate Manager. To do this, follow these steps:
  
    
    

1. Open Windows Certificate Manager. To do this, click **Start**, click **Run**, type **certmgr.msc**, and then click **OK**. 
    
  
2. Double-click **Personal**, and then double-click **Certificates**. 
    
  
3. Sort by the **Issued By** column, and then look for a certificate that is issued by Communications Server.
    
  
4. Right-click the certificate, and then click **Delete**. 
    
  
Next, if the user is running Windows 7, remove their stored credentials in Windows Credential Manager. To do this, follow these steps:
  
    
    

1. Click **Start**, click **Control Panel**, and then click **Credential Manager**. 
    
  
2. Locate the set of credentials that is used to connect to Lync Online. 
    
  
3. Expand the set of credentials, and then click **Remove from Vault**. 
    
  
4. Sign in to Lync Online again and reenter the user's credentials.
    
  
Finally, if the user still cannot sign in after you've updated their credentials, try deleting the RSA folder on the user's computer, because it could be blocking completion of the user authentication process:
  
    
    

1. Sign in to the user's computer using an administrator account.
    
  
2. If necessary, turn on the folder view option **Show hidden files**. For details, see the Windows help topic  [Show hidden files](https://go.microsoft.com/fwlink/?linkid=231159). 
    
  
3. Type the following into the address bar of File Explorer: **C:\\Documents and Settings\\UserName\\Application Data\\Microsoft\\Crypto\\RSA**, **where** ** *UserName* ** ** is your Windows sign-in name**.
    
  
4. Delete any folder that begins with the name **S-1-5-21-** followed by a string of numbers.
    
  

### Modify TrustModelData registry keys
<a name="__modify_trustmodeldata_registry"> </a>

When a user signs in for the first time, they may receive a dialog box that contains the following phrase: **Lync cannot verify that the server is trusted for your sign-in address. Connect anyway?** This is a security feature, and not an error. However, you can prevent the dialog box from appearing by using a Group Policy Object (GPO) to update users' machines with your domain name before they sign in for the first time. To accomplish this, do the following:
  
    
    

- Create and deploy a GPO that appends your Lync Online domain name—for example, domainName.contoso.com—to the current value of HKEY_LOCAL_MACHINE\\Software\\Policies\\Microsoft\\Communicator\\TrustModelData.
    
  

> [!IMPORTANT]
>  You must *append*  your domain name to the existing value, not simply replace it.
  
    
    

For details, see the Microsoft Knowledge Base article 2531068,  [Skype for Business (Lync) cannot verify that the server is trusted for your sign-in address](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068).
  
    
    

### Update user settings in Active Directory
<a name="__update_user_settings_1"> </a>

If your organization had a previous installation of Microsoft Office Communications Server or Microsoft Lync Server 2010, you may not have deleted your users from the server before decommissioning it. As a result, the **msRTCSIP-UserEnabled** attribute is still set to **FALSE** in Active Directory Domain Services.
  
    
    
To fix this issue, follow these steps:
  
    
    

1. Update the **msRTCSIP-UserEnabled** attribute for all affected users to **TRUE**.
    
  
2. Rerun the Microsoft Online Services Directory Synchronization Tool (DirSync). For details, see  [Active Directory synchronization: Roadmap](https://technet.microsoft.com/en-us/library/hh967642.aspx). 
    
  
 [To troubleshoot Lync sign-in errors, start by eliminating the most common causes of sign-in difficulty. If necessary, you can then follow specific resolution steps based on the type of error. If the user still cannot sign in, collect additional information, and then seek additional help. ](troubleshooting-skype-for-business-online-sign-in-errors-for-administrators.md#__top)
  
    
    

## Use the Microsoft Support troubleshooting guide
<a name="__toc325626447"> </a>

If you're still not able to resolve the user's sign-in problems, review the suggestions in Microsoft Knowledge Base article 2541980,  [How to troubleshoot authentication and connectivity issues in Skype for Business (Lync) Online](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980).
  
    
    

## Collect more information and seek additional help
<a name="__collect_more_information_1"> </a>

If you've followed the guidance above and still can't resolve your Lync Online sign-in issues, you must collect additional information and contact technical support. To do this, follow these steps: 
  
    
    

1. Obtain the Lync log files and Windows Event log details from the user's machine. For step-by-step instructions, see the end-user help topic  [Turn on error logs in Lync](http://technet.microsoft.com/library/eaf6602b-95e0-4c27-869f-36017475806c%28Office.14%29.aspx).
    
  
2. Send the log files and detailed information about the error to Microsoft technical support.
    
  
You may be asked to supply additional diagnostic information by installing the Microsoft Online Services Diagnostic and Logging (MOSDAL) Support Toolkit on the affected user's machine. For details, see  [Using the MOSDAL Support Toolkit](http://technet.microsoft.com/library/ddf1f52f-24a1-4675-abe0-141052c88b72%28Office.14%29.aspx).
  
    
    
 [To troubleshoot Lync sign-in errors, start by eliminating the most common causes of sign-in difficulty. If necessary, you can then follow specific resolution steps based on the type of error. If the user still cannot sign in, collect additional information, and then seek additional help. ](troubleshooting-skype-for-business-online-sign-in-errors-for-administrators.md#__top)
  
    
    

