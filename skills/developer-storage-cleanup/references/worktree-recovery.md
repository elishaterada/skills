# Worktree recovery

## Establish ownership

Obtain paths from `git worktree list --porcelain`, using a NUL-delimited form when supported. Respect locks and managed-app ownership. Cross-check active and pinned chats, current project tasks, spawned worktrees, previews, aliases and running tools. A merged tree used by an ongoing task stays active. Filesystem inactivity alone is insufficient.

Resolve shared Git storage through `git rev-parse --git-common-dir`. Use read-only inventory commands with optional index locking disabled where supported. Account separately for the checked-out tracked files, shared history and ignored files. Inspect status with untracked files and submodules included, then inspect ignored files as a separate set. Original masters, `.env` files, browser state and release recovery data can all be ignored.

## Preserve before retirement

Record the exact HEAD, branch or detached state, index/staged state, working changes and private/untracked files. A diff against HEAD does not contain ignored files and does not alone preserve the distinction between staged and unstaged work. Include deletions and symlink targets. Inspect nested repositories and submodules; work inside them needs its own preservation.

Inspect the worktree's HEAD reflog for unique commits that no retained ref reaches, including detached work. Preserve those tips before unregistering the tree, because its HEAD reflog can disappear with it. Keep needed environment configuration and restoration metadata without exposing secrets.

For an approved archive, choose a compact recovery format rather than copying every dependency. Preserve package manifests and locks; omit only demonstrated regenerable dependencies/builds. Keep unique inputs and source assets. Protect archive permissions, record a manifest and test that the exact working state and private files can be recreated.

A Git bundle may be standalone or incremental. State its prerequisites. For incremental recovery, verify prerequisites against a retained baseline and force ingestion of the actual bundle pack in a separate validation repository. Check that required branch-specific and snapshot objects are in that pack. A shared clone can read missing objects from the live source and mask an incomplete archive. Protect restored snapshot/reflog commits with durable refs; merely unpacking objects does not keep them reachable through garbage collection.

Existing branch refs are useful but do not replace preservation of uncommitted or ignored work. A stash is not a universal backup and may omit private inputs. Do not assume a managed app's archive includes ignored files or every reflog tip; verify its documented behavior and preserve omissions separately.

## Remove and verify

Use the owning app's supported archive operation when it can handle this tree. Some tools can archive only attachments owned by the current chat. Do not attach an unrelated chat's worktree or bypass a locked/protected tree to force archival. A filesystem fallback needs explicit scope authorization, verified preservation and an inactivity check; label it a local recovery archive rather than claiming native one-click restoration.

Recheck HEAD, branch, staged/unstaged changes, file set, activity and locks immediately before removal. Use Git's worktree removal for an approved unmanaged tree. If removal partly unregisters it but leaves files, inspect those leftovers before deleting them; do not assume an error meant nothing changed. Keep an exact path allowlist and stop on unexpected contents.

Verify the surviving registry, retained commits and inputs, preview processes, task-specific routes and any running infrastructure. Do not kill a stored PID without confirming its current identity, or retire a shared alias based only on its name. Keep review-world databases independent of disposable previews. Branch deletion and remote changes require their own authorization and expected-tip checks.
