| Command & Example                                  | Description                                                      | Example Usage                                                        |
|----------------------------------------------------|------------------------------------------------------------------|----------------------------------------------------------------------|
| jj git init                                        | Initialize a Git-backed repository with jj                       | jj git init                                                          |
| jj clone <repo-url>                                | Clone a remote repository (using Git, then initialize jj)        | git clone https://github.com/user/repo.git<br>cd repo<br>jj git init |
| jj file track .                                    | Track files in the current directory                             | jj file track .                                                      |
| jj commit -m ""message""                           | Commit current changes with a message                            | jj commit -m ""Initial commit""                                      |
| jj new                                             | Create a new commit for the next change                          | jj new                                                               |
| jj describe -m ""description""                     | Set or change commit description                                 | jj describe -m ""Refactored login flow""                             |
| jj git remote add origin <repo-url>                | Add a remote repository                                          | jj git remote add origin https://github.com/user/repo.git            |
| jj git push -c @-                                  | Push the parent of the working copy commit to remote             | jj git push -c @-                                                    |
| jj bookmark create <name>                          | Create a named bookmark (branch)                                 | jj bookmark create foo                                               |
| jj git push --allow-new                            | Push new bookmarks to remote                                     | jj git push --allow-new                                              |
| jj status                                          | Show status of working copy and current commit                   | jj status                                                            |
| jj diff                                            | Show differences between commits                                 | jj diff                                                              |
| jj log                                             | Show commit history                                              | jj log                                                               |
| jj git fetch                                       | Fetch changes from the default remote                            | jj git fetch                                                         |
| jj git fetch --remote origin                       | Fetch changes from a specific remote                             | jj git fetch --remote origin                                         |
| jj git fetch --all-remotes                         | Fetch changes from all configured remotes                        | jj git fetch --all-remotes                                           |
| jj bookmark list                                   | List all local bookmarks                                         | jj bookmark list                                                     |
| jj bookmark list --all-remotes                     | List all local and remote bookmarks                              | jj bookmark list --all-remotes                                       |
| jj edit <bookmark-name>                            | Switch working copy to a different bookmark                      | jj edit main                                                         |
| jj edit <bookmark-name> --ignore-immutable         | Switch to a bookmark, bypassing immutability                     | jj edit main --ignore-immutable                                      |
| jj bookmark set <name> -r <revision>               | Set a bookmark to point to a specific revision                   | jj bookmark set foo -r abc123                                        |
| jj bookmark rename <old-name> <new-name>           | Rename a bookmark                                                | jj bookmark rename foo boo                                           |
| jj bookmark delete <bookmark-name>                 | Delete a bookmark and mark for remote deletion                   | jj bookmark delete foo                                               |
| jj bookmark delete glob:*                          | Delete all bookmarks (using wildcard)                            | jj bookmark delete glob:*                                            |
| jj bookmark forget <bookmark-name>                 | Delete a local bookmark without affecting remote                 | jj bookmark forget foo                                               |
| jj bookmark forget glob:*                          | Forget all local bookmarks without remote deletion               | jj bookmark forget glob:*                                            |
| jj bookmark track <bookmark>@origin                | Start tracking a remote bookmark locally                         | jj bookmark track main@origin                                        |
| jj abandon <revset>                                | Abandon (delete) specified commits/revisions                     | jj abandon abc123                                                    |
| jj abandon ""root()..@"" --ignore-immutable        | Abandon all commits from root to current, bypassing immutability | jj abandon ""root()..@"" --ignore-immutable                          |
| jj rebase -b <bookmark> -d <destination>           | Rebase a bookmark onto a destination bookmark/commit             | jj rebase -b foo -d main                                             |
| jj git push --bookmark <name>                      | Push a specific bookmark to the remote                           | jj git push --bookmark foo                                           |
| jj git push --deleted                              | Push bookmark deletions to the remote                            | jj git push --deleted                                                |
| jj git push --bookmark <name> --force              | Force-push a bookmark to overwrite remote history                | jj git push --bookmark foo --force                                   |
| jj resolve <file-name>                             | Resolve conflicts in a file using a merge tool                   | jj resolve main.py                                                   |
| jj resolve <file-name> --tool :ours                | Resolve conflict by accepting one side (ours)                    | jj resolve main.py --tool :ours                                      |
| jj resolve <file-name> --tool :theirs              | Resolve conflict by accepting the other side (theirs)            | jj resolve main.py --tool :theirs                                    |
| jj squash                                          | Incorporate conflict resolution into the current commit          | jj squash                                                            |
| jj undo                                            | Undo the last operation                                          | jj undo                                                              |
| jj op log                                          | Show operation history for potential recovery                    | jj op log                                                            |
| jj op restore <operation-id>                       | Restore repository state to a previous operation                 | jj op restore 12345678                                               |
| jj config get revset-aliases.""immutable_heads()"" | Check immutable commits configuration                            | jj config get revset-aliases.""immutable_heads()""                   |
| jj config set --user ui.merge-editor <tool>        | Set a custom merge editor for conflict resolution                | jj config set --user ui.merge-editor meld                            |
