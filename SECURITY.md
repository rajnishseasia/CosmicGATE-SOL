# Security Policy

## Supported Versions
The `CosmicGATE-SOL` project currently supports the latest version of the repository (main branch) for security updates. We recommend using the latest release to ensure you have the most recent security patches.

| Version | Supported          |
|---------|--------------------|
| main    | :white_check_mark: |
| Older   | :x:                |

## Reporting a Vulnerability
We take the security of CosmicGATE-SOL seriously. If you discover a security vulnerability, please report it responsibly by following these steps:

1. **Do Not Report Publicly**: Avoid disclosing the issue in public forums, such as GitHub issues, until it has been addressed to prevent exploitation.
2. **Contact Us Privately**:
   - Email the maintainers at [security@cosmicgate.ai](mailto:security@cosmicgate.ai) with a detailed description of the vulnerability.
   - Include steps to reproduce, potential impact, and any suggested fixes.
   - If possible, use encrypted communication (e.g., PGP key available upon request).
3. **Expected Response**:
   - You will receive an acknowledgment within 48 hours.
   - We aim to resolve critical vulnerabilities within 14 days and will keep you updated on progress.
4. **Disclosure Process**:
   - Once the issue is resolved, we may coordinate with you for responsible disclosure, including credit in release notes (if desired).
   - Public disclosure will occur only after a fix is deployed, unless otherwise agreed.

## Access Control
To ensure the security and integrity of the CosmicGATE-SOL repository, access is tightly controlled:
- **Repository Permissions**:
  - Only authorized maintainers have write access to the `main` branch.
  - External contributors must submit changes via pull requests (PRs) to a feature branch.
  - GitHub branch protection rules are enabled for the `main` branch, requiring at least one maintainer review and passing CI checks before merging.
- **Solana Deployment Access**:
  - Deployment of Solana programs (e.g., to Devnet or Mainnet) is restricted to maintainers with access to Solana keypairs or deployment tools.
  - Credentials are stored securely in environment variables or Solana keypair files, not in the repository.
- **Configuring Access**:
  - To request access (e.g., collaborator status), contact the maintainers via the [issue tracker](https://github.com/rajnishseasia/CosmicGATE-SOL/issues) with your GitHub username and justification.
  - Maintainers will review and grant access based on project needs.

## Pull Request (PR) Security
To maintain code quality and security, all contributions must follow a secure PR process:
- **Submission**: Submit PRs from a forked repository or a feature branch (e.g., `feature/<your-feature-name>`).
- **Review Process**:
  - PRs require at least one approval from a maintainer.
  - Automated checks (e.g., `cargo clippy`, `anchor test`) must pass via GitHub Actions.
  - Sensitive data (e.g., Solana keypairs) is scanned using GitHub’s secret scanning feature.
- **Branch Protection**:
  - The `main` branch is protected to prevent direct pushes.
  - PRs must be up-to-date with `main` before merging.
- See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed PR submission guidelines.

## Deployment Security
Deployments for CosmicGATE-SOL involve deploying Solana programs to the Solana blockchain, managed securely to prevent unauthorized access or data exposure:
- **Solana Deployment**:
  - Only maintainers with access to Solana keypairs or deployment tools can deploy programs.
  - Use Solana Devnet for testing deployments to avoid mainnet costs.
  - Store credentials in environment variables or secure keypair files, not in the repository.
- **Deployment Process**:
  - Build and deploy programs using:
    ```bash
    anchor build
    anchor deploy
    ```
  - Deployments are triggered after PR approval and passing tests (`anchor test`).
  - Ensure all tests pass before deployment to avoid runtime errors on the blockchain.
- **Security Checks**:
  - Run `cargo audit` to check for vulnerabilities in Rust dependencies.
  - Verify program integrity before deployment using Solana CLI tools (e.g., `solana program show`).
- Report deployment issues via the [issue tracker](https://github.com/rajnishseasia/CosmicGATE-SOL/issues).

## Security Guidelines
- **Sensitive Data**: Never commit Solana private keys, keypairs, or sensitive data to the repository. Use environment variables or Solana keypair files.
- **Dependencies**: Ensure all Rust dependencies in `Cargo.toml` are up-to-date. Use `cargo update` and check for vulnerabilities with `cargo audit`.
- **Code Review**: All contributions are subject to review to ensure no security issues are introduced.
- **Anchor Programs**: Follow Anchor’s security best practices for Solana program development (e.g., validate inputs, use safe math).

## Reporting Issues
For non-security-related issues, please use the [issue tracker](https://github.com/rajnishseasia/CosmicGATE-SOL/issues).

## Contact
For security concerns, reach out via [security@cosmicgate.ai](mailto:security@cosmicgate.ai). For other inquiries, use the [issue tracker](https://github.com/rajnishseasia/CosmicGATE-SOL/issues).

Thank you for helping keep CosmicGATE-SOL secure!