---
title: 'Tutorial: Azure Active Directory single sign-on (SSO) integration with Templafy SAML2 | Microsoft Docs'
description: Learn how to configure single sign-on between Azure Active Directory and Templafy SAML2.
services: active-directory
author: jeevansd
manager: CelesteDG
ms.reviewer: celested
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.topic: tutorial
ms.date: 06/23/2020
ms.author: jeedes
---

# Tutorial: Azure Active Directory single sign-on (SSO) integration with Templafy SAML2

In this tutorial, you'll learn how to integrate Templafy SAML2 with Azure Active Directory (Azure AD). When you integrate Templafy SAML2 with Azure AD, you can:

* Control in Azure AD who has access to Templafy SAML2.
* Enable your users to be automatically signed-in to Templafy SAML2 with their Azure AD accounts.
* Manage your accounts in one central location - the Azure portal.

To learn more about SaaS app integration with Azure AD, see [What is application access and single sign-on with Azure Active Directory](../manage-apps/what-is-single-sign-on.md).

## Prerequisites

To get started, you need the following items:

* An Azure AD subscription. If you don't have a subscription, you can get a [free account](https://azure.microsoft.com/free/).
* Templafy SAML2 single sign-on (SSO) enabled subscription.

## Scenario description

In this tutorial, you configure and test Azure AD SSO in a test environment.

* Templafy SAML2 supports **SP** initiated SSO
* Templafy SAML2 supports **Just In Time** user provisioning

## Adding Templafy SAML2 from the gallery

To configure the integration of Templafy SAML2 into Azure AD, you need to add Templafy SAML2 from the gallery to your list of managed SaaS apps.

