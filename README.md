# Automatically Syncing iTerm2 Preferences with GitHub

## 1. Local Setup
#!/bin/zsh

- Initialize a git repository in the directory where your iTerm2 preferences are stored:

  \```zsh
  git init
  \```

- Add your GitHub repository or gist as a remote:

  \```zsh
  git remote add origin [YOUR_GITHUB_REPO_URL]
  \```

## 2. Automate the Push
# Automatically Syncing iTerm2 Preferences with GitHub

...

## 2. Automate the Push

- Create a script that detects changes in your iTerm2 preferences, commits those changes, and then pushes them to GitHub. Here's the script for `zsh`:

  \```zsh
  #!/usr/bin/env zsh

  # Navigate to the directory containing iTerm2 preferences
  cd /path/to/iterm2/preferences/directory

  # Check for changes
  if [[ $(git status -s) ]]; then
      # Add all changes
      git add .

      # Commit the changes
      git commit -m "Update iTerm2 preferences"

      # Push to GitHub
      git push origin master
  fi
  \```

- Save the script to a file, for example, `update_iterm_prefs.zsh`.
  
- Make the script executable:

  \```zsh
  chmod +x update_iterm_prefs.zsh
  \```

...


- Save the script to a file, for example, `update_iterm_prefs.sh`.
  
- Make the script executable:

  \```zsh
  chmod +x update_iterm_prefs.sh
  \```

## 3. Automate the Script Execution

- Use a tool like `launchd` (on macOS) to run the script periodically or upon specific triggers.

**Notes**:
- Ensure you have set up SSH keys or token authentication for git to push without requiring a password.
- This approach will push all changes in the directory, so be cautious about what else is in there.
- Always ensure you're not committing sensitive or personal information.
