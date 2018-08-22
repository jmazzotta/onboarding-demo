---
# Mandatory fields. See more on aka.ms/skyeye/meta.
title: useful links for onboarding to Docs
description: Getting started 
author: Joe Mazzotta
ms.author: joemaz
ms.date: 08/11/2018
ms.topic: contributor-guide
ms.prod: docs
---
# Useful links for anyone Onboarding to Docs

1. It is required to have basic understanding of Git, Github including creating a Pull Request (PR), merging or resolving merge conflicts, and an understanding of commits. Here is more info: https://microsoft.sharepoint.com/:p:/r/teams/MAXCommercialTechNettoDocsmigration/_layouts/15/Doc.aspx?sourcedoc=%7B44e20ca0-dd32-4c2d-a074-f86c9f99252c%7D&action=edit&uid=%7B44E20CA0-DD32-4C2D-A074-F86C9F99252C%7D&ListItemId=91&ListId=%7BF0DAE79D-B89F-4176-A132-D742D5FE939D%7D&odsp=1&env=prodbubble

2. Microsoft Docs is a platform where external users, customers, developers come to learn or use Microsoft technical content.
3. 
4. Step 1 of 3:

   ![provision conceptual repo step 1](media/portal-provision-con-step1.png)

   - **1: Account/Organization** Select from the list available to you, based on the GitHub or VSTS ID you signed in with.
   - **2: Repo Name** To create a new repo, type the desired name. This should generally be short and indicate the content of the repo. Check with your team for specific naming guidelines. To add a new doc set to an existing repo, you would select the repo from the drop-down list.
   - **3: Private Repository** Check the box to make your repo private. By default it will be public.
   - **4: Locale** For English repos, keep the default, en-us.
   - **5: Override** Most users will not modify this option. Use this option ONLY if your repo naming convention for localization needs to follow a different one than the standard. If so, click on **Override** and select your locale. <!-- some guidance on how to know/who to talk to would be nice!! -->
   - **6: Notification Subscribers** Add any group or individual aliases that should be notified when there's a new content build or publishing event.
   - **7: Preview Pull Requests** Select this option to run a build on all pull requests and publish preview from all branches to review.docs.microsoft.com (accessible by Microsoft internal users only).
   - Click **Next** to move to Step 2.

1. Step 2 of 3:
   
   ![provision conceptual repo step 2](media/portal-provision-con-step2.png)

   - **1: Doc set Name** The name of the new conceptual doc set you are creating. In general this should be short, descriptivem and appropriate to use as part of URL paths to your topics. Check the SEO  and URL guidelines (linked above) and your team naming guidelines.
   - **2: Doc set Folder** The folder in the repo to contain your doc set files. This is usually the same as the doc set name, but you do have to type it in again.
   - **3: Site/Themes** The site to publish to. Choose **Docs** (the default) unless it is your team policy to publish to another site and you have permission to do so. Content published to MSDN, TechNet, and VisualStudio.com will not be published live. <!-- need  clarification on this -->
   - **4: Tenant** Your business group, such as C + E.
   - **5: Template** Choose **Conceptual** for general non-reference content. If you want to create or migrate a specialized type of conceptual content, check with the [APEX Engagement PM Team](mailto:ceapexpir@microsoft.com) first to make sure your content type is supported.
   - **6: Base Url** This will be the first part of the path for published all pages of your doc set. The first part of the base URL is determined by the chosen site, generally docs.microsoft.com, and cannot be edited. The second part is your doc set name by default and should not be changed to minimize confusion.
   - **7: Product Family** This is a legacy value from the MTPS publishing system, and is not used for most doc sets. You can set it to a meaningful value for your content if available; otherwise leave the default, MSDN. <!-- why do we still need this? need to clarify guidance which is confusing -->
   - **8: Public Contributors** If you selected Public in the previous step, this will be checked by default. Leave it checked to enable public contributions to the repo (highly recommended). If you selected a Private repo, do not check this option, or users will attempt to make contributions but get a page not found (404) error because they do not have access to the repo. <!-- why do we allow this then? seems a bad experience -->
   - **9: API Scan** Check this box to enable APIScan metadata to be published for your content. Most conceptual content does not require APIScan, but some reference documentation, such as Win32/COM reference, is hand-authored rather than auto-generated and therefore treated as conceptual by OPS. APIScan is most often required for conceptual content migrated from older systems such as CAPS or WDCML.
     
    > [!WARNING]
    > You are responsible for ensuring that APIScan requirements are met for your content. Missing APIScan metadata is a compliance issue and can cause unexpected ship delays for Microsoft products. If you are creating or migrating  hand-authored reference content, make sure to check whether APIScan is required and whether there is existing APIScan metadata on source content. Be sure to check APIScan when creating the docset, and be sure to include APIScan metadata in migration if appropriate. <!-- link to contributor guide APIScan topic when available -->
    
   - Click **Next** to move to a summary page.
