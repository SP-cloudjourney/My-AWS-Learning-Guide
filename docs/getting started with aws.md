<h1 style="color: #FF9900;">Getting started with AWS</h1>

# Creating a Root Account

## What Is a Root Account?

When you sign up for AWS for the first time, you are creating what is called the root account. This is the main owner account for your entire AWS environment. It has full access to everything, including services, settings, and billing.

You can think of it like the admin login on your personal computer, except it controls all the cloud resources in your AWS setup. Whoever has access to the root account has complete control.

## Why It Matters

Because the root account has full permissions, it is also the most sensitive. If someone gains access to it without authorisation, they can make changes to your entire environment. AWS recommends using the root account only when absolutely necessary, such as for setting up your account and enabling security features. After that, you should avoid using it for daily tasks and instead work through limited-access accounts.

## How to Create a Root Account

You do not need any technical experience to get started. All you need is an email address and a payment method.

1. Go to [aws.amazon.com](https://aws.amazon.com)
2. Click **Create an AWS Account**
3. Enter your email address and choose a password
4. Name your account (this can be anything you like, such as "My AWS Practice Lab")
5. Add your contact and billing information
6. Select the Free Tier plan if you are just exploring

Once you complete these steps, you will have access to the AWS Management Console. This is the dashboard where you can launch and manage all your cloud services.

## Best Practices After Creating the Account

Once you have created your root account, it is important to secure it properly. Even if you are just using AWS for learning or experimentation, the root account has full access to everything. If someone else gains control of it, they could delete your resources, access your billing information, or launch expensive services without your permission.

### Enable Multi-Factor Authentication (MFA)

Multi-Factor Authentication, or MFA, adds an extra layer of security. In addition to your password, you will be asked to enter a code from your phone each time you log in.

To enable MFA on your root account:

1. Sign in to the AWS Management Console using your root account
2. In the top-right corner, click on your account name and choose **Security Credentials**
3. Scroll down to **Multi-Factor Authentication (MFA)** and click **Activate MFA**
4. Choose **Virtual MFA device**
5. Use an authenticator app on your phone (such as **Google Authenticator**, **Authy**, or **Microsoft Authenticator**) to scan the QR code
6. Enter the two codes shown in your app to complete the setup

After this, each time you log in, AWS will ask for a code from your MFA app. This helps protect your account even if someone knows your password.

### Use a Password Manager

The root account password should be long, complex, and unique. A password manager, such as Bitwarden, 1Password, or KeePass, can help you generate and store a strong password securely.

### Limit Use of the Root Account

After the initial setup, avoid logging in with the root account unless absolutely necessary. For all daily tasks, you should create an IAM user ([which I cover here](iam.md)) and grant it only the permissions it needs.

This reduces your risk and follows AWS best practice for account security.

### Set a Budget and Billing Alerts

Although not strictly a security measure, setting a budget protects you from accidental charges. I enabled the Free Tier and also created a budget so I would be alerted if I ever go over. I will explain how to do this in [Setting budgets and billing alerts](budgets.md).

## Summary

The root account is the most powerful access point to your AWS environment. It is necessary for setting up your account, but it should be used carefully and only when needed. Once your initial setup is complete, focus on using more secure, limited-access accounts for your daily tasks.