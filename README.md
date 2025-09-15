# Foghorn

A language for declarative econometrics.

[![License: PolyForm Noncommercial](https://img.shields.io/badge/license-PolyForm%20Noncommercial-blue)](./LICENSE)
[![GHC](https://img.shields.io/badge/GHC-9.6%2B-brightgreen)](https://www.haskell.org/ghc/)
[![Build](https://img.shields.io/badge/build-cabal-informational)](#)

---

## Overview

**Foghorn** is a **declarative language for econometric research**. Rather than writing step-by-step data manipulation code followed by estimation procedures, researchers simply **define their specifications and variables**. **Foghorn** then infers the correct sequence of operations, automatically transpiling the specification into standard SQL and estimation languages. In other words, researchers do **not** need to implement data-handling workflows manually—-**Foghorn** derives them directly from the specification.

**Foghorn** is composed of several libraries that work together to provide a **generalized framework for writing econometric specifications**. These include:

_foghorn-dsl_

At its core is an **embedded domain-specific language (EDSL)** for expressing variable definitions and model specifications. Leveraging type-level programming, Foghorn encodes econometric logic directly into the type system. Unlike traditional approaches—where econometric processes interpret data definitions only at run time—-**Foghorn** can reason about specifications **before execution**. This capability eliminates the need for researchers to manually define data-processing steps, allowing them to focus on the **economic substance** of their models. Because its rules are expressed in terms of **general econometric indices and data types, Foghorn** remains agnostic to specific research domains or model classes.

_foghorn_modules_

**Topic modules** in **Foghorn** supply the **concrete context** for econometric research. Each module pairs a database (e.g., PostgreSQL) with definitions that describe its structure and variable schemas. Researchers can then import these modules to write their econometric specifications.

By leveraging **functional composition, Foghorn** enables researchers to **assemble complex, reusable workflows** from simple, well-defined building blocks—making the construction of sophisticated analyses both modular and efficient.

_foghorn_transpilers_

**Foghorn** translates high-level econometric specifications into **step-by-step data manipulation** and estimation procedures written in standard languages such as SQL and Stata. This process—known as **transpiling**—is widely used in programming to extend existing languages with additional features and type safety ([See this wikipedia article](https://en.wikipedia.org/wiki/Source-to-source_compiler)).

Transpiling in **Foghorn** creates **bi-directional transparency** in econometric research. The high-level specification offers a **top-down view**, highlighting variable definitions and key assumptions, while the transpiled code provides a **bottom-up view**, detailing the concrete data transformations starting from the raw inputs.


--- 

## Current status

**Foghorn** itself is complete, but many of its supporting libraries currently have only basic documentation. I am progressively adding these libraries to the repository as I expand their documentation.

At present, only one topic module has been completed, as my current **Foghorn**-based projects focus primarily on Corporate Finance. If you’re interested in collaborating or discussing other potential applications, please contact me via my UNSW email.

I plan to share demonstration videos once the core libraries are fully documented and available.

---

## Installation

Foghorn is not yet on Hackage. For now, please recursively clone this central repository.

> git clone --recurse-submodules git@github.com:tumarkin/foghorn

--- 

## Compatibility

- GHC: 9.6+  
- Build tool: `cabal`  
- OS: Linux/macOS/Windows (standard GHC/cabal environments)

---

## Repository structure

This project home currently has the following libraries:

#### _foghorn-base_

This library defines the economic data types recognized by Foghorn. These include standard types such as text, integers, and floating-point numbers; multiple date variants (e.g., Date, TradingDate, MonthEnd, DataDate); and specialized types for particular applications or databases (e.g., SIC codes, GVKEYs, and PERMNOs).

Unlike most languages, which group variables primarily by representation (e.g., treating all dates as a single type), Foghorn distinguishes between specific variants to improve its econometric reasoning. The library also defines econometric index types—including Panel, TimeSeries, and CrossSection—and provides utility functions for working with both data types and indices at the term level and type level.

#### _foghorn-data-xxx_

These libraries define the variable schemas for commonly used economic datasets but do not include the underlying data, which must be sourced from the respective providers. Each library specifies both the indexing scheme and the data type for every variable in a table.
 
For example, the foghorn-data-comp library includes the module Foghorn.Data.Compustat.Funda, which tells Foghorn how to interpret Compustat’s fundamentals data. It identifies whether each variable is text, numeric, or another type, and it specifies that the panel is indexed cross-sectionally by Gvkey and over time by DataDate.

---

## Documentation

- Currently, each sub-module has documentation linked through its README.md. Click into the sub-module and then scroll down to find the link to the online documentation. 
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
- Maintained on a **non-commercial, academic** basis. Support is on a best-effort basis; response times may vary.

