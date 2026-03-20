# Aero Accreditation Core Power Automate Export Inventory

- Source artifact in KB repo: `Artifacts/PowerAutomate_Exports/AeroAccreditationCore_1_0_0_36_managed.zip`
- Original user-provided file: `C:\Users\rodne\Downloads\AeroAccreditationCore_1_0_0_36_managed.zip.txt`
- Solution unique name: `AeroAccreditationCore`
- Solution display name: `Aero Accreditation Core`
- Version: `1.0.0.36`
- Managed: `true`
- Publisher: `AeroAccreditationDigitalization`
- Publisher display name: `AAD`
- Customization prefix: `aad`

## Flow Inventory

1. `ProcessIntakeInbox-1090A00C-D311-F111-8341-7CED8D35F541.json`
   - Trigger key: `For_a_selected_file`
   - Trigger type: `Request`
   - Trigger kind: `ApiConnection`
   - Operation: `ForASelectedFileHybridTrigger`
   - SharePoint site: `https://mysait.sharepoint.com/sites/AccreditationDigitalization`
   - Table/List id: `5bcda010-124c-48ac-a9a7-00b70706baf4`

2. `GetStudentResults-75B78E64-CD15-F111-8341-7CED8D35F541.json`
   - Trigger key: `When_a_file_is_created_or_modified_(properties_only)`
   - Trigger type: `OpenApiConnection`
   - Operation: `GetOnUpdatedFileItems`
   - Polling recurrence: every `1 Minute`
   - SharePoint site: `https://mysait.sharepoint.com/sites/AccreditationDigitalization`
   - Table/List id: `5bcda010-124c-48ac-a9a7-00b70706baf4`
   - Conditions:
     - filename equals `_INBOX-READY.txt`
     - path contains `/_inbox/`

3. `GenerateLettersForIntake-58E4CD34-741D-F111-8341-7CED8D35F541.json`
   - Trigger key: `trigger_ForSelectedIntake`
   - Trigger type: `Request`
   - Trigger kind: `ApiConnection`
   - Operation: `GetItemHybridTriggerSchema`
   - SharePoint site: `https://mysait.sharepoint.com/sites/AccreditationDigitalization`
   - Table/List id: `979bac79-369e-4cda-ba63-08223b5dcbb3`

4. `QueueHardCopyOnCourseAuditAdminReview-1B411426-1E23-F111-8342-7CED8D35F541.json`
   - Trigger key: `When_a_file_is_created_or_modified_(properties_only)`
   - Trigger type: `OpenApiConnection`
   - Operation: `GetOnUpdatedFileItems`
   - Polling recurrence: every `1 Minute`
   - SharePoint site: `https://mysait.sharepoint.com/sites/AccreditationDigitalization`
   - Table/List id: `66f929e3-72b9-434b-9337-9dcfe55d8da0`

5. `OnCohortCreation-C416AF44-950B-F111-8406-7CED8D35F541.json`
   - Trigger key: `OnIntakeCreation`
   - Trigger type: `OpenApiConnection`
   - Operation: `GetOnNewItems`
   - Polling recurrence: every `1 Minute`
   - SharePoint site: `https://mysait.sharepoint.com/sites/AccreditationDigitalization`
   - Table/List id: `979bac79-369e-4cda-ba63-08223b5dcbb3`