1. Step 3 of 3: Review the options you have selected and click **Start** to provision the repo if they are correct. The repo will then be previsioned with default configuration files, including legal notices, project and build configurations, and stub TOC and breadcrumb files. Files will be in the correct locations for a single conceptual doc set in the new repo. Don't them unless you are following specific steps in this guide for a desired outcome.
    - If your selections are not correct, click **Previous** to change your selections or **Cancel** to cancel.

## Repo permissions

**GitHub:**

If you create your new repo in the Microsoft Docs organization via the OPS Portal as recommended, the following GitHub teams will be granted access automatically. 

> [!IMPORTANT]
> If you create your repo in a different organization, or not via the Portal, you need to add them manually, via **the Settings -> Collabotors and teams** tab in GitHub.

|Team                                                                                  |Access level|Description|
|--------------------------------------------------------------------------------------|------------|-----------|
|[OPS_Admin](https://github.com/orgs/MicrosoftDocs/teams/ops_admin)                    |Admin       |**Required.** For assistance with enabling content to go live ("Goto live flag") and for disaster recovery. Includes members of the APEX engineering, support, and PM teams.|
|[APEX-Eng-Team](https://github.com/orgs/MicrosoftDocs/teams/apex-eng-team)            |Read        |For troubleshooting issues.|
|[OPS_ServiceAccounts](https://github.com/orgs/MicrosoftDocs/teams/ops_serviceaccounts)|Read        |A collection of service accounts that may need access to support downstream processes, such as localization, BI, testing, etc.|

<!-- It seems a bunch more are actually added via Portal. Are they all required? -->

To learn more about repo permissions in GitHub, see the [Repository permission levels for an organization](https://help.github.com/articles/repository-permission-levels-for-an-organization/) page of the GitHub documentation. 

**VSTS:**

If your repo is in VSTS, you need to add the following permissions: <!-- all manually? -->

|Team     |Access level|Description <!-- ?? need to get details and add -->  |
|---------|------------|---------|
|OPS_Admin|Admin       |         |
|Olprod   |Read        |         |
|Openloc  |Read        |         |

## OPS Notifications

To receive email notifications from the Open Publishing Build Service, you need to modify some of your personal account settings on GitHub.

Click the profile drop-down in the upper right and choose **Settings**. 

To get email for push operations:

1. Go to the **Emails** tab in the left nav.
1. Clear the **Keep my email address private** checkbox.
1. When this option is unchecked and you push commits, GitHub sends OP a notification with the primary email address in this list. Otherwise, GitHub sends OP a notification with username@users.noreply.github.com, and you won't receive a notification from OP.

To get email for pull requests:

1. Go to the **Profile** tab in the left nav.
1. Set a public email.
1. For a pull request, GitHub does not send OP the user's email address. So OP looks up the username to get the user's public email address, which is listed in this field. If you don't list one, you won't get mail for your pull request.

To not receive additional notifications:

1. Go to **Profile** and under **Public email** set it to **Don't show my email address**. This is so you won't get emailed by  readers outside of Microsoft.
1. Go to the **Emails** tab and under **Email preferences** select **Only receive account-related emails, and those I subscribe to**.

## Doc feedback via GitHub issues

It's recommended to enable user feedback from Docs via GitHub issues. This allows users to submit feedback about a specific page of documentation to a public feedback repo. The Docs issues feature includes some automation, such as an auto-generated **Details** summary and optional label automtion. For more information, see the [GitHub issues](https://review.docs.microsoft.com/en-us/help/contribute/github-issues-feedback?branch=master) content in the Docs Contributor Guide.

## PRMerger

PRMerger is a workflow automation tool to facilitate collaboration in a repo. With PRMerger, contributors without write permissions can sign off on their PRs via comments. Depending on the content of a PR, it is either merged automatically or flagged for human review. For more information, see PRMerger in the [Docs Contributor Guide](https://review.docs.microsoft.com/en-us/help/contribute/prmerger-overview?branch=master).
