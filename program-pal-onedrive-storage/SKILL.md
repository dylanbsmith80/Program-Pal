---
name: program-pal-onedrive-storage
description: Use when Program Pal needs to save, copy, organize, or locate client assessment forms and generated workout programs in the trainer's local OneDrive Training Pal folder using the required client-folder naming convention.
---

# Program Pal OneDrive Storage Skill

Use this skill when storing Program Pal client files in the trainer's local OneDrive-synced Training Pal folder.

This skill governs file organization only. It does not generate assessments, design programs, select exercises, or format Excel workbooks.

## Storage Mechanism

Use the local OneDrive sync folder on the Mac. Do not use Microsoft Graph, browser upload, or direct cloud API upload unless the trainer explicitly asks for that later.

Read the storage root from `config/storage-root.local.md` when it exists. That file is private and ignored by git.

If the local config is missing or the path is inaccessible, ask the trainer for the current OneDrive Training Pal folder path before storing files.

## Folder Structure

The root folder is the trainer's OneDrive `Training Pal` folder.

Each client gets one folder named:

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

1. Resolve the OneDrive Training Pal root folder.
2. Create the client folder if it does not exist.
3. Create `Assessments/` and `Programs/` subfolders if they do not exist.
4. Copy the assessment into `Assessments/`.
5. Preserve the original assessment file unless the trainer explicitly asks to move it.

When storing a generated workout workbook:

1. Resolve the OneDrive Training Pal root folder.
2. Create the client folder if it does not exist.
3. Create `Assessments/` and `Programs/` subfolders if they do not exist.
4. Save or copy the workbook into `Programs/`.
5. Preserve the generated workspace copy unless the trainer explicitly asks to move it.

## Access And Permission Rules

If macOS, OneDrive, or sandbox permissions prevent access to the folder:

- State that the path could not be accessed.
- Ask the trainer to confirm the folder path or grant access.
- Do not silently save files somewhere else.
- Do not create a duplicate cloud workflow without explicit trainer approval.

## Privacy Rules

Client folders and files may contain private client information.

Use only the client folder naming convention above unless instructed otherwise.

Do not upload, share, rename, delete, or move client files outside the OneDrive Training Pal folder unless the trainer explicitly asks.

## Handoff

Use this skill after:

- `program-pal-initial-assessment` when an assessment file should be stored.
- `personal-training-workbook-format` when a completed workbook should be stored.

This skill may also be used at the beginning of a client workflow to locate prior assessments or programs for that client.
