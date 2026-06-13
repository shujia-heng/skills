# Skills

A collection of specialized agent skills and utilities.

## Projects

### migrate-transcripts

A skill for managing conversation transcript migration when moving projects to new locations.

**Purpose**: When you move a project folder to a new location, the transcript history for `/resume` becomes inaccessible. This skill helps you find and migrate old transcripts from the previous project location to the new location.

**What it does**:
1. Identifies the current project's transcript directory by encoding the working directory path
2. Searches `~/.claude/projects/` for candidate directories that match your project
3. Lets you select which old location to migrate from
4. Copies all `.jsonl` transcript files to the new location
5. Clears extended attributes and confirms success

**Usage**: Invoke this skill when you want to restore `/resume` functionality after moving a project folder.

## License

See [LICENSE](LICENSE) for details.
