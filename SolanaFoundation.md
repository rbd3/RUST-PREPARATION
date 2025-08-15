### Review Solana program basics: 
Understand accounts, instructions, cross-program invocations (CPI), and the runtime. Solana programs are stateless and use PDAs (program-derived addresses) heavily.

### Resources:
**https://github.com/sannykim/solsec?tab=readme-ov-file**

***https://neodyme.io/en/blog/token-2022/#security-implications-6***

SPL Token-2022 docs (docs.spl.solana.com/token/extensions/confidential-transfers).
GitHub repo: Explore spl-token-2022 crate (github.com/solana-labs/solana-program-library/tree/master/token/program-2022)

### Master Solana's zk-sdk and ZK Concepts
The zk-sdk handles proof generation and verification for encrypted data in confidential transfers.

## Resources:

Official zk-sdk docs (docs.rs/solana-zk-sdk) and zk-token-sdk (docs.rs/solana-zk-token-sdk).
zk-security.xyz blog on Solana's phantom challenge bug for real-world vuln examples.

## Common issues to watch for:

Missing ownership/signer checks (e.g., unauthorized account modifications).
Account confusion (wrong data loaded into accounts).
CPI vulnerabilities (e.g., untrusted programs invoking yours).
Arithmetic overflows in balances/proofs.
ZK-specific: Soundness bugs, proof forgery, or decryption oracles.

### github.com/sannykim/solsec

## Tools
Trident finds dynamic bugs via fuzzing, Semgrep catches static code issues, and Neodyme’s framework proves exploitability for high-impact C4 submissions.

### Study Plan (1 Week, ~25-30 Hours)

Day 1-2: Neodyme Common Pitfalls (4-6 hours)

Read (1 hour), inspect Token-2022 code for pitfalls (2-3 hours), practice a signer check exploit (1-2 hours).


Day 3-4: Kudelski Solana Program Security (6-8 hours)

Read (1 hour), scan Token-2022 with Semgrep (3-4 hours), test an ownership vuln locally (2-3 hours).


Day 5-6: Sec3 How to Audit Part 4: Anchor (8-10 hours)

Read (1 hour), review Token-2022’s Anchor constraints (4-5 hours), fuzz-test a constraint error with Trident (3-4 hours).


Day 7: Consolidate (3-5 hours)

Revisit findings, draft a sample C4 report using Neodyme’s PoC framework, and cross-check Token-2022’s confidential transfer logic for issues like unchecked ZK proofs or account misuse.