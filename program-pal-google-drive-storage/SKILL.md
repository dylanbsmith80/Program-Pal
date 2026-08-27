---
name: program-pal-google-drive-storage
description: Use when Program Pal needs to save, upload, organize, or locate client assessment forms and generated workout programs in the trainer's Google Drive folder named Program pal using the required client-folder naming convention.
---

# Program Pal Google Drive Storage Skill

Use this skill when storing Program Pal client files in Google Drive.

This skill governs file organization only. It does not generate assessments, design programs, select exercises, or format Excel workbooks.

## Storage Mechanism

Use the configured Google Drive connector/plugin when available.

The target root folder in Google Drive is:

`Program pal`

Storage must always use the Google Drive account that is currently authenticated in the running user's connector or browser session. Do not use hardcoded Google Drive folder IDs, account-specific URLs, shared links, saved browser sessions from another user, or another trainer's authenticated Drive context.

If the authenticated user's Google Drive does not already contain a root-level folder named `Program pal`, create the `Program pal` folder in that user's My Drive root before creating client folders or uploading files.

If the Google Drive connector/plugin is unavailable, ask the trainer to enable or install Google Drive access before storing files. Do not silently switch to OneDrive, local Downloads, or another cloud folder.

If the Google Drive connector can search or list files but does not expose the actions needed to create folders, upload files, or place files in a target folder, use the authenticated Google Drive web UI through Browser or Chrome automation. Treat this as the required fallback, not as an optional convenience.

Only stop before storage when both connector-based storage and browser-based storage are unavailable or blocked. In that case, tell the trainer exactly which capability is blocked.

If multiple Google Drive folders named `Program pal` exist, ask the trainer which one to use before storing files.

## Folder Structure

Inside the Google Drive `Program pal` folder, each client gets one folder named:

`FirstNameLastInitial`

Examples:

- `DylanS`
- `MariaG`
- `JordanT`

Store all files directly inside the client folder:

```text
ClientFolder/
  YYYY-MM-DD Assessment - ClientFolderName.ext
  YYYY-MM-DD Program - ClientFolderName - ProgramLabel.ext
  YYYY-MM-DD Program - ClientFolderName - Next Program Label.ext
```

Do not create `Assessments/`, `Programs/`, or other category subfolders unless the trainer explicitly asks for them. The current trainer-preferred layout is a flat client folder, as in `Program pal/DylanS/`.

## Client Folder Naming Rules

Use the client's first name plus last initial.

Rules:

- Use no spaces.
- Use the first name as provided, normalized to title case when obvious.
- Use the first letter of the last name as an uppercase initial.
- Remove punctuation that would be awkward in a folder name.
- If the last name is missing, ask for the last initial before creating the folder.
- If two clients would have the same folder name, ask the trainer how to disambiguate before creating or storing files.

Do not use full last names unless the trainer explicitly asks.

## File Naming Rules

Use clear, date-prefixed file names.

Assessment files:

`YYYY-MM-DD Assessment - ClientFolderName.ext`

Program files:

`YYYY-MM-DD Program - ClientFolderName - ProgramLabel.ext`

Examples:

- `2026-05-27 Assessment - DylanS.pdf`
- `2026-05-27 Program - DylanS - 8 Week Strength Block.xlsx`

If there are multiple programs for the same client, keep all of them directly in the client folder with distinct dates or program labels.

## Storage Workflow

When storing an assessment:

1. Find or create the Google Drive root folder named `Program pal`.
2. Create the client folder if it does not exist.
3. Upload or copy the assessment directly into the client folder.
4. Preserve the original assessment file unless the trainer explicitly asks to move or delete it.
5. Verify the uploaded assessment appears directly in the client folder before reporting completion.

When storing a generated workout workbook:

1. Find or create the Google Drive root folder named `Program pal`.
2. Create the client folder if it does not exist.
3. Upload or copy the workbook directly into the client folder.
4. Preserve the generated workspace copy unless the trainer explicitly asks to move or delete it.
5. Verify the uploaded workbook appears directly in the client folder before reporting completion.

## Browser Fallback Workflow

Use this workflow when connector write actions are unavailable but the trainer's browser has an authenticated Google Drive session:

1. Open the `Program pal` Google Drive folder.
2. Create the client folder using the required `FirstNameLastInitial` naming rule.
3. Open the client folder.
4. Rename or stage local files with the required date-prefixed file names before upload.
5. Upload the assessment file directly into the client folder.
6. Upload the program workbook directly into the client folder.
7. Use the Google Drive connector to list the client folder afterward when possible, confirming the final file names and links.

## Access And Permission Rules

If Google Drive access is unavailable, expired, disconnected, or missing required permissions:

- State that Google Drive access is unavailable.
- Ask the trainer to enable or reconnect Google Drive access.
- Do not save files to an alternate location unless the trainer explicitly approves.

If a file with the same name already exists:

- Do not overwrite it silently.
- Ask whether to replace it, keep both, or create a versioned file name.

## Post-Upload Report

After uploading or copying any assessment or workout program to Google Drive, report the result in a consistent receipt format.

Include:

- Drive folder: the final folder path, such as `Program pal/DylanS`.
- Uploaded file name: the exact file name now visible in Drive.
- Link: the Google Drive file link when available, or state `Unavailable` if the connector or browser flow cannot provide one.
- Duplicate status: state whether no duplicate was found, an existing file was replaced, both files were kept, a versioned name was created, or upload was skipped because the trainer declined a duplicate action.
- Local copy preserved: state `Yes`, `No`, or `Not applicable`, and mention the local path when useful.

Use this format:

```text
Drive Upload Complete

Drive folder: Program pal/ClientFolder
Uploaded file: YYYY-MM-DD Program - ClientFolder - Program Label.xlsx
Link: https://drive.google.com/...
Duplicate status: No duplicate found; uploaded as a new file.
Local copy preserved: Yes
```

If upload fails or is blocked, use the same fields where possible and clearly state the failure reason instead of reporting completion.

## Privacy Rules

Client folders and files may contain private client information.

Use only the client folder naming convention above unless instructed otherwise.

Do not share, publish, rename, delete, or move client files outside the Google Drive `Program pal` folder unless the trainer explicitly asks.

## Handoff

Use this skill after:

- `program-pal-initial-assessment` when an assessment file should be stored.
- `personal-training-workbook-format` when a completed workbook should be stored.

This skill may also be used at the beginning of a client workflow to locate prior assessments or programs for that client.
