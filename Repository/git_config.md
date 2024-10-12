# Git Config Overview

The `git config` command is used to set and get Git configuration values at various levels: **local**, **global**, and **system**. These configurations help customize Git's behavior, like setting your username, email, and default editor.

## Configuration Levels

1. **Local (`--local`)**:
   - Applies only to the repository you’re currently in.
   - Stored in `.git/config` within the project directory.
   - Default level if no other level is specified.

2. **Global (`--global`)**:
   - Applies to the current user across all repositories.
   - Stored in `~/.gitconfig` on Unix and `C:\Users\<username>\.gitconfig` on Windows.

3. **System (`--system`)**:
   - Applies to all users and repositories on the system.
   - Stored in `/etc/gitconfig` on Unix or `C:\ProgramData\Git\config` on Windows.

**Priority Order**: Local > Global > System.

## Basic Usage

To display a configuration value:

```bash
git config user.email
```

To set a value:

```bash
git config --global user.email "your_email@example.com"
```

## Setting the Default Editor

Git often uses a text editor for various commands (e.g., commit messages). You can set your preferred editor with:

- Atom: `git config --global core.editor "atom --wait"`
- Vim: `git config --global core.editor "vim"`
- Nano: `git config --global core.editor "nano -w"`

## Merge Tools

Git uses merge tools for resolving conflicts. You can set a preferred merge tool like:

```bash
git config --global merge.tool kdiff3
```

## Colored Output

Git supports colored output for better readability. The main setting is `color.ui`:

- **Disable Colors**: `git config --global color.ui false`
- **Enable Colors**: `git config --global color.ui auto`

Other color configurations (e.g., for branches, diffs, status) can be set for specific outputs.

## Git Aliases

Aliases are shortcuts for common commands. Examples:

- Shorten `git commit` to `git ci`:
  ```bash
  git config --global alias.ci commit
  ```

- Create an alias for amending commits:
  ```bash
  git config --global alias.amend "commit --amend"
  ```

## Formatting & Whitespace

Git can highlight whitespace issues in diffs:

- **Enabled by Default**:
  - `blank-at-eol`: Highlights extra spaces at the end of lines.
  - `space-before-tab`: Highlights spaces before tabs in indentation.
  - `blank-at-eof`: Highlights blank lines at the file end.

- **Optional**:
  - `tabwidth`: Defines tab width (default is 8, range is 1-63).

---

### Summary

- `git config` customizes Git behavior by modifying configuration files.
- Config levels: **Local**, **Global**, and **System**.
- Common uses:
  - Set username/email.
  - Change the default editor.
  - Adjust color output.
  - Create command aliases.
  - Highlight whitespace issues.