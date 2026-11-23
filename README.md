# CSI World Research Workspace

Eight-stage research tracker with benchmark records, model/harness reports, file evidence, reviewer feedback and encrypted backups.

## Use

Serve this directory through HTTPS or localhost. Unlock using the separately supplied workspace password. Changes save as encrypted browser-local IndexedDB data. To share, configure a repository-scoped GitHub fine-grained token with Contents read/write permission, fetch shared progress first, then publish. Tokens stay in page memory and are cleared by reload/lock. All editors use the same shared password. This is a team progress tracker with shared editing privileges, not a role-based approval system.

Research entries and attachments are AES-256-GCM encrypted with a PBKDF2-SHA256 key (310,000 iterations). Public source code and the encrypted vault remain accessible on GitHub Pages. Password strength determines resistance to offline guessing. Do not store GitHub credentials in research fields. A changed password requires re-encrypting the vault and migrating local backups.

Files are limited to 15MB each and 35MB total before encryption; large videos should use external storage links. Export backups regularly. Local records are not shared until publishing succeeds. Concurrent GitHub changes stop publishing and export a conflict backup, requiring manual reapplication. Clearing browser data removes unpublished local work.

## Hosting

GitHub Pages serves the repository root from main. Private repositories on GitHub Free cannot enable Pages. Keep the repository private unless its owner explicitly approves public visibility, or upgrade the organization / use another hosting provider.

## Development

Run `python3 -m http.server 8000` in this directory. No build step or runtime server is required. The initial workspace starts empty. Experimental progress must be entered by the researcher, not inferred from chat notes.
