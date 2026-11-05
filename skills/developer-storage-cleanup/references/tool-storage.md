# Tool storage

Identify actual ownership and installed versions on the current OS. Paths below describe categories, not a deletion allowlist.

## Build output and release copies

Generated output can live in ignored directories, tracked evidence, or old deployment folders with names such as `previous` and `recovery`. Inspect contents. Keep current rollback bytes, immutable assets needed by previous clients, source maps needed for a live incident and unique source inputs until their owners retire them. Do not run broad clean commands that also delete ignored secrets or local databases. Removing tracked files does not remove their historical objects; routine cleanup does not justify a history rewrite.

## Package stores, SDKs and testing browsers

Use the package manager's supported inventory and cleanup when available. Shared stores can serve multiple projects. Keep lockfiles, source/configuration, signing keys, keystores and working environments. Reinstalling packages has time and bandwidth costs.

Automation-browser caches often contain several versions referenced by different Playwright/Puppeteer installations. Inspect live package registrations and processes. Retain versions required by any installed active client; deleting a browser cache wholesale can break the agent performing the cleanup.

Remove obsolete simulator devices, runtimes and device-support files by their registered IDs through supported tooling. Save state or project-specific device data may be unique. A large Android directory can contain both disposable emulator images and valuable keystores/configuration. Do not infer authorization to remove shared SDKs from the retirement of one app project.

## Containers and local VMs

Inventory images, build cache, containers, volumes and allocated disk-image space separately. Stopped containers may contain unique writable data. Volumes are persistent data, not rebuildable cache. Avoid a blanket prune, especially one that includes volumes, when only unused images/build cache were approved. Do not manually remove an engine's live disk image. Use supported pruning/compaction and verify both the engine and host free space afterward.

VM folders can combine a downloadable OS with unique session disks and guest-installed work. Check activity and all needed state before uninstalling or compacting them. If image provenance does not establish disposability, verify a compressed recovery copy before removing the live image. Document the disk, metadata and baseline needed to restore, and subtract archive size from the savings estimate.

## AI agents, app profiles and databases

Separate conversation logs, history/index databases, generated artifacts, worktrees, browser caches and runtime downloads. Large session logs may already be compressed. Keep conversations unless their removal is specifically requested. A history database with little free space has little to gain from compaction; never remove its journals or duplicate-looking stores on inference alone.

Browser profiles contain cookies, IndexedDB, local storage and offline caches alongside ordinary cached responses. Preserve sign-ins and unsynced state. Check open files and app state; do not force-quit the user's editor or current agent. If a cloud app cannot confirm synchronization, preserve uncertain local data in a verified private recovery copy before approved clearing. Keep an active agent's primary runtime, required tool libraries and browser versions.

## Deduplication and archives

Compare full content hashes after narrowing by size, then recheck identity/content before mutation. Preserve all required paths and metadata. Prefer native copy-on-write clones for independently editable copies; hardlinks couple writes. Do not deduplicate files being written or assume matching names/partial hashes prove identity. Measure actual free space after the operation, because cloned files can report large duplicated folder totals while using shared physical blocks.

Verify archive payload bytes and restoration, not just compressor exit status. Handle expected platform metadata without ignoring changed real files. Keep reports and inventories outside Git and do not publish credentials or private file lists. Local archives remain on the same machine and may depend on a retained repository; label those limits clearly.
