# Contributing to CosmicGATE-SOL

Thank you for contributing to CosmicGATE-SOL, the Solana blockchain integration for CosmicGATE.ai, written in Rust. We welcome improvements to smart contracts, scripts, or documentation.

## Table of Contents
- [Code of Conduct](#code-of-conduct)
- [How to Contribute](#how-to-contribute)
- [Setting Up the Development Environment](#setting-up-the-development-environment)
- [Coding Guidelines](#coding-guidelines)
- [Submitting Changes](#submitting-changes)
- [Testing](#testing)
- [Reporting Issues](#reporting-issues)
- [Security](#security)
- [License](#license)

## Code of Conduct
Please follow our [Code of Conduct](CODE_OF_CONDUCT.md) to maintain a respectful community.

## How to Contribute
1. Check or create issues in the [issue tracker](https://github.com/rajnishseasia/CosmicGATE-SOL/issues).
2. Fork the repository and create a feature branch.
3. Follow the setup and coding guidelines.
4. Submit a pull request with a clear description.

## Setting Up the Development Environment
### Prerequisites
- **Rust**: Version 1.60 or later. Install via `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`.
- **Solana CLI**: Install via `sh -c "$(curl -sSfL https://release.solana.com/stable/install)"`.
- **Anchor**: Install via `cargo install --git https://github.com/coral-xyz/anchor anchor-cli --locked`.
- **Git**: For version control.

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/rajnishseasia/CosmicGATE-SOL.git
   cd CosmicGATE-SOL
   ```
2. Install dependencies:
   ```bash
   cargo build
   ```
3. Configure Solana:
   - Set the RPC endpoint:
     ```bash
     solana config set --url https://api.devnet.solana.com
     ```
   - Use a Solana keypair or environment variables for credentials.
4. Build and run:
   ```bash
   anchor build
   anchor test
   ```

## Coding Guidelines
- **Code Style**: Follow Rust conventions using `cargo fmt`. Run `cargo fmt` to format code.
- **Linting**: Use `cargo clippy` for static analysis. Install with:
   ```bash
   rustup component add clippy
   ```
   Run: `cargo clippy -- -D warnings`.
- **Commits**: Follow [Conventional Commits](https://www.conventionalcommits.org/) (e.g., `feat: add token transfer program`).
- **Structure**: Place Solana programs in `/programs` and tests in `/tests`.
- **Dependencies**: Keep dependencies minimal and list them in `Cargo.toml`.

## Submitting Changes
1. Create a branch:
   ```bash
   git checkout -b feature/<your-feature-name>
   ```
2. Make and test changes (use Solana Devnet).
3. Commit changes:
   ```bash
   git commit -m "feat: add token transfer program"
   ```
4. Push and open a pull request:
   ```bash
   git push origin feature/<your-feature-name>
   ```

## Testing
- Test on Solana Devnet to avoid mainnet costs.
- Run tests: `anchor test`.
- Add unit and integration tests in `/tests` using Anchor’s testing framework.
- Ensure all tests pass before submitting.

## Reporting Issues
- Use the [issue tracker](https://github.com/rajnishseasia/CosmicGATE-SOL/issues) for bugs or feature requests.
- Include detailed steps and logs.

## Security
- Never commit Solana private keys or sensitive data.
- Use environment variables or Solana keypair files for credentials.
- Report vulnerabilities via [SECURITY.md](SECURITY.md).

## License
Contributions are licensed under the MIT License. See [LICENSE](LICENSE).