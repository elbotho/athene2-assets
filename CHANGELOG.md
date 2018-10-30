# Changelog

All notable changes to this project will be documented in this file. The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

## [3.0.0] - 2017-10-30

### Added

- Dynamically import the new editor and its renderer. This leads to a much smaller bundle size for the initial load.
- Automated blue-green deployment of athene2-assets and server side renderer for new editor
- Automated deployment of Cloudflare workers
- Log version to browser console
- Add a content hash of length 8 to file names of chunks and assets (e.g. fonts and images)

### Changed

- Upgrade to Webpack 4

### Fixed

- Load all plugins in render server for new editor
- When server side rendering fails, still pass state down to client for improved debugging
- Hide double sidebar outside the editor

### Breaking Changes

- Removed `CommonsChunkPlugin`, i.e. there are no more `commons.js` and `common.css`
- Renamed `editor` to `legacy-editor`, i.e. one has to include `legacy-editor.js` resp. `legacy-editor.css` instead of `editor.js` resp. `editor.css`
- Asset bundle moved to `https://packages.serlo.org/athene2-assets@a/` resp. `https://packages.serlo.org/athene2-assets@b/` (blue-green deployment)
- Google Cloud Function moved to `https://europe-west1-serlo-assets.cloudfunctions.net/editor-renderer-a` resp. `https://europe-west1-serlo-assets.cloudfunctions.net/editor-renderer-b` (blue-green deployment)
- Needs an element with id `ory-editor-meta-data-wrapper` around the element with id `ory-editor-meta-data`

## [2.0.4] - 2017-09-28

[unreleased]: https://github.com/serlo-org/athene2-assets/compare/3.0.0...HEAD
[3.0.0]: https://github.com/serlo-org/athene2-assets/compare/3.0.0...6f69feb2bd6d4da735e760d3d640717b900f5959
[2.0.4]: https://github.com/serlo-org/athene2-assets/commit/6f69feb2bd6d4da735e760d3d640717b900f5959