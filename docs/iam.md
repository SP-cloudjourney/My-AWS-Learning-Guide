<h1 style="color: #FF9900;">IAM - Identity and Access Management</h1>

## What Is IAM?

IAM stands for Identity and Access Management. It is the AWS service that allows you to manage who can access your resources and what they are allowed to do. Instead of sharing the root account, IAM gives you the ability to create individual users with their own login credentials. Each user can have their own level of access depending on what you assign to them.

IAM is one of the most important services for securing your account, and it forms the foundation of access control in AWS.

## Why Use IAM Instead of the Root Account?

The root account has unrestricted access to your entire AWS environment. If that account is compromised, everything in your account could be exposed, changed, or deleted.

For that reason, AWS recommends using the root account only for a few specific tasks, such as setting up billing and enabling multi-factor authentication. For everything else, you should use IAM users with defined permissions.

## Key Concepts in IAM

Here are a few important terms to understand before we create any users:

### Users

A user represents a person who needs access to your AWS environment. Each user can have their own username, password, and access keys. You can give users access to the AWS Console, to the AWS CLI (Command Line Interface) [which I cover here](cli.md), or both.

### Groups

A group is a collection of users. Instead of assigning permissions to each user individually, you can assign permissions to the group and then add users to that group. For example, you might create an "Admins" group and assign administrator permissions to it. Then, anyone you add to the group will automatically inherit those permissions.

### Policies

A policy is a document that defines what actions are allowed or denied. These policies can be attached to users, groups, or roles. AWS provides many pre-built policies that you can use, such as AdministratorAccess or ReadOnlyAccess.

### A Closer Look at IAM Policies

IAM policies are what actually define the permissions given to a user, group, or role. They are written in JSON format, but most of the time you will use AWS's pre-built, managed policies.

Each policy contains a list of rules that describe what actions are allowed or denied, on which services, and under which conditions.

For example, the `AdministratorAccess` policy grants full access to all AWS services, while a policy like `AmazonS3ReadOnlyAccess` only allows viewing S3 content without the ability to delete or upload files.

You can attach policies directly to users, but it is usually better to assign them to groups. This makes permission management simpler and more consistent across users.

In later sections, we will look at how to view, understand, and even write custom policies if needed. For now, it is enough to know that policies are the building blocks of access control in AWS.

### Roles

A role is similar to a user but it is not tied to a specific person. Instead, it can be assumed by users or services when needed. Roles are often used when one AWS service needs permission to interact with another service, or when you want to allow temporary access.

For now, we will focus on creating users and groups. Roles will be explored in a future section.

## How to Create an IAM User

Here is how I created a new IAM user with administrator permissions:

1. In the AWS Console, go to **IAM** by typing it in the search bar at the top

2. In the left-hand menu, choose **Users**, then click **Add users**

3. Enter a username (for example, `admin-user`), then tick the boxes for **AWS Management Console access** and **Programmatic access**

4. Create a custom password or let AWS generate one. I chose to require a password reset on first sign-in

5. For permissions, choose **Add user to group**, then create a new group called `Admins` (or similar)

6. Attach the **AdministratorAccess** policy to the group

7. Complete the user creation process and make note of the **IAM sign-in URL**. This is a special login link that IAM users must use. Bookmark it for future use

### The Principle of Least Privilege

When assigning permissions in IAM, it is considered best practice to follow the principle of least privilege. This means giving users only the permissions they need to complete their tasks, and nothing more.

For example, if someone only needs to view files in S3, you should assign a read-only policy for S3 rather than full administrative access. By limiting what each user can do, you reduce the risk of mistakes or security issues if an account is ever compromised.

In this guide, we are using an administrator user for simplicity, but it is important to be aware that in real environments, permissions should always be kept to the minimum necessary.

### Access Keys and Programmatic Access

When creating an IAM user, you may have noticed the option to allow programmatic access. This type of access is used when interacting with AWS outside of the web console, such as through the AWS Command Line Interface (CLI) or Software Development Kit (SDKs)  like Python’s boto3 or JavaScript’s AWS SDK.

If programmatic access is enabled, AWS generates a set of access keys for the user. These consist of an **Access Key ID** and a **Secret Access Key**. Together, these act like a username and password for connecting to AWS from tools and scripts.

Access keys should be kept secure and never shared. If you lose them, you can delete and regenerate a new set in the IAM console.

We will explore how to install, configure, and use the AWS CLI [in this section](cli.md). For now, it is important to understand that these access keys allow the user to connect to AWS in other ways beyond the console.

## Best Practices

After creating your IAM user:

- Log in with your new IAM user and confirm you have access to the AWS Console
- Enable multi-factor authentication for this user, just as you did with the root account
- Do not share your IAM credentials with anyone else
- Only use the root account when absolutely necessary

## What We Will Use Going Forward

From this point on, I will be using the IAM user we just created for all examples and walkthroughs, unless stated otherwise. This approach helps keep the root account safe and encourages secure habits from the beginning.

## Summary

IAM allows you to control who can access your AWS environment and what they can do. By creating users and assigning them to groups, you can avoid using the root account for everyday tasks. This not only improves security, but also prepares you for how access is managed in real-world cloud environments.

## Download Flashcards for This Section

You can download the flashcards I created for IAM in a format ready to import into Anki:

[📥 Download IAM Flashcards (TSV)](docs/flashcards/IAM_flashcards_for_Anki.tsv.zip)
