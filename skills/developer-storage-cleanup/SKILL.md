---
name: developer-storage-cleanup
description: Reclaim developer-machine storage in repositories, Git worktrees, build caches, package stores, SDKs, simulators, containers and local VMs while preserving unfinished work, credentials, source assets and recovery data. Use for large repos or development tooling; general personal-file cleanup is outside its primary focus.
---

# Developer storage cleanup

Find the storage that development tools retain and retire only the approved inactive material. This skill is self-contained. Use available native tools and installed package managers; no other skill or automation framework is required.

## Inventory the actual machine

Measure volume free space and the largest relevant development directories before choosing an action. Drill down in bounded steps. Record inaccessible areas and keep reports outside repositories. Folder totals may double-count hardlinks or copy-on-write clones; sparse disk capacity is not allocation, and moving files to another directory on the same disk is not reclaiming space.

Separate these categories for each large checkout:

- Current Git-tracked source, assets and evidence, even when the directory looks temporary.
- Git's object/history store, resolving a worktree's shared Git directory rather than assuming every `.git` is a private folder.
- Untracked and ignored files, including private inputs as well as rebuildable output.
- Dependencies, generated builds, old release/rollback copies and tool downloads.

Use Git's actual inventory and worktree registry. Status alone excludes ignored inputs. Inspect package/SDK/container registries and live processes rather than deciding from size or age. Do not print environment-file contents or credentials.

## Choose the smallest useful cleanup

A broad audit request permits diagnosis, not wholesale pruning. Present concrete groups with their reported size, owner, regeneration cost, activity and unique-data risks. Act within the user's current authorization, without asking again for an unchanged approved scope. Reconfirm if new unique data or a materially different operation appears. Host confirmation rules still apply.

Start with retired generated builds and unused cache/tool versions. Keep current rollback and previous-client support until the relevant release is retired. A clean worktree, old branch or stopped container is not automatically disposable.

Before each group, recheck the exact approved paths, registry state, active processes, open files and pending changes. Keep symlinks and mounted paths from escaping that scope. Pause the affected group on a lock, changed ownership or live work; continue independent approved groups. Do not force-quit working apps or stop another active agent.

For repository/worktree removal, read [worktree recovery](references/worktree-recovery.md). For package caches, SDKs, containers, agent data, browsers and VMs, read only the relevant parts of [tool storage](references/tool-storage.md).

## Preserve work and prove recovery

Keep unfinished changes, unique commits, ignored private files, original audio/art, project databases, credentials, AI conversations and important source/provenance unless their removal is specifically authorized. Removing caches does not imply permission to remove profiles or history.

Prepare a private recovery copy outside the target when needed. Verify bytes, links, necessary metadata and a practical restoration before removing unique state. Confirm the source remained unchanged. A bundle that depends on main history is not standalone; a checkout from a shared object store alone does not prove that the archive contains the needed objects.

Do not merge, cherry-pick, rewrite history, push, delete branch refs or alter deployed services merely to make storage cleanup easier. Obtain the user's authorization for those separate changes. Retain a compact patch or archive for valuable experiments rather than silently integrating an entire stale branch.

## Verify and prevent recurrence

Remove one approved group, verify its result and required tools, then continue. Resume partial failures from verified state without expanding the deletion. Report removed, archived, retained and blocked items, restore dependencies, reported folder reduction and same-volume free-space readings. Include recovery archive overhead and concurrent activity in the accounting. Stop when additional cleanup risks unique data or provides negligible benefit.

Propose short retention rules and task-closeout cleanup where useful. Apply repository policy changes only within the requested scope. Keep raw screenshots, traces, videos, audits and build copies out of commits by default; commit concise decisions and necessary verification summaries. Preserve intentional source assets and test fixtures. An ignore rule affects new files, not already tracked evidence. Retiring historical tracked captures is a separate reviewed Git change, and deleting them from the current tree does not shrink existing history.
