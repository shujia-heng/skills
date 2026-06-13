---
name: migrate-transcripts
description: Find and copy old conversation transcripts from a previously-located project folder to the current project's transcript directory so /resume works after a folder move.
---

# Migrate Transcripts

When invoked, perform these steps:

1. Determine the current project's transcript directory:
   - Encode the current working directory path by replacing `/` with `-` and removing the leading `-`
   - The transcript dir is `~/.claude/projects/<encoded-path>/`

2. List all directories in `~/.claude/projects/` and find candidates that match this project by keywords (folder name, project name fragments).

3. Show the user the candidates found and which one(s) look like the old location.

4. Copy the `.jsonl` transcript files from the old location to the current one:
   - First clear extended attributes: `xattr -c "<old-dir>"/*.jsonl`
   - Then copy: `cp "<old-dir>"/*.jsonl "<current-dir>/"`

5. Confirm success and tell the user to try `/resume`.

If multiple candidates exist, ask the user which one to use. If none found, report that no matching old transcripts were located.
