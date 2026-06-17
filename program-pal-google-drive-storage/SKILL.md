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

If the Google Drive connector/plugin is unavailable, ask the trainer to enable or install Google Drive access before storing files. Do not silently switch to OneDrive, local Downloads, or another cloud folder.

If multiple Google Drive folders named `Program pal` exist, ask the trainer which one to use before storing files.

## Folder Structure

Inside the Google Drive `Program pal` folder, each client gets one folder named:

`FirstNameLastInitial`

Examples:

- `DylanS`
- `MariaG`
- `JordanT`

Inside each client folder, use:

```text
ClientFolder/
  Assessments/
  Programs/
```

Store assessment forms in `Assessments/`.

Store generated workout programs in `Programs/`.

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

If there are multiple programs for the same client, keep all of them in the `Programs/` folder with distinct dates or program labels.

## Storage Workflow

When storing an assessment:

1. Find the Google Drive root folder named `Program pal`.
2. Create the client folder if it does not exist.
3. Create `Assessments/` and `Programs/` subfolders if they do not exist.
4. Upload or copy the assessment into `Assessments/`.
5. Preserve the original assessment file unless the trainer explicitly asks to move or delete it.

When storing a generated workout workbook:

1. Find the Google Drive root folder named `Program pal`.
2. Create the client folder if it does not exist.
3. Create `Assessments/` and `Programs/` subfolders if they do not exist.
4. Upload or copy the workbook into `Programs/`.
5. Preserve the generated workspace copy unless the trainer explicitly asks to move or delete it.

## Access And Permission Rules

If Google Drive access is unavailable, expired, disconnected, or missing required permissions:

- State that Google Drive access is unavailable.
- Ask the trainer to enable or reconnect Google Drive access.
- Do not save files to an alternate location unless the trainer explicitly approves.

If a file with the same name already exists:

- Do not overwrite it silently.
- Ask whether to replace it, keep both, or create a versioned file name.

## Privacy Rules

Client folders and files may contain private client information.

Use only the client folder naming convention above unless instructed otherwise.

Do not share, publish, rename, delete, or move client files outside the Google Drive `Program pal` folder unless the trainer explicitly asks.

## Handoff

Use this skill after:

- `program-pal-initial-assessment` when an assessment file should be stored.
- `personal-training-workbook-format` when a completed workbook should be stored.

This skill may also be used at the beginning of a client workflow to locate prior assessments or programs for that client.
