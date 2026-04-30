# @niivue/pwa

## 0.1.0

### Minor Changes

- 62ecdef: Add keyboard shortcuts

### Patch Changes

- 23028fd: shift+drop adds files as overlays to the last canvas instead of creating new ones
  overlay handler resolves index -1 to last canvas with bounds check
  HeaderBox now uses signal effect instead of stale useEffect dependency
  added onVolumeUpdated callback to ExtendedNiivue, called after load
- c4394cb: Fix MHD files loading as a black image. MHD is a detached format where voxel data lives in a separate `.raw` file referenced by `ElementDataFile` in the header. NiiVue's URL-based loader does not auto-detect the paired `.raw` URL for MHD files, so the extension now parses the header, resolves the raw file URI, and passes it to the webview as `urlImgData` (URL path) or `pairedData` (binary-data path). The webview forwards `urlImgData` to NiiVue's `loadImages` call and uses a Blob URL to load `pairedData` when binary buffers are provided.
- 79610b8: Initial configuration for automated independent releases via Changesets.
- Updated dependencies [27432cf]
- Updated dependencies [23028fd]
- Updated dependencies [c4394cb]
- Updated dependencies [79610b8]
- Updated dependencies [62ecdef]
  - @niivue/react@0.2.0
