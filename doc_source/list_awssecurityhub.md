# Actions, Resources, and Condition Keys for AWS Security Hub<a name="list_awssecurityhub"></a>

AWS Security Hub \(service prefix: `securityhub`\) provides the following service\-specific resources, actions, and condition context keys for use in IAM permission policies\.

References:
+ Learn how to [configure this service](https://docs.aws.amazon.com/securityhub/latest/userguide/)\.
+ View a [list of the API operations available for this service](https://docs.aws.amazon.com/securityhub/1.0/APIReference/)\.
+ Learn how to protect this service and its resources by [using IAM](https://docs.aws.amazon.com/securityhub/latest/userguide/securityhub-access.html) permission policies\.

**Topics**
+ [Actions Defined by AWS Security Hub](#awssecurityhub-actions-as-permissions)
+ [Resources Defined by AWS Security Hub](#awssecurityhub-resources-for-iam-policies)
+ [Condition Keys for AWS Security Hub](#awssecurityhub-policy-keys)

## Actions Defined by AWS Security Hub<a name="awssecurityhub-actions-as-permissions"></a>

You can specify the following actions in the `Action` element of an IAM policy statement\. By using policies, you define the permissions for anyone performing an operation in AWS\. When you use an action in a policy, you usually allow or deny access to the API operation or CLI command with the same name\. However, in some cases, a single action controls access to more than one operation\. Alternatively, some operations require several different actions\. For details about the columns in the following table, see [The Actions Table](reference_policies_actions-resources-contextkeys.md#actions_table)\.


****  

| Actions | Description | Access Level | Resource Types \(\*required\) | Condition Keys | Dependent Actions | 
| --- | --- | --- | --- | --- | --- | 
|   [ AcceptInvitation ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_AcceptInvitation.html)  | Accepts the invitation to be monitored by a master Security Hub account\. | Write |  |  |  | 
|   [ BatchDisableStandards ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_BatchDisableStandards.html)  | Disables the standards specified by the standards subscription ARNs\. | Write |   [ standards\-subscription\* ](#awssecurityhub-standards-subscription)   |  |  | 
|   [ BatchEnableStandards ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_BatchEnableStandards.html)  | Enables the standards specified by the standards ARNs\. | Write |   [ standard\* ](#awssecurityhub-standard)   |  |  | 
|   [ BatchImportFindings ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_BatchImportFindings.html)  | Imports security findings that are generated by the integrated third\-party products into Security Hub\. | Write |  |   [ securityhub:TargetAccount ](#awssecurityhub-securityhub_TargetAccount)   |  | 
|   [ CreateInsight ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_CreateInsight.html)  | Creates an insight, which is a collection of related findings defined by an aggregation statement and optional filters\. | Write |  |  |  | 
|   [ CreateMembers ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_CreateMembers.html)  | Creates member Security Hub accounts in the current AWS account \(which becomes the master Security Hub account\) that has Security Hub enabled\. | Write |  |  |  | 
|   [ DeclineInvitations ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_DeclineInvitations.html)  | Declines invitations that are sent to this AWS account \(invitee\) by the AWS accounts \(inviters\) that are specified by the account IDs\. | Write |  |  |  | 
|   [ DeleteInsight ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_DeleteInsight.html)  | Deletes an insight that is specified by the insight ARN\. | Write |   [ insight\* ](#awssecurityhub-insight)   |  |  | 
|   [ DeleteInvitations ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_DeleteInvitations.html)  | Deletes invitations that are sent to this AWS account \(invitee\) by the AWS accounts \(inviters\) that are specified by their account IDs\. | Write |  |  |  | 
|   [ DeleteMembers ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_DeleteMembers.html)  | Deletes the Security Hub member accounts that are specified by the account IDs\. | Write |  |  |  | 
|   [ DescribeProducts ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_DescribeProducts.html)  | Returns information about the products available that you can subscribe to\. | Read |  |  |  | 
|   [ DisableImportFindingsForProduct ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_DisableImportFindingsForProduct.html)  | Stops you from being able to import findings generated by the integrated third\-party providers into Security Hub\. | Write |   [ product\* ](#awssecurityhub-product)   |  |  | 
|   [ DisableSecurityHub ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_DisableSecurityHub.html)  | Disables the AWS Security Hub Service\. | Write |  |  |  | 
|   [ DisassociateFromMasterAccount ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_DisassociateFromMasterAccount.html)  | Disassociates the current Security Hub member account from its master account\. | Write |  |  |  | 
|   [ DisassociateMembers ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_DisassociateMembers.html)  | Disassociates the Security Hub member accounts that are specified by the account IDs from their master account\. | Write |  |  |  | 
|   [ EnableImportFindingsForProduct ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_EnableImportFindingsForProduct.html)  | Enables you to import findings generated by the integrated third\-party providers into Security Hub\. | Write |   [ product\* ](#awssecurityhub-product)   |  |  | 
|   [ EnableSecurityHub ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_EnableSecurityHub.html)  | Enables the AWS Security Hub service\. | Write |  |  |  | 
|   [ GetEnabledStandards ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_GetEnabledStandards.html)  | Lists and describes enabled standards\. | List |  |  |  | 
|   [ GetFindings ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_GetFindings.html)  | Lists and describes Security Hub\-aggregated findings that are specified by filter attributes\. | Read |  |  |  | 
|   [ GetInsightResults ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_GetInsightResults.html)  | Lists the results of the Security Hub insight specified by the insight ARN\. | Read |   [ insight\* ](#awssecurityhub-insight)   |  |  | 
|   [ GetInsights ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_GetInsights.html)  | Lists and describes insights that are specified by insight ARNs\. | List |   [ insight\* ](#awssecurityhub-insight)   |  |  | 
|   [ GetInvitationsCount ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_GetInvitationsCount.html)  | Returns the count of all Security Hub membership invitations that were sent to the current member account, not including the currently accepted invitation\. | Read |  |  |  | 
|   [ GetMasterAccount ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_GetMasterAccount.html)  | Provides the details for the Security Hub master account to the current member account\. | Read |  |  |  | 
|   [ GetMembers ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_GetMembers.html)  | Returns the details on the Security Hub member accounts that are specified by the account IDs\. | Read |  |  |  | 
|   [ InviteMembers ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_InviteMembers.html)  | Invites other AWS accounts to enable Security Hub and become Security Hub member accounts\. When an account accepts the invitation and becomes a member account, the master account can view and manage the Security Hub findings of the member account\. | Write |  |  |  | 
|   [ ListEnabledProductsForImport ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_ListEnabledProductsForImport.html)  | Lists all Security Hub integrated third\-party findings providers\. | List |  |  |  | 
|   [ ListInvitations ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_ListInvitations.html)  | Lists all Security Hub membership invitations that were sent to the current AWS account\. | List |  |  |  | 
|   [ ListMembers ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_ListMembers.html)  | Lists details about all member accounts for the current Security Hub master account\. | List |  |  |  | 
|   [ ListProductSubscribers ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_ListProductSubscribers.html)  | Returns a list of account IDs that are subscribed to the product\. | List |  |  |  | 
|   [ UpdateFindings ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_UpdateFindings.html)  | Updates the AWS Security Hub\-aggregated findings specified by the filter attributes\. | Write |  |  |  | 
|   [ UpdateInsight ](https://docs.aws.amazon.com/securityhub/1.0/APIReference/API_UpdateInsight.html)  | Updates the AWS Security Hub insight specified by the insight ARN\. | Write |   [ insight\* ](#awssecurityhub-insight)   |  |  | 

## Resources Defined by AWS Security Hub<a name="awssecurityhub-resources-for-iam-policies"></a>

The following resource types are defined by this service and can be used in the `Resource` element of IAM permission policy statements\. Each action in the [Actions table](#awssecurityhub-actions-as-permissions) identifies the resource types that can be specified with that action\. A resource type can also define which condition keys you can include in a policy\. These keys are displayed in the last column of the table\. For details about the columns in the following table, see [The Resource Types Table](reference_policies_actions-resources-contextkeys.md#resources_table)\.


****  

| Resource Types | ARN | Condition Keys | 
| --- | --- | --- | 
|   [ insight ](https://docs.aws.amazon.com/securityhub/latest/userguide/securityhub-access.html#resources)  |  arn:$\{Partition\}:securityhub:$\{Region\}:$\{Account\}:insight/$\{CompanyId\}/$\{ProductId\}/$\{UniqueId\}  |  | 
|   [ standard ](https://docs.aws.amazon.com/securityhub/latest/userguide/securityhub-access.html#resources)  |  arn:$\{Partition\}:securityhub:::ruleset/$\{StandardsName\}/v/$\{StandardsVersion\}  |  | 
|   [ standards\-subscription ](https://docs.aws.amazon.com/securityhub/latest/userguide/securityhub-access.html#resources)  |  arn:$\{Partition\}:securityhub:$\{Region\}:$\{Account\}:subscription/$\{StandardsName\}/v/$\{StandardsVersion\}  |  | 
|   [ product\-subscription ](https://docs.aws.amazon.com/securityhub/latest/userguide/securityhub-access.html#resources)  |  arn:$\{Partition\}:securityhub:$\{Region\}:$\{Account\}:product\-subscription/$\{Company\}/$\{ProductId\}  |  | 
|   [ product ](https://docs.aws.amazon.com/securityhub/latest/userguide/securityhub-access.html#resources)  |  arn:$\{Partition\}:securityhub:$\{Region\}:$\{Account\}:product/$\{Company\}/$\{ProductId\}  |  | 

## Condition Keys for AWS Security Hub<a name="awssecurityhub-policy-keys"></a>

AWS Security Hub defines the following condition keys that can be used in the `Condition` element of an IAM policy\. You can use these keys to further refine the conditions under which the policy statement applies\. For details about the columns in the following table, see [The Condition Keys Table](reference_policies_actions-resources-contextkeys.md#context_keys_table)\.

To view the global condition keys that are available to all services, see [Available Global Condition Keys](reference_policies_condition-keys.html#AvailableKeys) in the *IAM Policy Reference*\.


****  

| Condition Keys | Description | Type | 
| --- | --- | --- | 
|   [ securityhub:TargetAccount ](https://docs.aws.amazon.com/securityhub/latest/userguide/securityhub-access.html#conditions)  | The ID of the AWS account into which you want to import findings\. In the AWS Security Finding format, this field is called AwsAccountId | String | 