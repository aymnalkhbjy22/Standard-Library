# ARCHITECT-Antivirus (v5.0)

A modular, lightweight, and defensive file scanner written entirely in Python using only the standard library. Designed for educational auditing, static inspection, heuristic triage, and structured reporting.

## Key Capabilities

- **Zero External Dependencies:** Runs natively out of the box on standard Python 3.8+ environments (including Termux/Linux).
- **Multi-Vector Static Analysis:**
  - **Cryptographic Hashing:** Computes SHA-256 using chunked streaming (memory-safe for large archives/payloads).
  - **Signature Matching:** Exact hash lookups against threat intelligence signatures.
  - **Heuristic Indicators:** Differentiates between known threats and suspicious indicators (flagged extensions, keyword heuristics).
- **Persistent Audit Logging:** Backed by SQLite to store scan histories, run metrics, error rates, and detection breakdowns.
- **Reporting Engine:** Automatic structured report generation in both JSON and CSV formats.

---

## Architecture & Directory Structure

```text
ARCHITECT-Antivirus/
├── main.py              # CLI Entry point & user menu
├── scanner.py           # Core scanning engine & hashing routines
├── database.py          # SQLite persistence schema & data access layer
├── reports.py           # JSON/CSV exporter
├── signatures.py        # Threat signatures & heuristic indicators
├── config.py            # Global paths, constants, and severity levels
├── requirements.txt     # Dependency definitions
├── README.md            # Documentation
├── data/                # SQLite storage (antivirus.db)
├── reports/             # Exported scan summaries (.json, .csv)
└── logs/                # Audit & operational runtime logs
