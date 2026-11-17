# 🦀 Rust Assist Tools

[![Rust](https://img.shields.io/badge/language-Rust-orange?logo=rust)](https://www.rust-lang.org/)
[![Awesome](https://img.shields.io/badge/collection-curated-blue)](https://github.com/)
[![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-blue.svg)](CONTRIBUTING.md)

> A curated collection of useful Rust development tools, IDE extensions, plugins, language servers, debugging utilities, code formatters, linters, and productivity tools.

**Rust Assist Tools** aims to help Rust developers discover the best tools to improve their coding experience, productivity, debugging workflow, and project management.

Whether you are a beginner, experienced Rust developer, or systems engineer, this repository provides a collection of resources to make Rust development easier.

---

## 📑 Table of Contents

- [IDEs & Code Editors](#-ides--code-editors)
- [IDE Extensions & Plugins](#-ide-extensions--plugins)
- [Language Servers](#-language-servers)
- [Code Completion & Intelligence](#-code-completion--intelligence)
- [Debugging Tools](#-debugging-tools)
- [Code Formatting](#-code-formatting)
- [Linters & Static Analysis](#-linters--static-analysis)
- [Cargo & Package Management](#-cargo--package-management)
- [Testing Tools](#-testing-tools)
- [Performance & Profiling](#-performance--profiling)
- [Documentation Tools](#-documentation-tools)
- [AI Coding Assistants](#-ai-coding-assistants)
- [Terminal & Productivity](#-terminal--productivity)
- [Getting Started](#-getting-started)
- [Contributing](#-contributing)
- [License](#-license)

---

## 💻 IDEs & Code Editors

Popular IDEs and editors for Rust development.

| Tool | Description | Platform |
|---|---|---|
| [Visual Studio Code](https://code.visualstudio.com/) | Lightweight editor with extensive Rust extensions | Windows / Linux / macOS |
| [RustRover](https://www.jetbrains.com/rust/) | Dedicated Rust IDE by JetBrains | Windows / Linux / macOS |
| [IntelliJ IDEA](https://www.jetbrains.com/idea/) | Full-featured IDE with Rust plugin | Windows / Linux / macOS |
| [Neovim](https://neovim.io/) | Modern extensible terminal editor | Windows / Linux / macOS |
| [Helix](https://helix-editor.com/) | Modal editor with built-in LSP support | Windows / Linux / macOS |
| [Zed](https://zed.dev/) | High-performance collaborative code editor | macOS / Linux / Windows |
| [Emacs](https://www.gnu.org/software/emacs/) | Highly customizable development environment | Windows / Linux / macOS |
| [Sublime Text](https://www.sublimetext.com/) | Fast and lightweight code editor | Windows / Linux / macOS |
| [Visual Studio](https://visualstudio.microsoft.com/) | IDE with Rust integration options | Windows |

## VS Code starter config


{
  "rust-analyzer.check.command": "clippy",
  "editor.formatOnSave": true,
  "[rust]": {
    "editor.defaultFormatter": "rust-lang.rust-analyzer"
  },
  "editor.codeActionsOnSave": {
    "source.fixAll": "explicit"
  }
}
  
## Emacs config
File: ~/.emacs.d/init.el

;; Rust mode
(use-package rust-mode
  :ensure t
  :mode "\\.rs\\'"
  :hook (rust-mode . eglot-ensure))

;; LSP configuration
(use-package eglot
  :ensure t
  :hook (rust-mode . eglot-ensure))

;; Format on save
(add-hook 'rust-mode-hook
  (lambda ()
    (add-hook 'before-save-hook
      #'rust-format-buffer nil t)))


## 🧩 IDE Extensions & Plugins

Useful extensions that enhance the Rust development experience.

### Visual Studio Code

| Extension | Description |
|---|---|
| [rust-analyzer](https://marketplace.visualstudio.com/items?itemName=rust-lang.rust-analyzer) | Code completion, navigation, diagnostics and refactoring |
| [CodeLLDB](https://marketplace.visualstudio.com/items?itemName=vadimcn.vscode-lldb) | Rust debugging with LLDB |
| [Even Better TOML](https://marketplace.visualstudio.com/items?itemName=tamasfe.even-better-toml) | TOML syntax highlighting and validation |
| [Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens) | Displays errors and warnings inline |
| [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens) | Git history and code insights |
| [crates](https://marketplace.visualstudio.com/items?itemName=serayuzgur.crates) | Dependency version information for Cargo.toml |
| [Todo Tree](https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree) | Finds and organizes TODO comments |

### Neovim

| Plugin | Description |
|---|---|
| [rustaceanvim](https://github.com/mrcjkb/rustaceanvim) | Rust development integration |
| [nvim-lspconfig](https://github.com/neovim/nvim-lspconfig) | Language server configuration |
| [crates.nvim](https://github.com/Saecki/crates.nvim) | Cargo dependency management |
| [nvim-cmp](https://github.com/hrsh7th/nvim-cmp) | Completion framework |
| [conform.nvim](https://github.com/stevearc/conform.nvim) | Code formatting integration |
| [nvim-dap](https://github.com/mfussenegger/nvim-dap) | Debug Adapter Protocol integration |

### JetBrains IDEs

| Plugin / Tool | Description |
|---|---|
| [Rust Plugin](https://plugins.jetbrains.com/plugin/8182-rust) | Rust language support |
| [RustRover](https://www.jetbrains.com/rust/) | Dedicated Rust development IDE |
| [Native Debugging Support](https://plugins.jetbrains.com/) | Native debugging integration |

## ⚙️ Language Servers

Language servers provide IDE features through the Language Server Protocol (LSP).

| Tool | Description |
|---|---|
| [rust-analyzer](https://github.com/rust-lang/rust-analyzer) | Main Rust language server |
| [RLS](https://github.com/rust-lang/rls) | Legacy Rust Language Server |
| [tower-lsp](https://github.com/ebkalderon/tower-lsp) | Framework for building LSP servers in Rust |

**Recommended:** rust-analyzer is the primary choice for modern Rust IDE integration.

## 🧠 Code Completion & Intelligence

| Tool | Description |
|---|---|
| [rust-analyzer](https://rust-analyzer.github.io/) | Smart completion, type information and code navigation |
| [Tabnine](https://www.tabnine.com/) | AI-assisted code completion |
| [GitHub Copilot](https://github.com/features/copilot) | AI coding suggestions |
| [Codeium / Windsurf](https://windsurf.com/) | AI coding assistance |
| [Continue](https://www.continue.dev/) | Open-source AI coding assistant |

## 🐞 Debugging Tools

| Tool | Description |
|---|---|
| [CodeLLDB](https://github.com/vadimcn/codelldb) | LLDB debugger integration |
| [LLDB](https://lldb.llvm.org/) | Native debugger |
| [GDB](https://www.sourceware.org/gdb/) | GNU debugger |
| [Delve](https://github.com/go-delve/delve) | Primarily a Go debugger; not a standard Rust debugger |
| [Miri](https://github.com/rust-lang/miri) | Detects certain classes of undefined behavior |
| [cargo-expand](https://github.com/dtolnay/cargo-expand) | Displays expanded Rust macros |

## 🎨 Code Formatting

| Tool | Description |
|---|---|
| [rustfmt](https://github.com/rust-lang/rustfmt) | Official Rust code formatter |
| [dprint](https://dprint.dev/) | Pluggable code formatter |
| [Prettier](https://prettier.io/) | Formatter for supported web and configuration files |

## 🔍 Linters & Static Analysis

| Tool | Description |
|---|---|
| [Clippy](https://github.com/rust-lang/rust-clippy) | Rust linting and suggestions |
| [Miri](https://github.com/rust-lang/miri) | Experimental interpreter and UB checker |
| [cargo-audit](https://github.com/RustSec/rustsec) | Dependency vulnerability auditing |
| [cargo-deny](https://github.com/EmbarkStudios/cargo-deny) | Dependency policy and license checks |
| [cargo-geiger](https://github.com/geiger-rs/cargo-geiger) | Tracks unsafe Rust usage |
| [cargo-outdated](https://github.com/kbknapp/cargo-outdated) | Checks outdated dependencies |

## 📦 Cargo & Package Management

| Tool | Description |
|---|---|
| [Cargo](https://doc.rust-lang.org/cargo/) | Official Rust package manager |
| [crates.io](https://crates.io/) | Rust package registry |
| [cargo-edit](https://github.com/killercup/cargo-edit) | Cargo dependency management commands |
| [cargo-watch](https://github.com/watchexec/cargo-watch) | Automatically runs commands when files change |
| [cargo-make](https://github.com/sagiegurari/cargo-make) | Task runner for Rust projects |
| [cargo-binstall](https://github.com/cargo-bins/cargo-binstall) | Installs prebuilt Cargo binaries |
| [cargo-workspaces](https://github.com/pksunkara/cargo-workspaces) | Cargo workspace management |

## 🧪 Testing Tools

| Tool | Description |
|---|---|
| [cargo test](https://doc.rust-lang.org/cargo/commands/cargo-test.html) | Built-in Rust testing |
| [cargo-nextest](https://nexte.st/) | Next-generation Rust test runner |
| [proptest](https://github.com/proptest-rs/proptest) | Property-based testing |
| [quickcheck](https://github.com/BurntSushi/quickcheck) | Property-based testing |
| [rstest](https://github.com/la10736/rstest) | Fixture-based testing framework |
| [mockall](https://github.com/asomers/mockall) | Mock object framework |
| [cargo-tarpaulin](https://github.com/xd009642/tarpaulin) | Code coverage tool |

## 🚀 Performance & Profiling

| Tool | Description |
|---|---|
| [Criterion.rs](https://github.com/criterion-rs/criterion.rs) | Benchmarking framework |
| [cargo-flamegraph](https://github.com/flamegraph-rs/flamegraph) | Flamegraph profiling |
| [samply](https://github.com/mstange/samply) | Sampling profiler |
| [DHAT](https://github.com/nnethercote/dhat-rs) | Heap profiling |
| [Tracy](https://github.com/wolfpld/tracy) | Real-time profiling |
| [hyperfine](https://github.com/sharkdp/hyperfine) | Command-line benchmarking |

## 📚 Documentation Tools

| Tool | Description |
|---|---|
| [rustdoc](https://doc.rust-lang.org/rustdoc/) | Official Rust documentation generator |
| [docs.rs](https://docs.rs/) | Rust crate documentation hosting |
| [mdBook](https://github.com/rust-lang/mdBook) | Documentation book generator |
| [cargo-readme](https://github.com/livioribeiro/cargo-readme) | Generates README from Rust documentation |
| [cargo-deadlinks](https://github.com/deadlinks/cargo-deadlinks) | Checks links in documentation |

## 🤖 AI Coding Assistants

AI-powered tools that can help with Rust development.

| Tool | Description |
|---|---|
| [GitHub Copilot](https://github.com/features/copilot) | AI code completion and assistance |
| [Cursor](https://cursor.com/) | AI-powered code editor |
| [Windsurf](https://windsurf.com/) | AI-powered development environment |
| [Continue](https://www.continue.dev/) | Open-source AI coding assistant |
| [Aider](https://aider.chat/) | AI pair programming in the terminal |
| [Cline](https://github.com/cline/cline) | Autonomous coding agent extension |

## 🖥️ Terminal & Productivity

| Tool | Description |
|---|---|
| [Starship](https://starship.rs/) | Cross-shell prompt |
| [Zellij](https://zellij.dev/) | Terminal workspace manager |
| [tmux](https://github.com/tmux/tmux) | Terminal multiplexer |
| [bat](https://github.com/sharkdp/bat) | Improved cat command |
| [fd](https://github.com/sharkdp/fd) | Fast file finder |
| [ripgrep](https://github.com/BurntSushi/ripgrep) | Fast text search |
| [eza](https://github.com/eza-community/eza) | Modern ls alternative |
| [just](https://github.com/casey/just) | Command runner |

---

## 🚀 Getting Started

### 1. Install Rust

Install Rust using rustup:

```bash
# Windows / macOS / Linux
https://rustup.rs/
```

### 2. Verify Installation

```bash
rustc --version
cargo --version
rustup --version
```

### 3. Install Essential Components

```bash
rustup component add rustfmt
rustup component add clippy
rustup component add rust-src
```

### 4. Create a Rust Project

```bash
cargo new hello-rust
cd hello-rust
```

### 5. Run Your Project

```bash
cargo run
```

### 6. Format and Check Code

```bash
cargo fmt
cargo check
cargo clippy
cargo test
```

---

## ⭐ Recommended Rust Development Setup

For developers who want a practical starting configuration:

| Category | Recommended Tool |
|---|---|
| IDE | Visual Studio Code |
| Language Server | rust-analyzer |
| Debugger | CodeLLDB |
| Formatter | rustfmt |
| Linter | Clippy |
| Package Manager | Cargo |
| Testing | cargo-nextest |
| Benchmarking | Criterion.rs |
| Security Audit | cargo-audit |
| AI Assistant | GitHub Copilot / Continue |
| Documentation | rustdoc |

---
## ⭐ Editor Recommendations

Our recommended editors and development environments for Rust programming.

### 🥇 Best Overall — Visual Studio Code

**Recommended for:** Beginners, intermediate developers, and general Rust development.

- rust-analyzer integration
- CodeLLDB debugging
- Git and GitHub integration
- Extensive extension marketplace
- Lightweight and customizable

**Recommended extensions:**
- [rust-analyzer](https://marketplace.visualstudio.com/items?itemName=rust-lang.rust-analyzer)
- [CodeLLDB](https://marketplace.visualstudio.com/items?itemName=vadimcn.vscode-lldb)
- [Even Better TOML](https://marketplace.visualstudio.com/items?itemName=tamasfe.even-better-toml)
- [crates](https://marketplace.visualstudio.com/items?itemName=serayuzgur.crates)
- [Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens)

### 🥈 Best Dedicated Rust IDE — RustRover

**Recommended for:** Professional Rust developers and large-scale projects.

- Advanced Rust code intelligence
- Refactoring and navigation
- Integrated debugging
- Cargo and workspace support
- Intelligent inspections

Website: https://www.jetbrains.com/rust/

### 🥉 Best for Terminal Developers — Neovim

**Recommended for:** Experienced developers who prefer keyboard-driven workflows.

- Highly customizable
- Fast startup and performance
- LSP integration
- Powerful plugin ecosystem

**Recommended plugins:**
- [rustaceanvim](https://github.com/mrcjkb/rustaceanvim)
- [nvim-lspconfig](https://github.com/neovim/nvim-lspconfig)
- [crates.nvim](https://github.com/Saecki/crates.nvim)
- [nvim-dap](https://github.com/mfussenegger/nvim-dap)

### 🚀 Best Modern Editor — Zed

**Recommended for:** Developers looking for a modern, fast coding environment.

- Native Rust language support
- AI-assisted development features
- Fast editor experience
- Collaboration capabilities

Website: https://zed.dev/

### ⚡ Best Minimalist Editor — Helix

**Recommended for:** Developers who prefer a built-in modal editing experience.

- Built-in LSP support
- Multiple selections
- Tree-sitter integration
- Minimal plugin configuration

Website: https://helix-editor.com/

---

## 🏆 Quick Comparison

| Editor | Best For | Difficulty |
|---|---|---|
| VS Code | General development | Beginner |
| RustRover | Professional Rust projects | Beginner–Intermediate |
| Neovim | Custom workflows | Advanced |
| Zed | Modern development | Beginner–Intermediate |
| Helix | Minimalist workflows | Intermediate |
| Emacs | Highly customizable workflows | Advanced |

## 💡 Our Final Recommendation

| Developer Type | Recommended Setup |
|---|---|
| Rust Beginner | VS Code + rust-analyzer |
| Professional Developer | RustRover |
| Terminal Enthusiast | Neovim + rustaceanvim |
| Performance-Focused Developer | Zed |
| Minimalist Developer | Helix |
| AI-Assisted Developer | VS Code + Continue / GitHub Copilot |

**Essential Rust tools for every setup:**

`rust-analyzer` · `Cargo` · `rustfmt` · `Clippy` · `CodeLLDB`

> Recommendation principle: Choose an editor that fits your workflow. The Rust toolchain and rust-analyzer matter more than the editor itself.

## 🤝 Contributing

Contributions are welcome! Help make this repository a better resource for the Rust community.

You can contribute by:

- Adding useful Rust IDE extensions.
- Discovering new developer tools.
- Improving tool descriptions.
- Fixing broken links.
- Updating outdated information.
- Adding useful tutorials and resources.

### Contribution Guidelines

1. Fork this repository.
2. Create a new branch.
3. Add your recommended tool to the appropriate category.
4. Include the official project link and a short description.
5. Verify that the link works.
6. Submit a Pull Request.

Please read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting changes.

---

## 📌 Suggestions & Issues

Found an interesting Rust development tool?

- Open an [Issue](../../issues).
- Submit a [Pull Request](../../pulls).
- Suggest new IDE integrations or extensions.

---

## 📜 License

This repository is distributed under the MIT License.

See [LICENSE](LICENSE) for more information.

---

## ❤️ Support the Project

If you find this collection useful:

- ⭐ Star this repository.
- 🔀 Share it with other Rust developers.
- 🤝 Contribute new tools and resources.
- 📢 Help grow the Rust developer community.

**Built for Rust developers, by the developer community.**

🦀 Happy Rust coding!
