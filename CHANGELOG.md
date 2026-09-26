# Change Log

All notable changes to the "onedark-vibrant-vscode" extension will be documented in this file.

## 1.7.0

- VS Code: with rust-analyzer semantic highlighting on, std types (`Box`, `Vec`, `String`, `Option`) and primitives are teal, enum variants are yellow where declared and blue where used, and `Some`, `None`, `Ok` and `Err` are yellow.
- Helix: enum variant definitions are yellow again. Constructors stay blue.

## 1.6.0

- VS Code: namespaces are yellow italic, numeric and primitive types are teal, and Rust attribute names like `derive` are cyan.
- Helix: character literals are green like strings, and enum variant definitions are blue like constructors. `Some`, `None`, `Ok` and `Err` stay yellow.

## 1.5.0

- Builtin types are teal #60D1C3, set apart from cyan builtin functions.

## 1.4.0

- Blue is #81BCF1 (was #6DB3F2): lighter, at 8.5:1 contrast on the editor background.

## 1.3.1

- README covers the VS Code theme; Helix setup moves to helix-themes/README.md.

## 1.3.0

- Added semantic token colors for Nix, including markdown styles for embedded markdown.
- Suggests Helix Nix Highlighting for Nix files.

## 1.2.0

- Fixed theme path casing in package.json.
- Added repository and license information to package.json.
- Implemented option to color JSON string quotes to match key/value colors.
- Added Nix / NixOS Home Manager modules for Helix theme integration.

## 1.0.0

- Initial release
