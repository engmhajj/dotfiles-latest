# Contents

<!-- toc -->

- [Symlink backup verification commands](#symlink-backup-verification-commands)
  - [List all the files and backups](#list-all-the-files-and-backups)
  - [Deletion original files and directories](#deletion-original-files-and-directories)
  - [Simulate replacement of existing dirs and symlinks](#simulate-replacement-of-existing-dirs-and-symlinks)
  - [See all the files and backups](#see-all-the-files-and-backups)
  - [Delete all the backups](#delete-all-the-backups)

<!-- tocstop -->

## Symlink backup verification commands

I used all the following to make sure that the sylink backup process works as
expected, it seems to be working as expected

### List all the files and backups

```bash
# These are files
ls -l /Users/mohamadelhajhassan/.vimrc*
ls -l /Users/mohamadelhajhassan/github/obsidian_main/.obsidian.vimrc*
ls -l /Users/mohamadelhajhassan/.zshrc*
ls -l /Users/mohamadelhajhassan/.tmux.conf*
ls -l /Users/mohamadelhajhassan/.config/alacritty/alacritty.toml*
ls -l /Users/mohamadelhajhassan/.yabairc*

# Below ones are directories
ls -ld /Users/mohamadelhajhassan/.config/nvim*
ls -ld /Users/mohamadelhajhassan/.hammerspoon*
ls -ld /Users/mohamadelhajhassan/.config/karabiner*
```

### Deletion original files and directories

- To delete all the original files and directories and confirm they will be
  recreated

```bash
# These are files
rm /Users/mohamadelhajhassan/.vimrc
rm /Users/mohamadelhajhassan/github/obsidian_main/.obsidian.vimrc
rm /Users/mohamadelhajhassan/.tmux.conf
rm /Users/mohamadelhajhassan/.config/alacritty/alacritty.toml
rm /Users/mohamadelhajhassan/.yabairc

# Below ones are directories
rm -r /Users/mohamadelhajhassan/.config/nvim
rm -r /Users/mohamadelhajhassan/.hammerspoon
rm -r /Users/mohamadelhajhassan/.config/karabiner
```

### Simulate replacement of existing dirs and symlinks

This will delete all the original files and directories, in case they're
symlinks, then re-create them as regular files with test data Useful to test
backup funcionality

```bash
# These are files
rm /Users/mohamadelhajhassan/.vimrc
rm /Users/mohamadelhajhassan/github/obsidian_main/.obsidian.vimrc
rm /Users/mohamadelhajhassan/.tmux.conf
rm /Users/mohamadelhajhassan/.config/alacritty/alacritty.toml
rm /Users/mohamadelhajhassan/.yabairc

# Below ones are directories
rm -r /Users/mohamadelhajhassan/.config/nvim
rm -r /Users/mohamadelhajhassan/.hammerspoon
rm -r /Users/mohamadelhajhassan/.config/karabiner

echo "# Test file auto created" > /Users/mohamadelhajhassan/.vimrc
echo "# Test file auto created" > /Users/mohamadelhajhassan/github/obsidian_main/.obsidian.vimrc
echo "# Test file auto created" > /Users/mohamadelhajhassan/.tmux.conf
echo "# Test file auto created" > /Users/mohamadelhajhassan/.config/alacritty/alacritty.toml
echo "# Test file auto created" > /Users/mohamadelhajhassan/.yabairc
mkdir -p /Users/mohamadelhajhassan/.config/nvim
echo "echo 'Test content'" > /Users/mohamadelhajhassan/.config/nvim/testfile.sh
mkdir -p /Users/mohamadelhajhassan/.hammerspoon
echo "echo 'Test content'" > /Users/mohamadelhajhassan/.hammerspoon/testfile.sh
mkdir -p /Users/mohamadelhajhassan/.config/karabiner
echo "echo 'Test content'" > /Users/mohamadelhajhassan/.config/karabiner/testfile.sh
```

### See all the files and backups

```bash
# These are files
ls -l /Users/mohamadelhajhassan/.vimrc*
ls -l /Users/mohamadelhajhassan/github/obsidian_main/.obsidian.vimrc*
ls -l /Users/mohamadelhajhassan/.zshrc*
ls -l /Users/mohamadelhajhassan/.tmux.conf*
ls -l /Users/mohamadelhajhassan/.config/alacritty/alacritty.toml*
ls -l /Users/mohamadelhajhassan/.yabairc*

# Below ones are directories
ls -ld /Users/mohamadelhajhassan/.config/nvim*
ls -ld /Users/mohamadelhajhassan/.hammerspoon*
ls -ld /Users/mohamadelhajhassan/.config/karabiner*
```

### Delete all the backups

```bash
# These are files
rm /Users/mohamadelhajhassan/.vimrc_backup_*
rm /Users/mohamadelhajhassan/github/obsidian_main/.obsidian.vimrc_backup_*
rm /Users/mohamadelhajhassan/.zshrc.backup
rm /Users/mohamadelhajhassan/.tmux.conf_backup_*
rm /Users/mohamadelhajhassan/.config/alacritty/alacritty.toml_backup_*
rm /Users/mohamadelhajhassan/.yabairc_backup_*

# Below ones are directories
rm -r /Users/mohamadelhajhassan/.config/nvim_backup_*
rm -r /Users/mohamadelhajhassan/.hammerspoon_backup_*
rm -r /Users/mohamadelhajhassan/.config/karabiner_backup_*
```
