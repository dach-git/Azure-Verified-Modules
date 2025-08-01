---
title: AVM Issue Triage
description: Issue Triage description for the Azure Verified Modules (AVM) repository
---

## "AVM Core Team Triage" Explained

This page provides guidance for members of the **AVM Core Team** on how to **triage module proposals** and **generic issues** filed in the [AVM repository](https://aka.ms/AVM/repo), as well as how to manage these GitHub issues throughout their lifecycle.

During the AVM Core Team Triage step, the following will be checked, completed and actioned by the AVM Core Team during their triage calls (which are currently twice per week).

{{% notice style="note" %}}
Every module needs a module proposal to be created in the AVM repository.
{{% /notice %}}

{{% notice style="tip" %}}
During the triage process, the AVM Core Team should also check the status of following queries:

- Open items that **need triaging**: <a href="https://aka.ms/AVM/NeedsTriage">&nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#FBCA04;">Needs: Triage 🔍</mark>&nbsp;</a>
  - Bicep items (that need triaging): <a href="https://aka.ms/AVM/NeedsTriageBicep">&nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#1D73B3;color:white;">Language: Bicep 💪</mark>&nbsp;&nbsp;&&nbsp;&nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#FBCA04;">Needs: Triage 🔍</mark>&nbsp;</a>
  - Terraform items (that need triaging): <a href="https://aka.ms/AVM/NeedsTriageTerraform">&nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#7740B6;color:white;">Language: Terraform 🌐</mark>&nbsp;&nbsp;&&nbsp;&nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#FBCA04;">Needs: Triage 🔍</mark>&nbsp;</a>
- Open items that **need triaging AND aren't being triaged yet**: <a href="https://aka.ms/AVM/NeedsTriageButNotInTriage">&nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#FBCA04;">Needs: Triage 🔍</mark>&nbsp;&nbsp; & **NOT** &nbsp;&nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#E4E669;">Status: In Triage 🔍</mark>&nbsp;</a>
- Open items that **need attention**: <a href="https://aka.ms/AVM/NeedsAttention">&nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#E99695;">Needs: Attention 👋</mark>&nbsp;</a>
- Open items that **need owners**: <a href="https://aka.ms/AVM/NeedsModuleOwner">&nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#FF0019;color:white;">Needs: Module Owner 📣</mark>&nbsp;</a>
- Open items with **no recent activity**: <a href="https://aka.ms/AVM/NoRecentActivity">&nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#808080;color:white;">Status: No Recent Activity 💤</mark>&nbsp;</a>
- Open **question/feedback** items: <a href="https://aka.ms/AVM/QuestionsFeedback">&nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#CB6BA2;color:white;">Type: Question/Feedback 🙋‍♀️</mark>&nbsp;</a>
- Open items with **long term** status: <a href="https://aka.ms/AVM/StatusLongTerm">&nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#B60205;color:white;">Status: long-term ⏳</mark>&nbsp;</a>
- Open items that are <a href="https://aka.ms/AVM/NotInAProject">**not in a project**</a>.

{{% /notice %}}

## Module Proposal triage

An issue is considered to be a module proposal if

- it was opened through the "[New AVM Module Proposal 📝](https://aka.ms/avm/moduleproposal)" template,
- it has the labels of &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#FBCA04;">Needs: Triage 🔍</mark>&nbsp; and &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#ADD8E6;">Type: New Module Proposal 💡</mark>&nbsp; applied to it, and
- it is assigned to the "[AVM - Module Triage](https://github.com/orgs/Azure/projects/529)" GitHub project.

Follow these steps to triage a module proposal:

1. Add the &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#E4E669;">Status: In Triage 🔍</mark>&nbsp; label to indicate you're in the process of triaging the issue.
2. Check module proposal issue/form:
    - Check the [Bicep]({{% siteparam base %}}/indexes/bicep/) or [Terraform]({{% siteparam base %}}/indexes/terraform/) module indexes for the proposed module to make sure it is not already available or being worked on.
    - Ensure the module's details are correct as per specifications - [naming]({{% siteparam base %}}/spec/RMNFR1), [classification]({{% siteparam base %}}/specs/shared/module-classifications/) (resource/pattern) etc.
    - Check if the module is added to the "`Proposed`" column on the [AVM - Modules Triage](https://aka.ms/avm/moduletriage) GitHub project board.
    - Check if the requestor is a Microsoft FTE.
    - If there's any additional clarification needed, contact the requestor through comments (using their GH handle) or internal channels - for Microsoft FTEs only! You can look them up by their name or using the Microsoft Open Source Management Portal's People finder: "[Linked people across Microsoft organizations](https://repos.opensource.microsoft.com/people?q=)". Make sure you capture any decisions regarding the module in the comments section.
    - Make adjustments to the module's name/classification as needed.
    - Change the name of the issue to reflect the module's name, i.e.,
      - After the "[Module Proposal]:" prefix, change the issues name to the module's approved name between backticks, i.e., \` and \`, e.g., `avm/res/sql/managed-instance` for a Bicep module, or `avm-res-compute-virtualmachine` for a Terraform module.
      - Example:
        - "[Module Proposal]: `avm/res/sql/managed-instance`"
        - "[Module Proposal]: `avm-res-sql-managedinstance`"
    - Check if the GitHub Policy Service Bot has correctly applied the module language label: &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#1D73B3;color:white;">Language: Bicep 💪</mark>&nbsp; or &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#7740B6;color:white;">Language: Terraform 🌐</mark>&nbsp;
3. Apply relevant labels

    - Module classification (resource/pattern): &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#D3D3D3;">Class: Resource Module 📦</mark>&nbsp; or &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#A9A9A9;">Class: Pattern Module 📦</mark>&nbsp;

### Triaging pattern modules

As part of the triage of pattern modules, the following points need to be considered/clarified with the module requestor:

- Shouldn't this be a resource module? What makes it a pattern - e.g., does it deploy multiple resources?
- What is it for? What problem does it fix or provides a solution for?
- What is/isn't part of it? Which resource and/or pattern modules are planned to be leveraged in it? Provide a list of resources that would be part of the planned module.
- Where is it coming from/what's backing it - e.g., Azure Architecture Center (AAC), community request, customer example. Provide an architectural diagram and related documentation if possible - or a pointer to these if they are publicly available.
- Don't let the module's scope to grow too big, split it up to multiple smaller ones that are more maintainable - e.g., hub & spoke networking should should be split to a generic hub networking and multiple workload specific spoke networking patterns.
- The module's name should be as descriptive as possible.
- Adopt strict name-to-scope mapping - e.g., hub & spoke networking shouldn't deploy monitoring.

### Scenario 1: Requestor doesn't want to / can't be module owner

{{% notice style="note" %}}
If requestor is interested in becoming a module owner, but is not a Microsoft FTE, the AVM core team will try to find a Microsoft FTE to be the module owner whom the requestor can collaborate with.
{{% /notice %}}

1. If the requestor indicated they didn't want to or can't become a module owner (or is not a Microsoft FTE), make sure the &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#FF0019;color:white;">Needs: Module Owner 📣</mark>&nbsp; label is assigned to the issue. Note: the GitHub Policy Service Bot should automatically do this, based on how the issue author responded to the related question.
1. Move the issue to the "`Looking for owners`" column on the [AVM - Modules Triage](https://aka.ms/avm/moduletriage) GitHub project board.
1. Add a comment on the issue with the `#RFRC` tag to indicate that the repository should be created. This allows the module to be added the module indexes in the `Proposed` state, so that it can be found by the community and potential module owners.
1. Find module owners - if the requestor didn't volunteer in the module proposal OR the requestor does not want or cannot be owner of the module:
    - Try to find an owner from the AVM communities or await a module owner to comment and propose themselves on the proposal issue.
1. When a new potential owner is identified, continue with the steps described [as follows](#scenario-2-requestor-wants-to-and-can-become-module-owner).

### Scenario 2: Requestor wants to and can become module owner

If the requestor indicated they want to become the module owner, the GitHub Policy Service Bot will add the &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#FBEF2A;">Status: Owners Identified 🤘</mark>&nbsp; label and will assign the issue to the requestor.

You **MUST** still confirm that the requestor is a Microsoft FTE and that they understand the implications of becoming the owner! If any of these conditions aren't met, remove the &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#FBEF2A;">Status: Owners Identified 🤘</mark>&nbsp; label and unassign the issue from the requestor.

1. Make sure the requestor is a Microsoft FTE. You can look them up by their name or using the Microsoft Open Source Management Portal's People finder: "[Linked people across Microsoft organizations](https://repos.opensource.microsoft.com/people?q=)".
2. Clarify the roles and responsibilities of the module owner:
    - Clarify they understand and accept what "module ownership" means by replying in a comment to the requestor/proposed owner:

{{% expand title="➕ Standard AVM Core Team Reply to Proposed Module Owners" %}}

{{< highlight lineNos="false" type="markdown" wrap="true" title="" >}}

{{% include file="/static/includes/msg-std-reply-new-prop-mod-owners.md" %}}

{{< /highlight >}}

{{% /expand %}}

3. Once module owner identified has confirmed they understand and accept their roles and responsibilities as an AVM module owner
    - Make sure the issue is assigned to the confirmed module owner.
    - Move the issue into the "`In development`" column on the [AVM - Modules Triage](https://aka.ms/avm/moduletriage) GitHub Project board.
    - Add a comment on the issue with the `#RFRC` tag to indicate that the repository should be created. This allows the module to be added the module indexes in the `Proposed` state, so that it can be found by the community.
    - Make sure the &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#FBEF2A;">Status: Owners Identified 🤘</mark>&nbsp; label is added to the issue.
      - If applied earlier, remove the &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#FF0019;color:white;">Needs: Module Owner 📣</mark>&nbsp; label from the issue.
    - Remove the labels of &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#FBCA04;">Needs: Triage 🔍</mark>&nbsp; and &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#E4E669;">Status: In Triage 🔍</mark>&nbsp; to indicate you're done with triaging the issue.
4. Update the AVM Module Indexes, following the [process documented internally](https://dev.azure.com/CSUSolEng/Azure%20Verified%20Modules/_wiki/wikis/AVM%20Internal%20Wiki/684/Module-index-update-process).
5. Use the following text to approve module development

{{% expand title="➕ Final Confirmation for Proposed Module Owners - Bicep" %}}

{{< highlight lineNos="false" type="markdown" wrap="true" title="" >}}

{{% include file="/static/includes/msg-final-conf-new-prop-mod-owners-bicep.md" %}}

{{< /highlight >}}

{{% /expand %}}

{{% expand title="➕ Final Confirmation for Proposed Module Owners - Terraform" %}}

{{< highlight lineNos="false" type="markdown" wrap="true" title="" >}}

{{% include file="/static/includes/msg-final-conf-new-prop-mod-owners-tf.md" %}}

{{< /highlight >}}

{{% /expand %}}

{{% notice style="important" %}}

Although, it's not directly part of the module proposal triage process, to begin development, module owners and contributors might need additional help from the AVM core team, such as:

1. Update any Azure RBAC permissions for test tenants/subscription, if needed.
2. In case of **Bicep modules** only:
    - Look for the module owners confirmation on the related `[Module Proposal]` issue that they have created the required `-module-owners-` and `-module-contributors-` GitHub teams.
    - Ensure the `-module-owners-` and `-module-contributors-` GitHub teams have been assigned to their respective parent teams as outlined [here]({{% siteparam base %}}/spec/snfr20/#grant-permissions---bicep).
    - Ensure the [`CODEOWNERS`](https://github.com/Azure/bicep-registry-modules/blob/main/.github/CODEOWNERS) file in the [BRM repo](https://aka.ms/BRM) has been updated.
    - Ensure the [`AVM Module Issue template`](https://github.com/Azure/bicep-registry-modules/blob/main/.github/ISSUE_TEMPLATE/avm_module_issue.yml) file in the [BRM repo](https://aka.ms/BRM) has been updated.

{{% /notice %}}

## Post-Development issue management

Once module is developed and `v0.1.0` has been published to the relevant registry

1. Assign the &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#C8E6C9;">Status: Module Available 🟢</mark>&nbsp; label to the issue.
2. Move the issue into "`Done`" column in [AVM - Modules Triage](https://aka.ms/avm/moduletriage) GitHub Project.
3. Update the AVM Module Indexes, following the [process documented internally](https://dev.azure.com/CSUSolEng/Azure%20Verified%20Modules/_wiki/wikis/AVM%20Internal%20Wiki/684/Module-index-update-process).
4. Close the issue.

{{% notice style="important" %}}

- The Module Proposal issue **MUST remain open** until the module is fully developed, tested and published to the relevant registry.
- Do NOT close the issue before the successful publication is confirmed!
- Once the module is fully developed, tested and published to the relevant registry, and the Module Proposal issue was closed, it **MUST remain closed**.

{{% /notice %}}

## Orphaned modules

### When a module becomes orphaned

If a module meets the criteria described in the "[Orphaned Modules]({{% siteparam base %}}/specs/shared/module-lifecycle/#3-orphaned-avm-modules)" chapter, the module is considered to be orphaned and the below steps must be performed.

{{% notice style="note" %}}
The original **Module Proposal issue** related to the module in question **MUST remain closed and intact**.

Instead, a **new Orphaned Module issue** must be opened that **MUST remain open** until the ownership is fully confirmed!

Once the **Orphaned Module issue** was closed, it **MUST remain closed**. If the module will subsequently become orphaned again, a new Orphaned Module issue must be opened.
{{% /notice %}}

1. Submit an "orphaned module" issue by using the "[Orphaned AVM Module 🟡](https://aka.ms/AVM/OrphanedModule)" issue template.
2. Make sure the &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#FBCA04;">Needs: Triage 🔍</mark>&nbsp;, &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#FF0019;color:white;">Needs: Module Owner 📣</mark>&nbsp;, and the &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#F4A460;">Status: Module Orphaned 🟡</mark>&nbsp; labels are assigned to the issue and it is assigned to the "[AVM - Module Triage](https://github.com/orgs/Azure/projects/529)" GitHub project.
3. Move the issue into the "`Orphaned`" column on the [AVM - Modules Triage](https://aka.ms/avm/moduletriage) GitHub Project board.
4. Update the AVM Module Indexes, following the [process documented internally](https://dev.azure.com/CSUSolEng/Azure%20Verified%20Modules/_wiki/wikis/AVM%20Internal%20Wiki/684/Module-index-update-process).
5. Place an information notice as per the below guidelines:
    - In case of a Bicep module:
      - Place the information notice - with the text below - in an `ORPHANED.md` file, in the module's root.
      - Run the [`utilities/tools/Set-AVMModule.ps1`](https://github.com/Azure/bicep-registry-modules/blob/main/utilities/tools/Set-AVMModule.ps1) utility with the module path as an input. This re-generates the module’s `README.md` file, so that the `README.md` file will also contain the same notice in its header.
      - Make sure the content of the `ORPHANED.md` file is displayed in the `README.md` in its header (right after the title).
    - In case of a Terraform module, place the information notice - with the text below - in the `README.md` file, in the module's root.
    - Once the information notice is placed, submit a Pull Request.

Include the following text in the information notice:

{{% expand title="➕ Orphaned module notice for module README file" %}}

{{< highlight lineNos="false" type="markdown" wrap="true" title="ORPHANED.md" >}}

{{% include file="/static/includes/orphaned-module-notice.md" %}}

{{< /highlight >}}

{{% /expand %}}

6. Try to find a new owner using the AVM communities or await a new module owner to comment and propose themselves on the issue.

### When a new owner is identified

{{% notice style="tip" %}}
To look for Orphaned Modules:

- Click on the following link to use this saved query ➡️ <a href="https://aka.ms/avm/OrphanedModules">&nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#F4A460;">Status: Module Orphaned 🟡</mark>&nbsp;</a> ⬅️.
- Check the `Orphaned` swim lane on the [Module Triage board](https://aka.ms/avm/moduletriage).
{{% /notice %}}

1. When a new potential owner is identified, clarify the roles and responsibilities of the module owner:
    - Clarify they understand and accept what "module ownership" means by replying in a comment to the requestor/proposed owner:

{{% expand title="➕ Standard AVM Core Team Reply to New Owners of an Orphaned Module" %}}

{{< highlight lineNos="false" type="markdown" wrap="true" title="" >}}

{{% include file="/static/includes/msg-std-reply-new-orph-mod-owners.md" %}}

{{< /highlight >}}

{{% /expand %}}

2. Once the new module owner candidate has confirmed they understand and accept their roles and responsibilities as an AVM module owner
    - Assign the issue to the confirmed module owner.
    - Remove the &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#F4A460;">Status: Module Orphaned 🟡</mark>&nbsp; and the &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#FF0019;color:white;">Needs: Module Owner 📣</mark>&nbsp; labels from the issue.
    - Add the &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#C8E6C9;">Status: Module Available 🟢</mark>&nbsp; and &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#FBEF2A;">Status: Owners Identified 🤘</mark>&nbsp; labels to the issue.
    - Move the issue into the "`Done`" column on the [AVM - Modules Triage](https://aka.ms/avm/moduletriage) GitHub Project board.
3. Update the AVM Module Indexes, following the [process documented internally](https://dev.azure.com/CSUSolEng/Azure%20Verified%20Modules/_wiki/wikis/AVM%20Internal%20Wiki/684/Module-index-update-process).
4. Get the new owner(s) and any new contributor(s) added to the related `-module-owners-` or `-module-contributors-` teams. See [SNFR20]({{% siteparam base %}}/spec/SNFR20) for more details.
5. Remove the information notice (i.e., the file that states that `⚠️THIS MODULE IS CURRENTLY ORPHANED.⚠️, etc.` ):
    - In case of a Bicep module:
      - Delete the `ORPHANED.md` file from the module's root.
      - Run the [`utilities/tools/Set-AVMModule.ps1`](https://github.com/Azure/bicep-registry-modules/blob/main/utilities/tools/Set-AVMModule.ps1) utility with the module path as an input. This re-generates the module’s `README.md` file, so that it will no longer contain the orphaned module notice in its header.
      - Double check the previous steps was successful and the `README.md` file no longer has the information notice in its header (right after the title).
    - In case of a Terraform module, remove the information notice from the `README.md` file in the module's root.
    - Once the information notice is removed, submit a Pull Request.
6. Use the following text to confirm the new ownership of an orphaned module:

{{% expand title="➕ Final Confirmation for New Owners of an Orphaned Module" %}}

{{< highlight lineNos="false" type="markdown" wrap="true" title="" >}}

{{% include file="/static/includes/msg-final-conf-new-orph-mod-owners.md" %}}

{{< /highlight >}}

{{% /expand %}}

7. Close the Orphaned Module issue.

## Deprecated modules

### When a module becomes deprecated

If a module meets the criteria described in the "[Deprecated Modules]({{% siteparam base %}}/specs/shared/module-lifecycle/#4-deprecated-modules)" chapter, the module is considered to be deprecated and the below steps must be performed.

1. Submit a "deprecated module" issue by using the "[Deprecate AVM Module 🔴](https://aka.ms/avm/DeprecatedModule)" issue template.
2. Make sure the &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#FBCA04;">Needs: Triage 🔍</mark>&nbsp; and the &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#000000;color:white;">Status: Module Deprecated 🔴</mark>&nbsp; labels are assigned to the issue and it is assigned to the "[AVM - Module Triage](https://github.com/orgs/Azure/projects/529)" GitHub project.
3. Update the AVM Module Indexes, following the [process documented internally](https://dev.azure.com/CSUSolEng/Azure%20Verified%20Modules/_wiki/wikis/AVM%20Internal%20Wiki/684/Module-index-update-process).
4. Place an information notice as per the below guidelines:
    - In case of a Bicep module:
      - Place the information notice - with the text below - in an `DEPRECATED.md` file, in the module's root.
      - Run the [`utilities/tools/Set-AVMModule.ps1`](https://github.com/Azure/bicep-registry-modules/blob/main/utilities/tools/Set-AVMModule.ps1) utility with the module path as an input. This re-generates the module’s `README.md` file, so that the `README.md` file will also contain the same notice in its header.
      - Make sure the content of the `DEPRECATED.md` file is displayed in the `README.md` in its header (right after the title).
      - Publish a new patch version, having the updated `README.md` stating the module is deprecated.
    - In case of a Terraform module:
      - Place the information notice - with the text below - in the `README.md` file, in the module's root.
      - Archive the module's repository on GitHub.
    - Once the information notice is placed, submit a Pull Request.
5. Keep the module's `-owners-` and `-contributors-` GitHub teams, as these will keep granting access to the source code of the module.

Place the following information notice in the module's repository:

{{% expand title="➕ Deprecated module indicators" %}}

{{< highlight lineNos="false" type="markdown" wrap="true" title="DEPRECATED.md" >}}

{{% include file="/static/includes/deprecated-module-notice.md" %}}

{{< /highlight >}}

{{% /expand %}}

## General feedback/question, documentation update and other standard issues

An issue is a "General Question/Feedback ❔" if it was opened through the ["General Question/Feedback ❔"](https://github.com/Azure/Azure-Verified-Modules/issues/new?assignees=&labels=Type%3A+Question%2FFeedback+%3Araising_hand%3A&projects=&template=question_feedback.yml&title=%5BQuestion%2FFeedback%5D%3A+) issue template, and has the labels of &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#CB6BA2;color:white;">Type: Question/Feedback 🙋‍♀️</mark>&nbsp; and &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#FBCA04;">Needs: Triage 🔍</mark>&nbsp; applied to it.

An issue is a "AVM Documentation Update 📘" if it was opened through the ["AVM Documentation Update 📘"](https://github.com/Azure/Azure-Verified-Modules/issues/new?template=documentation_update.yml) issue template, and has the labels of &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#0075CA;color:white;">Type: Documentation 📄</mark>&nbsp; and &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#FBCA04;">Needs: Triage 🔍</mark>&nbsp; applied to it.

An issue is considered to be a "standard issue" or "blank issue" if it was opened without using an issue template, and hence it does **NOT** have any labels assigned, OR only has the &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#FBCA04;">Needs: Triage 🔍</mark>&nbsp; label assigned.

When triaging the issue, consider adding one of the following labels as fits:

- &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#0075CA;color:white;">Type: Documentation 📄</mark>&nbsp;
- &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#A2EEEF;">Type: Feature Request ➕</mark>&nbsp;
- &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#D73A4A;color:white;">Type: Bug 🐛</mark>&nbsp;
- &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#FFFF00;">Type: Security Bug 🔒</mark>&nbsp;

To see the full list of available labels, please refer to the [GitHub Repo Labels]({{% siteparam base %}}/spec/SNFR23) section.

{{% notice style="note" %}}

If an intended module proposal was mistakenly opened as a "General Question/Feedback ❔" or other standard issue, and hence, it doesn't have the &nbsp;<mark style="background-image:none;white-space: nowrap;background-color:#ADD8E6;">Type: New Module Proposal 💡</mark>&nbsp; label associated to it, a new issue **MUST** be created using the "New AVM Module Proposal 📝" [issue template](https://aka.ms/avm/moduleproposal). The mistakenly created "General Question/Feedback ❔" or other standard issue **MUST** be closed.

{{% /notice %}}
