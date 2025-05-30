
# Guided Lab: Exploring AWS Identity and Access Management (IAM)

## Lab overview and objectives

In this lab, you explore users and groups and inspect the associated policies in the AWS Identity and Access Management (IAM) service. You also add users to the groups and verify the permissions that are inherited by them.

After completing this lab, you should be able to do the following:

-   Explore pre-created IAM users and groups.
    
-   Inspect IAM policies as they were applied to the pre-created groups.
    
-   Follow a real-world scenario, while adding users to groups with specific capabilities enabled.
    
-   Locate and use the IAM sign-in URL.
    
-   Test the effects of policies on service access.
    

## Duration

This lab requires approximately **40 minutes** to complete.

## AWS service restrictions

In this lab environment, access to AWS services and service actions might be restricted to the ones that are needed to complete the lab instructions. You might encounter errors if you attempt to access other services or perform actions beyond the ones that are described in this lab.

## Accessing the AWS Management Console

1.  At the top of these instructions, choose **Start Lab**.
    
    -   The lab session starts.
        
    -   A timer displays at the top of the page and shows the time remaining in the session.
        
        **Tip:** To refresh the session length at any time, choose **Start Lab** again before the timer reaches 0:00.
        
    -   Before you continue, wait until the circle icon to the right of the AWS link in the upper-left corner turns green. When the lab environment is ready, the **AWS Details** panel displays.
        
2.  To connect to the AWS Management Console, choose the **AWS** link in the upper-left corner above the terminal window.
    
    -   A new browser tab opens and connects you to the console.
        
        **Tip:** If a new browser tab does not open, a banner or icon is usually at the top of your browser with a message that says your browser is preventing the site from opening pop-up windows. Choose the banner or icon, and then choose **Allow pop-ups**.
        
3.  Arrange the AWS Management Console tab so that it displays alongside these instructions. Ideally, you have both browser tabs open at the same time so that you can follow the lab steps.
    

## Task 1: Explore the users and groups, and inspect policies

In this task, you explore the users and groups that were created for you in IAM.

4.  First, note the Region that you are in; for example, **N. Virginia**. The Region is displayed in the upper-right corner of the console page.
    
    You might need this information later in the lab.
    
5.  Choose the **Services** menu, locate the **Security, Identity, & Compliance** services, and choose **IAM**.
    
6.  In the navigation pane on the left, choose **Users**.
    
    The following IAM users were created for you:
    
    -   user-1
        
    -   user-2
        
    -   user-3
        
7.  Choose the name of **user-1**.
    
    -   This brings you to a summary page for user-1. The **Permissions** tab is displayed.
        
    -   Notice that user-1 does not have any permissions.
        
8.  Choose the **Groups** tab.
    
    Notice that user-1 also is not a member of any groups.
    
9.  Choose the **Security credentials** tab.
    
    Notice that user-1 is assigned a **Console password**. This allows the user to access the AWS Management Console.
    
10.  In the navigation pane on the left, choose **User groups**.
    
    The following groups were created for you:
    
    -   EC2-Admin
        
    -   EC2-Support
        
    -   S3-Support
        
11.  Choose the name of the **EC2-Support** group.
    
    This brings you to the summary page for the **EC2-Support** group.
    
12.  Choose the **Permissions** tab.
    
    This group has a managed policy called **AmazonEC2ReadOnlyAccess** associated with it. Managed policies are prebuilt policies (built either by AWS or by your administrators) that can be attached to IAM users and groups. When the policy is updated, the changes to the policy are immediately applied against all users and groups that are attached to the policy.
    
13.  Below **Policy Name**, choose the link for the **AmazonEC2ReadOnlyAccess** policy.
    
14.  Choose the **JSON** tab.
    
    -   A policy defines which actions are allowed or denied for specific AWS resources. This policy is granting permission to _List_ and _Describe_ (view) information about Amazon Elastic Compute Cloud (Amazon EC2), Elastic Load Balancing, Amazon CloudWatch, and Amazon EC2 Auto Scaling. This ability to view resources, but not modify them, is ideal for assigning to a support role.
        
    -   Statements in an IAM policy have the following basic structure:
        
        -   **Effect** says whether to _Allow_ or _Deny_ the permissions.
            
        -   **Action** specifies the API calls that can be made against an AWS service (for example, _cloudwatch:ListMetrics_).
            
        -   **Resource** defines the scope of entities covered by the policy rule (for example, a specific Amazon Simple Storage Service [Amazon S3] bucket or Amazon EC2 instance; an asterisk [ * ] means _any resource_).
            
15.  In the navigation pane on the left, choose **User groups**.
    
