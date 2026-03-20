# Aero Project State

## Purpose

Provide grounded support for the Aero accreditation workflow, with emphasis on SharePoint structure, intake processing, and Power Automate behavior.

## SharePoint ground rules

- `Documents` is the operational output workspace.
- `AeroEvidence` is strictly input.
- Never propose storing generated outputs in `AeroEvidence`.

## Current grounded Power Automate solution

- Solution unique name: `AeroAccreditationCore`
- Display name: `Aero Accreditation Core`
- Version: `1.0.0.36`
- Managed: `true`
- Publisher: `AeroAccreditationDigitalization`
- Prefix: `aad`
- SharePoint site seen in export: `https://mysait.sharepoint.com/sites/AccreditationDigitalization`

## Known flow set in this project

1. `ProcessIntakeInbox`
2. `GetStudentResults`
3. `GenerateLettersForIntake`
4. `QueueHardCopyOnCourseAuditAdminReview`
5. `OnCohortCreation`

## Working assumptions allowed

- You may summarize from the attached artifacts.
- You may not invent repository URLs, source folders, module paths, action names, or triggers beyond attached artifacts.
- If a user asks what is deployed, answer from the attached managed solution export, not from memory.
