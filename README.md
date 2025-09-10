# Foghorn

A language for declarative econometrics.

[![License: PolyForm Noncommercial](https://img.shields.io/badge/license-PolyForm%20Noncommercial-blue)](./LICENSE)
[![GHC](https://img.shields.io/badge/GHC-9.6%2B-brightgreen)](https://www.haskell.org/ghc/)
[![Build](https://img.shields.io/badge/build-cabal-informational)](#)

---

## Overview

This is the home repository for Foghorn. Foghorn libraries were developed without complete documentation. Libraries are added to this home as soon as the documentation is complete.

---

## Installation

Foghorn is not yet on Hackage. For now, please clone this central repository.

--- 

## Compatibility

- GHC: 9.6+  
- Build tool: `cabal`  
- OS: Linux/macOS/Windows (standard GHC/cabal environments)

---

## Documentation

- In-source **Haddock** comments describe kinds, indices, and constraints.  
- To build HTML docs locally:
  ```bash
  cabal haddock --enable-documentation \
    --haddock-html --haddock-hyperlink-source --haddock-quickjump all
  ```

---

## Contributing

Contributions are welcome, especially improvements to documentation, additional variable definitions, or clarifications to type-level design. Please open an issue to discuss your idea before submitting a pull request.

---

## License

PolyForm Noncommercial 1.0.0.   For any commercial use, contact **Rob Tumarkin <tumarkin@gmail.com>**.

---

## Changelog

See [CHANGELOG.md](./CHANGELOG.md).

---

## Maintainers & Support

**Maintainer**
- **Rob Tumarkin** — [@tumarkin](https://github.com/tumarkin)

**Getting Help**
- Review the in-code Haddock documentation.  
- Report bugs or unexpected behavior via the [issue tracker](https://github.com/tumarkin/foghorn/issues).  
- For feature ideas, open an issue with the `enhancement` label.

**Support Policy**
- Maintained on a **non-commercial, academic** basis. Support is **best-effort**; response times may vary.