1. Sign in to the [Azure portal](https://portal.azure.com) using either a work or school account, or a personal Microsoft account.
1. On the left navigation pane, select the **Azure Active Directory** service.
1. Navigate to **Enterprise Applications** and then select **All Applications**.
1. To add new application, select **New application**.
1. In the **Add from the gallery** section, type **Templafy SAML2** in the search box.
1. Select **Templafy SAML2** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

## Configure and test Azure AD single sign-on for Templafy SAML2

Configure and test Azure AD SSO with Templafy SAML2 using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between an Azure AD user and the related user in Templafy SAML2.

To configure and test Azure AD SSO with Templafy SAML2, complete the following building blocks:

1. **[Configure Azure AD SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    * **[Create an Azure AD test user](#create-an-azure-ad-test-user)** - to test Azure AD single sign-on with B.Simon.
    * **[Assign the Azure AD test user](#assign-the-azure-ad-test-user)** - to enable B.Simon to use Azure AD single sign-on.
1. **[Configure Templafy SAML2 SSO](#configure-templafy-saml2-sso)** - to configure the single sign-on settings on application side.
    * **[Create Templafy SAML2 test user](#create-templafy-saml2-test-user)** - to have a counterpart of B.Simon in Templafy SAML2 that is linked to the Azure AD representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

## Configure Azure AD SSO

Follow these steps to enable Azure AD SSO in the Azure portal.

1. In the [Azure portal](https://portal.azure.com/), on the **Templafy SAML2** application integration page, find the **Manage** section and select **single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, click the edit/pen icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, enter the values for the following fields:

    In the **Sign-on URL** text box, type a URL using the following pattern:
    `https://<CLIENTSUBDOMAIN>.templafy.com`

	> [!NOTE]
	> The value is not real. Update the value with the actual Sign-On URL. Contact [Templafy SAML2 Client support team](mailto:support@templafy.com) to get the value. You can also refer to the patterns shown in the **Basic SAML Configuration** section in the Azure portal.

1. Templafy SAML2 application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes.

	![image](common/default-attributes.png)

1. In addition to above, Templafy SAML2 application expects few more attributes to be passed back in SAML response which are shown below. These attributes are also pre populated but you can review them as per your requirements.

	| Name | Source Attribute| Namespace  |
	| ---------------| --------------- | --------- |
	| givenname | user.givenname | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims` |
	| surname | user.surname | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims`|
	| emailaddress | user.mail | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims`
	| streetaddress | user.streetaddress | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims`|
	| city | user.city | `http://schemas.templafy.com/2016/06/identity/claims`|
	| postalcode | user.postalcode | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims`|
	| stateorprovince | user.state | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims`|
	| country | user.country | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims`|
	| jobtitle | user.jobtitle | `http://schemas.templafy.com/2016/06/identity/claims`|
	| department | user.department | `http://schemas.templafy.com/2016/06/identity/claims`|
	| phonenumber | user.telephonenumber | `http://schemas.templafy.com/2016/06/identity/claims` |
	| facsimilenumber | user.facsimiletelephonenumber | `http://schemas.templafy.com/2016/06/identity/claims`|
	| upn | user.userprincipalname | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims`|
	| nameidentifier | user.mail | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims`|
	| | |

1. On the **Set up single sign-on with SAML** page, In the **SAML Signing Certificate** section, click copy button to copy **App Federation Metadata Url** and save it on your computer.

	![The Certificate download link](common/copy-metadataurl.png)

### Create an Azure AD test user

In this section, you'll create a test user in the Azure portal called B.Simon.

1. From the left pane in the Azure portal, select **Azure Active Directory**, select **Users**, and then select **All users**.
1. Select **New user** at the top of the screen.
1. In the **User** properties, follow these steps:
   1. In the **Name** field, enter `B.Simon`.  
   1. In the **User name** field, enter the username@companydomain.extension. For example, `B.Simon@contoso.com`.
   1. Select the **Show password** check box, and then write down the value that's displayed in the **Password** box.
   1. Click **Create**.

### Assign the Azure AD test user

In this section, you'll enable B.Simon to use Azure single sign-on by granting access to Templafy SAML2.

1. In the Azure portal, select **Enterprise Applications**, and then select **All applications**.
1. In the applications list, select **Templafy SAML2**.
1. In the app's overview page, find the **Manage** section and select **Users and groups**.

   ![The "Users and groups" link](common/users-groups-blade.png)

1. Select **Add user**, then select **Users and groups** in the **Add Assignment** dialog.

	![The Add User link](common/add-assign-user.png)

1. In the **Users and groups** dialog, select **B.Simon** from the Users list, then click the **Select** button at the bottom of the screen.
1. If you're expecting any role value in the SAML assertion, in the **Select Role** dialog, select the appropriate role for the user from the list and then click the **Select** button at the bottom of the screen.
1. In the **Add Assignment** dialog, click the **Assign** button.

## Configure Templafy SAML2 SSO

To configure single sign-on on **Templafy SAML2** side, you need to send the **App Federation Metadata Url** to [Templafy SAML2 support team](mailto:support@templafy.com). They set this setting to have the SAML SSO connection set properly on both sides.

### Create Templafy SAML2 test user

In this section, a user called B.Simon is created in Templafy SAML2. Templafy SAML2 supports just-in-time user provisioning, which is enabled by default. There is no action item for you in this section. If a user doesn't already exist in Templafy SAML2, a new one is created after authentication.

## Test SSO

In this section, you test your Azure AD single sign-on configuration using the Access Panel.

When you click the Templafy SAML2 tile in the Access Panel, you should be automatically signed in to the Templafy SAML2 for which you set up SSO. For more information about the Access Panel, see [Introduction to the Access Panel](../user-help/my-apps-portal-end-user-access.md).

## Additional resources

- [ List of Tutorials on How to Integrate SaaS Apps with Azure Active Directory ](./tutorial-list.md)

- [What is application access and single sign-on with Azure Active Directory? ](../manage-apps/what-is-single-sign-on.md)

- [What is conditional access in Azure Active Directory?](../conditional-access/overview.md)

- [Try Templafy SAML2 with Azure AD](https://aad.portal.azure.com/)

- [What is session control in Microsoft Cloud App Security?](/cloud-app-security/proxy-intro-aad)