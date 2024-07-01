# Multi-Factor Authentication (MFA) for Oracle Cloud Infrastructure Users
It's more important than ever to protect your assets in the cloud. Many customers already use identity providers like Oracle Identity Cloud Service (IDCS), Microsoft Active Directory Federation Services (AD FS), and [Okta](http://blogs.oracle.com/cloud-infrastructure/oracle-cloud-simplifies-identity-management-with-enhanced-okta-support) to control access to Oracle Cloud Infrastructure. Customers set up multi-factor authentication with these identity providers to help keep out unwanted visitors. The OCI Control Plane also support multi-factor authentication natively.

In this lab, you will add a temporary one-time password (TOTP) device to your account to enable MFA. All that you need to set up TOTP is a mobile device with a TOTP application like Oracle Mobile Authenticator (available on [iTunes](http://itunes.apple.com/us/app/oracle-mobile-authenticator/id835904829?mt=8) and [Google Play](http://play.google.com/store/apps/details?id=oracle.idm.mobile.authenticator&hl=en_US)).  

## Tasks

### Task 1: Sign in to your Oracle Cloud Infrastructure account

[Sign into your Oracle Cloud Infrastructure tenancy](https://console.us-ashburn-1.oraclecloud.com/) as a native user (that is, don't use any single sign-on federation that you might have set up).

![ociLogin](images/ociLogin.png)

### Task 2: Visit your user profile page

In the upper-right corner of the Console, click the Profile icon and select your profile ID.

![usericon](images/usericon.png)

### Task 3: Click to enable multi-factor authentication

Click the **Enable Multi-Factor Authentication** tab. You are given instructions to install a TOTP app on your mobile device.

![](https://cdn.app.compendium.com/uploads/user/e7c690e8-6ff9-102a-ac6d-e4aebca50425/e47946a2-cb58-49f4-95c7-b98adfe35806/Image/c0546ec8f9cac20b7b0b9af69c90e66f/3___enable_mfa__cropped____newiii.png)

### Task 4: Install a TOTP app on your mobile device

For your TOTP app, try Oracle Mobile Authenticator (available on [iTunes](http://itunes.apple.com/us/app/oracle-mobile-authenticator/id835904829?mt=8) and [Google Play](http://play.google.com/store/apps/details?id=oracle.idm.mobile.authenticator&hl=en_US)).

![](https://cdn.app.compendium.com/uploads/user/e7c690e8-6ff9-102a-ac6d-e4aebca50425/e47946a2-cb58-49f4-95c7-b98adfe35806/Image/c49263dcc99d7af50f7947cfeba12ee4/4___app_store__cropped____new.png)

### Task 5: Use your TOTP app to get the code

Use the barcode scan function in the app to scan the barcode on the Enable Multi-Factor Authentication dialog box in the Console.

![](https://cdn.app.compendium.com/uploads/user/e7c690e8-6ff9-102a-ac6d-e4aebca50425/e47946a2-cb58-49f4-95c7-b98adfe35806/Image/b7afc634bc1e1bb355ce203ea2e5dc59/5___enroll_device___newii.png)

### Task 6: Enter the code into the confirmation dialog box

Enter the verification code that the app generates into the **Verification Code** field in the Enable Multi-Factor Authentication dialog box. Then, click **Enable** and then **Close**.

![](https://cdn.app.compendium.com/uploads/user/e7c690e8-6ff9-102a-ac6d-e4aebca50425/e47946a2-cb58-49f4-95c7-b98adfe35806/Image/7321fbb3a934aa5d4611797e96678474/6___confirm___new.png)

You're done! The next time that you sign in to this account, you will be prompted to enter the code from your TOTP app.

If you ever lose the device, any administrator for your tenancy can disable TOTP on your behalf and allow you to sign in. You just need to set up multi-factor authentication again when you sign back in.

## Acknowledgements

This lab is based on [Multi-Factor Authentication for Oracle Cloud Infrastructure Users](https://blogs.oracle.com/cloud-infrastructure/multi-factor-authentication-for-oracle-cloud-infrastructure-users).
