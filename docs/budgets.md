<h1 style="color: #FF9900;">Setting budgets and billing alerts</h1>

# Staying Within the Free Tier

When you first create an AWS account, it is easy to accidentally use paid services without realising it. That is why one of the first things I did was set up a billing budget and email alerts. This helps me stay within the Free Tier and avoid unexpected charges.

## What Is the Free Tier?

AWS offers a Free Tier that allows you to use many services at no cost for the first twelve months. This includes:

- 750 hours per month of EC2 t2.micro or t3.micro instances. If you're not familiar with EC2, I cover it in more detail [in this section](ec2.md)
- 5 GB of standard S3 storage. You can read about S3 and how it works [on this page](s3.md)
- 1 million Lambda requests. I explain Lambda functions [here](lambda.md)
- 25 GB of DynamoDB storage. You will find an overview of DynamoDB [in this section](dynamodb.md)

The Free Tier is generous for learning, but it is not unlimited. If you go over the included usage, you will be charged.

## Why Set a Budget?

Budgets help you track how much you are spending, or are about to spend. Even if you plan to stay within the Free Tier, it is useful to:

- Receive email alerts when you are nearing usage limits
- Keep an eye on any unexpected costs
- Learn how AWS billing works in practice

## How to Create a Budget in AWS

1. Go to the **Billing Dashboard**:  [https://console.aws.amazon.com/billing](https://console.aws.amazon.com/billing)

2. In the left-hand menu, click **Budgets**

3. Click **Create a budget** and select **Cost budget**

4. Name your budget (for example, “Free Tier Budget”) and choose **Recurring monthly**

5. Set a fixed monthly amount. I chose **£1.00**, so I would be notified of any cost at all

6. Under **Alerts**, set up email notifications for when your actual cost goes over £0.50 and again at £1.00

7. Review and confirm to create the budget

## Setting Free Tier Usage Alerts (Optional but Helpful)

1. Go to the **Billing Preferences** page

2. Tick the box to **Receive Free Tier Usage Alerts**

3. Enter your email address and save

You will now receive alerts when your Free Tier usage reaches 85 percent and 100 percent.

## My Setup

I personally set my budget at £1.00 with alerts at £0.50 and £1.00. I also turned on Free Tier usage alerts so I would be notified before I go over any limits. This gives me peace of mind while I explore services and experiment in my account.

## Summary

Setting a budget and turning on usage alerts is a quick but valuable step when starting with AWS. It helps you stay in control, avoid unnecessary charges, and build good habits early in your cloud learning journey.