16.  Choose the name of the **S3-Support** group.
    
17.  Choose the **Permissions** tab.
    
    The S3-Support group has the **AmazonS3ReadOnlyAccess** policy attached.
    
18.  Below **Policy Name**, choose the link for the **AmazonS3ReadOnlyAccess** policy.
    
19.  Choose the **JSON** tab.
    
    This policy has permissions to _Get_ and _List_ for _all_ resources in Amazon S3.
    
20.  In the navigation pane on the left, choose **User groups**.
    
21.  Choose the name of the **EC2-Admin** group.
    
22.  Choose the **Permissions** tab.
    
    This group is different from the other two. Instead of a managed policy, the group has an _inline policy_, which is a policy assigned to just one user or group. Inline policies are typically used to apply permissions for specific situations.
    
23.  Below **Policy Name**, choose the name of the **EC2-Admin-Policy** policy.
    
24.  Choose the **JSON** tab.
    
    This policy grants permission to _Describe_ information about Amazon EC2 instances and the ability to _Start_ and _Stop_ instances.
    
25.  At the bottom of the screen, choose **Cancel** to close the policy, and then choose **Continue**.
    

## Business scenario

For the remainder of this lab, you work with these users and groups to enable permissions that support the following business scenario.

Your company is growing its use of AWS services and is using many Amazon EC2 instances and Amazon S3 buckets. You want to give access to new staff based on their job function, as indicated in the following table:


| User | In Group | In Group |
|--|--|--|--|
|user-1| S3-Support | Read-only access to Amazon S3 |
|user-2| EC2-Support | Read-only access to Amazon EC2 |
|user-3| EC2-Admin | View, Start, and Stop Amazon EC2 instances |



## Task 2: Add users to groups

You recently hired _user-1_ into a role where they will provide support for Amazon S3. In this task, you add them to the _S3-Support_ group so that they inherit the necessary permissions through the attached _AmazonS3ReadOnlyAccess_ policy.

Note: Ignore any "not authorized" errors that appear during this task. They are caused by your lab account having limited permissions and don't impact your ability to complete the lab.

### Task 2.1: Add user-1 to the S3-Support group

26.  In the left navigation pane, choose **User groups**.
    
27.  Choose the name of the **S3-Support** group.
    
28.  On the **Users** tab, choose **Add users**.
    
29.  Select **user-1**, and choose **Add users**.
    
    On the **Users** tab, notice that _user-1_ was added to the group.
    

### Task 2.2: Add user-2 to the EC2-Support group

You hired _user-2_ into a role where they will provide support for Amazon EC2. You will add them to the _EC2-Support_ group so that they inherit the necessary permissions through the attached _AmazonEC2ReadOnlyAccess_ policy.

30.  Use what you learned from the previous steps to add _user-2_ to the _EC2-Support_ group.
    
    Verify that _user-2_ is now part of the _EC2-Support_ group.
    

### Task 2.3: Add user-3 to the EC2-Admin group

You hired _user-3_ as your Amazon EC2 administrator to manage your EC2 instances. You will add them to the _EC2-Admin_ group so that they inherit the necessary permissions through the attached _EC2-Admin-Policy_.

31.  Use what you learned from the previous steps to add _user-3_ to the _EC2-Admin_ group.
    
    Verify that _user-3_ is now part of the _EC2-Admin_ group.
    
32.  In the navigation pane on the left, choose **User groups**.
    
    Each group should have a **1** in the **Users** column. This indicates the number of users in each group.
    
    If you do not have a **1** for the **Users** column for a group, revisit the previous steps to ensure that each user is assigned to a group, as shown in the table in the **Business scenario** section.
    

## Task 3: Sign in and test user permissions

In this task, you test the permissions inherited by IAM users in the console.

### Task 3.1: Get the console sign-in URL

33.  In the navigation pane on the left, choose **Dashboard**.
    
    Notice the **Sign-in URL for IAM users in this account** section at the top of the page. The sign-in URL looks similar to the following: **https://123456789012.signin.aws.amazon.com/console**
    
    This link can be used to sign in to the AWS account that you are currently using.
    
34.  Copy the sign-in link to a text editor.
    

### Task 3.2: Test user-1 permissions

35.  Open a private or incognito window in your browser.
    
36.  Paste the sign-in link into the private browser, and press ENTER.
    
    You will now sign-in as _user-1_, who was hired as your Amazon S3 storage support staff.
    
37.  Sign in with the following credentials:
    
    -   **IAM user name:**  `user-1`
        
    -   **Password:**  `Lab-Password1`
        
