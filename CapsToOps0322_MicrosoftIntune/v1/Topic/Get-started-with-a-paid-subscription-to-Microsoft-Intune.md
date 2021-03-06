---
title: Get started with a paid subscription to Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a
author: Staciebarker
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - hu-hu
  - it-it
  - ja-jp
  - ko-kr
  - nl-nl
  - pl-pl
  - pt-br
  - pt-pt
  - ru-ru
  - sv-se
  - tr-tr
  - zh-cn
  - zh-tw
---
# Get started with a paid subscription to Microsoft Intune
Whether you start with a 30-day free trial,  or start with a paid subscription, Microsoft Intune provides a quick and easy way for you to manage mobile devices and computers in your organization. This topic  leads you through the steps of setting up a cloud-only instance of [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)].

If you purchase at least 150 licenses for Microsoft Intune in an eligible plan, you can use the "FastTrack Center Benefit," a service where Microsoft specialists work with you to get your environment ready for Intune. See [Microsoft Intune Service Benefit Description](https://technet.microsoft.com/library/mt228265.aspx).

Getting started with a paid subscription of Intune shares many of the same steps as starting with a [free 30-day trial](https://technet.microsoft.com/library/dn646983.aspx). However  in this topic, you'll also cover some additional areas that most people might not need to address in trial deployments, including:

-   Synchronizing on-premises Active Directory accounts with Intune and Azure Active Directory

-   Domain and DNS service considerations

-   Customizing Intune features for production use

This topic focuses on configuring Intune as a standalone service. If you're currently using Microsoft System Center Configuration Manager (ConfigMgr) to manage computers and servers, you can connect Intune with ConfgMgr in a hybrid deployment. This configuration offers several benefits and leverages your existing on-premises infrastructure. See [Manage Mobile Devices with Configuration Manager and Microsoft Intune](https://technet.microsoft.com/library/jj884158.aspx) for more information about hybrid Intune and ConfigMgr deployments.

## Before you begin
Starting with a paid subscription means that you've [completed an Intune trial](https://technet.microsoft.com/library/dn646983.aspx) and that you're ready to deploy Intune and make changes to your existing network infrastructure. This could range from simply adding or updating your internal and external DNS records to connecting your existing Active Directory accounts to Azure Active Directory. Whatever mix of Intune  mobile device management features you leverage, you'll need to  carefully plan how Intune will interact with your existing network components and services. Specifically, you should review:

-   **How you'll manage user identity**:  For most medium-level and enterprise-level organizations, connecting your existing directory services to Intune via Azure Active Directory is the best and most convenient way to manage user identity with Intune. This is especially true if you already use other Microsoft cloud services, such as Office 365 or Exchange Online. Synchronizing your existing user accounts using [Microsoft's AD Connect](https://www.microsoft.com/download/details.aspx?id=47594) is a quick and easy way to connect your on-premises Active Directory to Azure Active Directory and configure a single sign-on authentication experience for your users.

-   **How DNS will be impacted**: If you want to use your own domain name instead of the default onmicrosoft.com domain generated by the Intune service, some public DNS record updates will be needed when configuring Azure (or other Microsoft cloud services) to use your custom domain. DNS records are required so that mobile devices can locate the Intune service, as well as making other mobility management services work correctly. You'll need to decide if you want  to manage your DNS records at your DNS host  or have Azure or Office 365 create and manage the DNS records for your domain after you change your DNS records to point to these services.

Ready to get started? You'll need the following when starting your paid subscription to Intune:

-   A device with a Silverlight-enabled web browser that you can use to access the websites where you'll  create Intune user accounts (the **Intune Account Portal**) and where you'll manage devices, groups, and policies  (the **Intune administration console**).

-   A second device with a web browser, which you can use to access the company portal to see how most [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] users will enroll and manage their devices, find and install software, and request help from administrators. Instead of using a second device with a web browser, you can use the “privacy mode” setting on the same browser that you use for [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] administration (for example: in Internet Explorer, you can click **Tools** &gt; **InPrivate Browsing**).

-   If you have an existing Microsoft Online Services account, you'll need the administrator credentials for that account. If you don’t have such an account, or if you want to use this Intune tenant for evaluation purposes only, you don't need tenant administrator credentials.

-   If you'll manage iOS or Windows Phone devices with Intune, you'll need certificates (or keys) and accounts to retrieve those certificates. Android devices don't need any additional certificates:

    |Platform|Certificate Requirements|More information|
    |------------|----------------------------|--------------------|
    |Windows Phone 8.1 and [!INCLUDE[winphone8_client_1](../Token/winphone8_client_1_md.md)]|No certificate is required for Windows Phone 8.1 users who install the company portal app from the Store. A Symantec certificate is required for Windows Phone 8.0 or to use Intune to deploy the company portal app to Windows Phone 8.1 devices.|This guidance assumes your users get the company portal app from the Store on a Windows Phone 8.1 or later device. For information about Windows Phone 8.0 support, see [Set up Windows Phone management with Microsoft Intune](../Topic/Set-up-Windows-Phone-management-with-Microsoft-Intune.md).|
    |Windows 10, [!INCLUDE[winblue_winrt_2](../Token/winblue_winrt_2_md.md)], [!INCLUDE[win8RT_client_1](../Token/win8RT_client_1_md.md)], or [!INCLUDE[winblue_client_2](../Token/winblue_client_2_md.md)] devices|There are no certificate requirements for enrolling Windows RT and Windows devices.|[Install the Windows PC client with Microsoft Intune](../Topic/Install-the-Windows-PC-client-with-Microsoft-Intune.md).|
    |iOS or Mac OS X|Get an Apple Push Notification service certificate.|Request an Apple Push Notification service certificate from Apple, as described here: [Set up iOS and Mac management with Microsoft Intune](../Topic/Set-up-iOS-and-Mac-management-with-Microsoft-Intune.md).|

## <a name="Step1"></a>Step 1: Sign up or sign in to Intune
Before  you either sign up or sign in to Intune,  you should consider the following:

-   Whether your organization already has a Microsoft Online Services work or school account

-   Whether you have an Enterprise Agreement or equivalent volume licensing agreement with Microsoft

|Sign up for a NEW account if either of the following is true:|Sign in with your WORK or SCHOOL account if:|
|-----------------------------------------------------------------|------------------------------------------------|
|**You don’t have a work or school account.** A work or school account is provided when you sign a volume licensing agreement with Microsoft or subscribe to Office 365. If your organization has not signed an Enterprise Agreement or equivalent volume licensing agreement with Microsoft (or has an Office 365 account), then you do not have a Microsoft Online Services account that you can use to sign in to Microsoft Online Services.<br /><br />**You will discard your Intune tenant after completing the 30-day trial.** You should sign up for a new account if you are using your [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] free trial subscription for evaluation purposes only, and you plan to redo your [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] service setup and device provisioning after the trial. This is the recommended option if you plan to use [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] with System Center 2012 Configuration Manager.<br /><br />If you sign up for a new account, you cannot later use an existing work or school account to manage that account, or combine it with existing volume licensing agreements.|**You have a work or school account provided with a volume licensing agreement or Office 365 subscription, and you are using this trial to evaluate [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].**<br /><br />If you are setting up [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] on an existing account, we recommend that you review [Introduction to Microsoft Intune](../Topic/Introduction-to-Microsoft-Intune.md) before continuing with these steps.|

### <a name="BKMK_ToSignUpforSubscription"></a>Sign up or sign in to Intune

1.  First, [click here to visit the Intune Sign up page](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20).

2.  On the **Sign up** page, sign in or sign up.

If  you complete the sign-up process, you're automatically signed in to the [!INCLUDE[wit_icp_1](../Token/wit_icp_1_md.md)] with the tenant administrator account. An email message that contains your account information is also sent to the email address that you provided during sign-up. This email confirms your subscription is active. If you sign in, you're automatically directed to the Intune admin portal.

## <a name="BKMK_ConfigureDomain"></a>Step 2: Configure a custom domain name
By default, [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] uses the domain name that you select when you subscribe to the service, which looks like **&lt;domain&gt;.onmicrosoft.com**. When your organization owns a custom domain, you can configure your instance of [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] to use that domain instead of the domain name provided with your subscription.

Before you create new user accounts or synchronize accounts from your on-premises Active Directory, we strongly recommend that you decide whether to use only the .onmicrosoft.com domain or to add one or more of your custom domain names. If you don't configure a custom domain name and suffix, each user account you import receives the onmicrosoft.com suffix for its user principal name (UPN). Configuring a custom domain before adding users can help simplify the management of user identities for your subscription by enabling users to sign in with the credentials they use to access other domain resources.

Because the tasks to configure [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] to use your organizations custom domain name are the same as for other Azure AD tenants, use the information and procedures found in [Add your domain](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

For more information about using your custom domain with a cloud-based service from Microsoft, see [Internet domain management](http://technet.microsoft.com/library/hh969248.aspx).

When you subscribe to a cloud-based service from Microsoft, your instance of that service becomes a tenant of Microsoft Azure Active Directory (Azure AD), which provides identity and directory services for your cloud-based service.

For more information about your Azure AD tenant, see [What is an Azure AD tenant?](http://technet.microsoft.com/library/jj573650.aspx).

## <a name="BKMK_SyncUsersFromAD"></a>Step 3: Synchronize Active Directory and add users to Intune
As mentioned, you can configure directory synchronization to import user accounts from your on-premises Active Directory to Microsoft Azure Active Directory. Additionally, when you activate directory synchronization in your Intune tenant, you are turning on this feature across  all the Microsoft cloud services that you are subscribed to. When you use multiple services with the same Azure AD, the user accounts that you synchronize are available to each cloud-based service that shares your Azure AD. Having your on-premises Active Directory service connected with all of your Azure Active Directory-based services makes managing user identity much simpler. You can also configure single sign-on features to make the authentication experience for your users familiar and easy.

The [Azure AD Connect wizard](https://www.microsoft.com/download/details.aspx?id=47594) is the single tool and guided experience for connecting your on-premises identity infrastructure to the cloud.  Choose your topology and needs (single or multiple directories, password sync or federation), and the wizard will deploy and configure all components required to get your connection up and running, including sync services, Active Directory Federation Services (AD FS), and the Azure AD PowerShell module.
Azure AD Connect encompasses functionality that was previously released as Dirsync and Azure AD Sync.
Learn more about directory integration at [Directory integration](http://technet.microsoft.com/library/jj573653.aspx).

After you've added users to your Intune subscription, we recommend that you grant a few user accounts administrative credentials. The console that you use to assign administrative credentials depends on the type of administrator you want to assign:

-   **Tenant administrator**: Use the **[!INCLUDE[wit_icp_1](../Token/wit_icp_1_md.md)]** to assign this type of administrator to manage your subscription, including billing, cloud storage, and managing the users who can use [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

-   **Service administrator**: Use the **[!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)]** to assign this type of administrator for day-to-day tasks including management of mobile devices or computers, deploying policy or software, and running reports.

To learn more about administrator accounts, see [Intune administrator accounts and special permissions](../Topic/What-to-know-before-setting-up-Microsoft-Intune.md#BKMK_AdminAccounts).

To learn about the benefits of synchronizing user accounts from your local directory to Azure AD, see
            [Similarities between Active Directory and Azure AD](http://technet.microsoft.com/library/dn518177.aspx).

## <a name="BKMK_AssignWitLicenses"></a>Step 4: Manage Intune licenses
A user must have a license to your Intune subscription before they can sign in to use the service. When users have a license, they are a member of the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] user group. This group includes all users who have a license to use the subscription. **Each user license supports enrolling up to five devices**.

-   **When you use the [!INCLUDE[wit_icp_2](../Token/wit_icp_2_md.md)] to add users** to your subscription, either manually or by bulk import from a CSV file, [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] assigns an available license to each user account. If you do not have an available license, then no license is assigned. With both methods, you have the option to not assign licenses to the new user accounts at the time you add them to your subscription.

-   **When you import users from your on-premises Active Directory**, [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] does not assign a license to each user account. Instead, at a later time, you must edit the user account to assign a license to the user.

-   **When your subscription shares Azure AD with other Azure AD tenants**, you have access to users that were added to those services. These users do not have a license to [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] until you assign a license to each of them.

If the option to assign or revoke a license to [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] is disabled, your subscription might include volume licensing options, such as the options available when using [Enterprise Mobility Suite](http://www.microsoft.com/server-cloud/products/enterprise-mobility-suite/default.aspx). For information on how to assign or revoke licenses, see the documentation for your licensing options.

## <a name="Step3"></a>Step 5: Create groups to organize users and devices
Groups in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] give you great flexibility for managing your devices and users. You can set up groups to suit your organizational needs (for example, by geographic location, department, or hardware characteristics) and use them to perform a wide variety of administrative tasks, from deploying policies for a set of users to deploying applications to a set of devices.

### Create a device group
Use device groups to deploy apps and updates, and configure other features. For example, set up a "My Devices" group using the following steps:

1.  In the [Intune administration console](https://manage.microsoft.com/), click **Groups** &gt; **Overview** &gt; **Create Group**.

2.  For the **Group name**, type “My Devices” and, from the parent group list, select **All Devices**, and then click **Next**.

3.  On the **Define Membership Criteria** page, select **All devices** to indicate that the group includes both mobile devices and computers.

4.  On the **Define Direct Membership** page, click **Next**. If you previously created a group that did not include all devices, and you wanted to add specific devices to your new group, you can do that here.

5.  On the **Summary** page, review the actions that will be taken, and then click **Finish**.

You can find the newly created group in the **Groups** list, in the **Groups** workspace, under **All Devices**. From here, you can also edit or delete the group.

### Create a user group
Use user groups to deploy software and device policies. For example, set up an "Intune Users" group using the following steps:

1.  In the [Intune administration console](https://manage.microsoft.com/), click **Groups** &gt; **Overview** &gt; **Create Group**.

2.  For the **Group name**, type “Intune Users” and, from the parent group list, select **All Users**, and then click **Next**.

3.  On the **Define Membership Criteria** page, set **Start group membership with** to **All users in the Parent group**.

4.  Beside **Exclude members from these security groups**, click **Browse** and then select **Company Administrator**. This exclusion lets you manage the Intune Users group without affecting the Company Administrator account (also known as the tenant administrator).

5.  On the **Define Direct Membership** page, click **Next**. You don’t need to do anything here because you want the Intune Users group to include all users, except for the Company Administrator.

6.  On the **Summary** page, review the actions that will be taken, and then click **Finish**.

You can find the newly created group in the **Groups** list, in the **Groups** workspace, under **All Users**. From here, you can also edit or delete the group.

To learn more about using groups, see [Use groups to manage users and devices with Microsoft Intune](../Topic/Use-groups-to-manage-users-and-devices-with-Microsoft-Intune.md).

## <a name="Step4"></a>Step 6: Create policies and publish an app
[!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] policies provide settings that help you control the security settings on mobile devices, maintain Windows Firewall and Endpoint Protection settings for computers, and deploy applications. If you are planning to use Intune for devices that you configure for production use after the trial, it's absolutely essential that you follow the instructions in [Manage settings and features on your devices with Microsoft Intune policies](../Topic/Manage-settings-and-features-on-your-devices-with-Microsoft-Intune-policies.md) and [Help secure Windows PCs with Endpoint Protection for Microsoft Intune](../Topic/Help-secure-Windows-PCs-with-Endpoint-Protection-for-Microsoft-Intune.md).

You can perform two types of app installations using Intune. The first is a **required install**, which automatically deploys the app to managed computers. The other is an **available install**, which deploys the app, or a link to the app, to the Intune company portal so that users can choose whether to install it on their computers or on their mobile devices.

Before using Intune to deploy apps, make sure that you have the appropriate licenses to publish, distribute, and use the app. The Licenses workspace lets you add and manage license agreement information for apps or software purchased through Microsoft Volume Licensing agreements, and for Microsoft or non-Microsoft software that was purchased by other means. You can then create license reports that display managed license usage information throughout your company to stay informed of license usage activity.

In these steps, you'll set up a mobile device configuration policy and a Windows computer firewall policy, and configure Skype as an available install for mobile devices after they're enrolled. After you add and deploy a new policy, all users or devices in the group to which you deployed the policy inherit the settings as their baseline policy. You can always review and edit the details of these policies later from the Policy workspace.

#### Create and deploy a mobile device configuration policy

1.  Open the [Intune administration console](https://manage.microsoft.com/).

2.  In the left pane, click the **Policy** icon.

3.  In the **Tasks** list on the **Policy Overview** page, click **Add Policy**.

4.  In the policy list, expand the platform you want to create a policy for, then select **General Configuration**, choose **Create and Deploy a Policy with the Recommended Settings**, and then click **Create Policy**.

5.  When prompted to **Select the groups to which you want to deploy this policy**, select **My Trial Users** from the list, and click **Add** &gt; **OK**.

Your policy appears in the list of configuration policies, and has been deployed to the **My Trial Users** group. Double-click the policy to view its settings.

#### Publish the Skype app for mobile devices

1.  In the [Intune administration console](https://manage.microsoft.com/), click the **Apps** icon, then click **Apps** &gt; **Add App**. If prompted, enter your [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] credentials.

    > [!NOTE]
    > When you start the **Intune Software Publisher** for the first time, a short delay occurs while the application is installed.

2.  Review the security warning and click **Run**.

3.  On the **Before you begin** page, click **Next**.

4.  On the **Software setup** page in **Select how this software is made available to devices**, select **External link**.

5.  Enter the external link for the software in **Specify the URL**, and then click **Next**. Make sure that you preface the URL with **http://**. For the Skype app, use the link below that matches the mobile device platform you're using:

    -   **iOS:**[https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8](https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8)

    -   **Android:**[https://play.google.com/store/apps/details?id=com.skype.raider](https://play.google.com/store/apps/details?id=com.skype.raider)

    -   **Windows Phone 8 or Windows Phone 8.1:**[http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51](http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51)

6.  On the **Software description** page, provide the information that you want users to see in the company portal for the software, and then click **Next**. The following settings are available (this example refers to Skype):

    -   **Publisher:** Enter the name of the publisher, "Microsoft"

    -   **Name:** Enter **Skype**

    -   **Description:** Enter a description for the software, such as **Skype communication app**

    -   **Category:** Select the category that best fits this software, such as **Collaboration**

    -   **Display this as a featured app and highlight it in the company portal:** Select this option to display the app prominently in the company portal on mobile devices.

    -   **Icon:** Choose whether to associate an icon with the software. The maximum size for the icon is 250 x 250 pixels. The recommended size is 32 x 32 pixels. This setting is optional for the Intune trial tenant.

7.  On the **Summary** page, verify the software information, and then click **Upload**. Click **Close** to exit the wizard.

8.  In the [Intune administration console](https://manage.microsoft.com/), click **Apps** &gt; **Apps** &gt; **Skype** &gt; **Manage Deployment**.

9. On the **Select Groups** page, select **My Trial Users** to deploy the software to that user group, and then click **Add** &gt; **Next**.

10. On the **Deployment Action** page, select **Available Install** from the **Approval** column for your group.

11. Click **Finish**.

The Skype app is now available to install on mobile devices from the company portal, but first you need to install [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] software on computers and mobile devices.

## <a name="BKMK_ConfigureCompanyPortal"></a>Step 7: Customize the company portal
The [!INCLUDE[wit_iwportal_1](../Token/wit_iwportal_1_md.md)] is where users access company data and can do common tasks like enrolling devices, installing apps, and locating information for assistance from your IT department.

When you customize the company portal, the configurations apply to both the company portal website and company portal apps.

### <a name="BKMK_ToCustomizeCompanyPortal"></a>Settings for customizing the company portal

1.  In the [Microsoft Intune administrator console](https://manage.microsoft.com), click **Admin** &gt; **Company Portal**.

2.  Configure one or more of the following optional items.

    |Configuration area|Field name|Maximum character length|More information|
    |----------------------|--------------|----------------------------|--------------------|
    |Company contact information and privacy statement|Company name|40|This name is displayed as the title of the company portal.|
    ||IT department contact name|40|This name is displayed on the **Contact IT** page.|
    ||IT department phone number|20|This contact number is displayed on the **Contact IT** page.|
    ||IT department email address|40|This contact address is displayed on the **Contact IT** page.<br /><br />You must enter a valid email address in the format **alias@domainname.com**.|
    ||Additional information|120|Displayed on the **Contact IT** page.|
    ||Company privacy statement URL|79|You can specify your own company privacy statement that appears when users click the privacy links from the company portal.<br /><br />You must enter a valid URL in the format **https://www.contoso.com**.|
    |Support contacts|Support website URL|150|If you have a support website that you want your users to use, specify the URL here. The URL must be in the format **https://www.contoso.com**.<br /><br />If you don't specify a URL, nothing is displayed for the support website on the **Contact IT** page in the company portal.|
    ||Website name|40|This name is the friendly name that is displayed for the URL to the support website.<br /><br />If you specify a support website URL and no friendly name, then **Go to IT website** is displayed on the **Contact IT** page in the company portal.|
    |Customization|Theme color|Not applicable|Select a theme color to apply to the company portal.|
    ||Include company logo|Not applicable|When you enable this option, you can upload your company logo to show in your company portal. You can upload two logos: one logo that is displayed when the company portal background is white, and one logo that is displayed when the company portal background uses your selected theme color.<br /><br />Each logo must be a .png or .jpg file type and have a maximum resolution of 400 x 100 pixels and be 750 KB or less in size.|
    ||Choose a background for [!INCLUDE[win8_client_2](../Token/win8_client_2_md.md)] company portal app|Not applicable|This setting affects the background for the [!INCLUDE[win8_client_2](../Token/win8_client_2_md.md)] company portal app only.|

3.  Click **Save** to save your changes.

After you save your changes, you can use the links provided at the bottom of the **Company Portal** page of the administration console to view the company portal website. These links cannot be changed. When a user signs in, these links display your subscriptions in the company portal.

## <a name="Step5"></a>Step 8: Enroll computers in Intune
You can install the [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] client software on computers in the following ways:

-   Users can use an installer provided by the administrator to manually enroll

-   [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] software can be included in an OS image or deployed using Group Policy

-   End users can also self-enroll their devices through the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] company portal

Each enrolled computer is linked to the user account that was used to install the client software. Microsoft Intune Endpoint Protection is also installed by default during Intune client installation on computers. Endpoint Protection helps to secure the computers in your organization by providing real-time protection against potential threats, keeping malicious software definitions up to date, and automatically running scheduled scans. For added security, you can also use Intune policies to manage Windows Firewall settings on managed computers.

What to know before you start:

-   The user must be an administrator on the computer to install the client software.

-   Self-enrolling requires that Internet Explorer is installed on the client computer.

-   Each time a user self-enrolls a computer, it uses a [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] license.

-   You must use a Microsoft Online Services work or school account to self-enroll a computer. This is the account that you used to sign in, or the administrator account that was created when you signed up for the free trial.

For this example, you'll use the self-enrollment approach:

1.  In the [Intune administration console](https://manage.microsoft.com/), click **Admin** &gt; **Company Portal**, and then scroll to the bottom of the screen. Copy the URL shown under **Intune company portal**.

2.  Use Internet Explorer to browse to the company portal URL that you acquired in the previous step, and log in with your administrator credentials.

3.  Click **Add Device**.

4.  Click **Download Software** and then click **Run**.

5.  Click **Next** to start the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)] Setup wizard.

6.  When the Setup wizard has completed, click **Finish**.

To learn more about computer management using [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], see [Install the Windows PC client with Microsoft Intune](../Topic/Install-the-Windows-PC-client-with-Microsoft-Intune.md).

To learn more about software management using [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], see [Deploy and configure apps with Microsoft Intune](../Topic/Deploy-and-configure-apps-with-Microsoft-Intune.md).

## <a name="Step6"></a>Step 9: Enroll mobile devices and install an app
To set up mobile device management with Intune, you must  first set the mobile device management authority,  enable management for device platforms, and enroll your devices with the company portal app. You can then deploy the Microsoft Skype application that you published.

#### Enable device management and enroll devices

1.  **Make Intune your mobile device management authority**
    In the [Intune administration console](https://manage.microsoft.com/), click **Admin** &gt; **Mobile Device Management**, and click **Set MDM Authority** under **Tasks**.  Click **Yes** in the MDM Authority dialog box.

2.  **Enable MDM for your device platform**
    Enable mobile device management for the device platform you want to manage. Depending on your platform, different requirements are needed:

    -   **iOS and Mac OS X**: see [Set up iOS and Mac management with Microsoft Intune](../Topic/Set-up-iOS-and-Mac-management-with-Microsoft-Intune.md).

    -   **Windows Phone**: see [Set up Windows Phone management with Microsoft Intune](../Topic/Set-up-Windows-Phone-management-with-Microsoft-Intune.md).

    -   **Android**: Android mobile devices allow users to enroll using the company portal app available from Google Play. No additional configuration in Intune is required.

3.  **Enroll devices**:

    -   **Android** - Install the **Intune Company Portal** app from Microsoft Corporation available on [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612) and sign in with the Intune user credentials added above.

    -   **iOS and Mac OS X** - Install the **Microsoft Intune Company Portal** app from Microsoft Corporation available in the App Store and sign in with the Intune user credentials added above. View **Enrolled devices** to add your device.

    -   **Windows Phone 8.1**- Users install the **Company Portal** app from Microsoft Corporation available in the Windows Phone store and sign in with the Intune user credentials added above.  View **Enrolled devices** to add your device.

    -   **Windows Phone 8.0**  - Users click **system settings** &gt; **company apps**, and sign in with Intune user credentials added above. The company portal app is deployed to your phone.

    If prompted for a **Server address**, type “manage.microsoft.com”.

4.  Open the company portal on the mobile device, choose **Apps**, and then install **Microsoft Skype**.

To learn more about mobile device management using [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], see [Get ready to enroll devices in Microsoft Intune](../Topic/Get-ready-to-enroll-devices-in-Microsoft-Intune.md).

## Post-configuration tasks
After you complete the initial configuration steps for an Intune  paid subscription, you should consider enabling additional mobile device management functionality.

-   **Connect Exchange to Intune:** For users with mobile devices  that haven't  enrolled in Intune, you can enable Exchange ActiveSync management using a connector for on-premises Exchange and for Exchange Online in  Microsoft Office 365. The Exchange connector connects you with your Exchange deployment and lets you manage mobile devices through the Intune administration console. To learn more about the Exchange connector, see [Mobile device management with Exchange ActiveSync and Microsoft Intune](../Topic/Mobile-device-management-with-Exchange-ActiveSync-and-Microsoft-Intune.md).

-   **Intune reports:** Microsoft Intune provides alerts and reports that you can use to help monitor devices, as well as software license status and actions that affect devices (such as wiping a device).  To learn more about reporting, see [Monitoring and reports with Microsoft Intune](../Topic/Monitoring-and-reports-with-Microsoft-Intune.md).

-   **Protecting company resources:** After you've configured Intune and enrolled your devices, you'll want to make sure that you're protecting devices against data loss and other threats. To learn more about protecting resources, see [Protect data and devices with Microsoft Intune](../Topic/Protect-data-and-devices-with-Microsoft-Intune.md).

## See Also
[Start using Microsoft Intune](../Topic/Start-using-Microsoft-Intune.md)

