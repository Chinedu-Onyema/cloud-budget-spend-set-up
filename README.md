# AWS Budgets Implementation Guide

This repository contains step-by-step instructions for setting up **AWS Budgets** to monitor costs, plan service usage, and implement a proactive alert system to prevent unexpected cloud expenditure.

## INTRODUCTION

In cloud engineering, cost management is a critical skill for engineers and organizations of all sizes. AWS Budgets gives you the ability to set custom budgets that alert you and your team when your costs or usage exceed (or are forecasted to exceed) your budgeted amount.

A primary benefit of setting up AWS Budgets is **avoiding payment for idle infrastructure**. It is common practice to spin up resources for development or learning purposes and subsequently forget to terminate them. AWS Budgets acts as a safeguard, reminding you to review and terminate existing infrastructure when costs rise unexpectedly.

AWS Budgets data is typically updated three times a day.

#### PDF GUIDE: [AWS BUDGETS .pdf](https://github.com/user-attachments/files/33021279/15.AWS.BUDGETS.pdf)

#### WATCH VIDEO WALKTHROUGH HERE: https://youtu.be/wVc_oUoY2p4



## PREREQUISITE

Before you begin, ensure you have:

*   An active [AWS Account](https://aws.amazon.com/).
*   Console access with sufficient permissions to view and manage AWS Budgets (e.g., `AdministratorAccess` or an IAM policy with `budgets:*` permissions).

## WALKTHROUGH STEPS

Follow these instructions to create a customized cost budget and configure email alerts.

### Step 1: Navigate to AWS Budgets

1.  Log in to the **AWS Management Console**.
2.  In the navigation bar search bar located at the top of the screen, type **budgets**.
3.  Select **AWS Budgets** from the search results to navigate to the dashboard.

### Step 2: Start the Budget Creation Wizard

1.  On the AWS Budgets dashboard, click the orange **Create budget** button.

### Step 3: Select Budget Setup Method

1.  In the *Choose budget setup* page, you are presented with options. For this tutorial, select **Customized (Advanced)**. This allows granular control over the budget parameters.

### Step 4: Select Budget Type

1.  Under *Budget types*, ensure **Cost budgets (Recommended)** is selected. This monitors the aggregate costs of your infrastructure.
2.  Click **Next** to proceed.

### Step 5: Configure Budget Details

Define the specifics of your budget on the *Set your budget* page.

1.  **Budget name:** Enter a meaningful name (e.g., `infrastructure-cost-budget`).
2.  **Period:** Set the period to **Monthly**.
3.  **Budget renewal type:** Select **Recurring budget**. This ensures the budget resets on the first day of every month automatically.
4.  **Budgeting method:** Select **Fixed**. This tracks a specific, static amount of spend.
    *   *Note: Alternatively, you can select 'Planned' if you are trying to align with anticipated organizational demands.*
5.  **Enter your budget amount:** Input a realistic monetary amount for your intended spend. For this learning exercise, you might choose a low amount (e.g., $10.00), but in a production environment, this should align with your organizational cost planning.

### Step 6: Define Budget Scope

1.  Under *Budget scope*, select **All AWS services (Recommended)**. This ensures the budget tracks costs across every service available in AWS, rather than a subset.
2.  Under *Aggregate cost by*, select **unblended cost**. This allows you to track actual accrued costs in near-real-time as services are used.
3.  Click **Next** to proceed.

### Step 7: Configure Alerts

Establish the threshold at which AWS will notify you of your spending.

1.  In the *Configure alerts* page, locate *Alert #1*. Click the dropdown to enter a threshold.
2.  **Threshold:** You can choose Percentage or Absolute Value. For this tutorial, select **Absolute value** and set the threshold to **0.25** dollars (or half of the amount you set in Step 5).
3.  **Trigger:** Select **Actual**. This means the alert will trigger only when your actual accumulated spend reaches $0.25.
4.  **Email recipients:** Enter the email address(es) responsible for the infrastructure budget (e.g., your email address for this tutorial).
5.  Click **Next**.

### Step 8: Review and Create

1.  Review the configuration settings you selected on the *Review alerts* page.
2.  If all details are correct, click the **Create budget** button.

## CONCLUSION

You have successfully created a customized AWS Cost Budget. You will now receive an email notification from AWS if your actual infrastructure spend exceeds the configured threshold of $0.25 for the current month.