38.  Choose the **Services** menu, and choose **S3**. You can also use the search bar to find and choose **S3**.
    
39.  Choose the name of one of your buckets, and browse the contents.
    
    Because this user is part of the _S3-Support_ group in IAM, they have permissions to view a list of Amazon S3 buckets and their contents.
    
    Now, test whether the user has access to Amazon EC2.
    
40.  Choose the **Services** menu, and choose **EC2**. You can also use the search bar to find and choose **EC2**.
    
41.  In the left navigation pane, choose **Instances**.
    
    You cannot see any instances. Instead, an error message says _you are not authorized to perform this operation_. This user has not been assigned any permissions to use Amazon EC2.
    
    You will now sign in as _user-2_, who was hired as your Amazon EC2 support person.
    
42.  First, sign out _user-1_ from the console:
    
    -   In the upper-right corner of the page, choose **user-1**.
        
    -   Choose **Sign Out**.
        

### Task 3.3: Test user-2 permissions

43.  Paste the sign-in link into the private browser again, and press ENTER.
    
44.  Sign in with the following credentials:
    
    -   **IAM user name:**  `user-2`
        
    -   **Password:**  `Lab-Password2`
        
45.  Choose the **Services** menu, and choose **EC2**. You can also use the search bar to find and choose **EC2**.
    
46.  In the navigation pane on the left, choose **Instances**.
    
    -   You are now able to see an EC2 instance. However, you cannot make any changes to Amazon EC2 resources because you have read-only permissions.
        
    -   If you cannot see an EC2 instance, then your Region might be incorrect. In the upper-right corner of the page, choose the Region name, and then choose the Region that you were in at the beginning of the lab (for example, **N. Virginia**).
        
47.  Select the EC2 instance.
    
48.  Choose the **Instance state** menu, and then choose **Stop instance**.
    
49.  To confirm that you want to stop the instance, choose **Stop**.
    
    An error message appears and says that _You are not authorized to perform this operation_. This demonstrates that the policy only allows you to view information without making changes.
    
    Next, check whether _user-2_ can access Amazon S3.
    
50.  Choose the **Services** menu, and choose **S3**. You can also use the search bar to find and choose **S3**.
    
    An error message says _You don't have permissions to list buckets_ because _user-2_ does not have permissions to use Amazon S3.
    
    You will now sign-in as _user-3_, who was hired as your Amazon EC2 administrator.
    
51.  First, sign out _user-2_ from the console:
    
    -   In the upper-right corner of the page, choose **user-2**.
        
    -   Choose **Sign Out**.
        

### Task 3.4: Test user-3 permissions

52.  Paste the sign-in link into the private browser again, and press ENTER.
    
53.  Sign in with the following credentials:
    
    -   **IAM user name:**  `user-3`
        
    -   **Password:**  `Lab-Password3`
        
54.  Choose the **Services** menu, and choose **EC2**.
    
55.  In the navigation pane on the left, choose **Instances**.
    
    -   An EC2 instance is listed. As an Amazon EC2 Administrator, this user should have permissions to _Stop_ the EC2 instance.
        
    -   If you cannot see an EC2 instance, then your Region might be incorrect. In the upper-right corner of the page, choose the Region name, and then choose the Region that you were in at the beginning of the lab (for example, **N. Virginia**).
        
56.  Select the EC2 instance.
    
57.  Choose the **Instance state** menu, and then choose **Stop instance**.
    
58.  To confirm that you want to stop the instance, choose **Stop**.
    
    This time, the action is successful because _user-3_ has permissions to stop EC2 instances. The **Instance state** changes to _Stopping_ and starts to shut down.
    
59.  Close your private browser window.
    

## Conclusion

Congratulations! You now have successfully done the following:

-   Explored pre-created IAM users and groups
    
-   Inspected IAM policies as applied to the pre-created groups
    
-   Followed a real-world scenario, while adding users to groups with specific capabilities enabled
    
-   Located and used the IAM sign-in URL
    
-   Tested the effects of policies on service access
    

## Submitting your work

60.  At the top of these instructions, choose Submit to record your progress and when prompted, choose **Yes**.
    

61.  If the results don't display after a couple of minutes, return to the top of these instructions and choose Grades
    
    **Tip**: You can submit your work multiple times. After you change your work, choose **Submit** again. Your last submission is what will be recorded for this lab.
    

62.  To find detailed feedback on your work, choose Details followed by **View Submission Report**.
    

## Lab complete

Congratulations! You have completed the lab.

63.  To confirm that you want to end the lab, at the top of this page, choose **End Lab**, and then choose **Yes**.
    
    A message appears: _Ended AWS Lab Successfully_
    
