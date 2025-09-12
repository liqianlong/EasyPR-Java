## Util

Filesystem helpers.

Package: `org.easypr.util`

### Public API

- `static void getFiles(String path, Vector<String> files)`
  - Recursively collects file paths under `path`.

- `static void recreateDir(String dir)`
  - Deletes the directory if present, then creates it.
