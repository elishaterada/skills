# Special cases

Read only the sections relevant to the current targets. Paths and product behavior vary; identify the actual owner and current supported controls instead of copying a deletion recipe from another machine.

## App caches and offline state

A browser profile contains both replaceable cached responses and valuable cookies, IndexedDB, local storage, downloads and unsynced drafts. A service-worker CacheStorage directory can hold offline content. Do not clear an entire profile for a cache-only request, and do not infer synchronization from an app being closed. If sync is blocked by an old app, an error or lack of connectivity, retain the uncertain state or make and verify a private recovery copy before clearing approved caches.

Prefer closing the app before filesystem cache cleanup. If the host can safely remove closed, old cache entries without disrupting a running app, restrict the action to a verified disposable entry format. Preserve open files, recent writes, indexes and journals. Otherwise defer that group until the app can close safely. Do not stop the user's active agent app without a concrete continuation plan.

Clear Adobe or other creative-app caches separately from source media, catalogs, project files and autosaves. Use official uninstallers for app removal and preserve other installed products and shared components. Review the actual final uninstaller state and installed files.

Downloaded browser builds, models and runtimes can be needed by multiple apps. Inspect current package registrations, process use and dependencies before removing old versions. A downloaded transcription model may support dictation. An agent runtime may be executing this cleanup. Explain re-download or reinstall consequences.

## Cloud files and operating-system storage

Prefer a provider's supported local-only removal or online-only action when the user wants to free local storage. Ordinary deletion in a synced folder may propagate to every device and the cloud. Confirm sync and the exact scope before acting. A placeholder's logical size does not show locally occupied bytes.

Do not treat OS storage categories, protected metadata, Mail/Messages stores, photo libraries, restore points or snapshots as generic junk. Identify the actual files and use supported maintenance tools. Backup thinning and removing the only backup require an explicit retention decision. Do not empty Trash unless that irreversible step is within the approved scope and host rules permit it.

## Virtual machines and databases

Inspect allocated VM image size, active users and guest state. A VM directory can combine downloadable base images with unique session disks, mounted projects and credentials. An origin/version marker is not automatically a checksum. If uniqueness cannot be ruled out, preserve the complete needed state in a verified compressed archive before removing the live VM. Protect permissions and account for the archive's own space.

For databases, inspect size and available reclaimable pages read-only when appropriate. A large database with few free pages will not shrink much through compaction. Follow supported app maintenance with the app stopped and a consistent backup. Do not independently remove SQLite WAL/SHM files, caches used as databases, or app history based on the filename.

## Duplicates and compression

Use file size to narrow candidates, then compare full content hashes. Recheck source identity and content before mutation. Equal filenames, timestamps, appearance or partial hashes do not establish duplicates. Byte identity alone does not mean every path is disposable; applications or backups may require those paths.

Prefer filesystem-native copy-on-write clones when all paths must remain independently editable. Hardlinks couple writes across paths and are unsuitable for that requirement. Preserve permissions, links and relevant metadata. Do not deduplicate files actively being written. Compression and deduplication need enough working space and a verified recovery path for unique data.

When verifying a tar archive, handle expected metadata entries, such as macOS AppleDouble files, without overlooking missing or changed real files. Validate decompression completion and each expected payload. If a local baseline, shared object store, external disk or cloud account is required to restore, document and retain it.

A local archive is still stored on the same machine. Label it accurately; do not describe it as an off-device or disaster-recovery backup. No single compression ratio or deletion total predicts physical savings on a shared-block filesystem.
