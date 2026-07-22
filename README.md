# Tracepoint Deployment Inspector

Tracepoint is a dependency-free static interface for evidence-based deployment artifact inspection. It keeps observed project facts, build-log claims, inference, conflicts, and unavailable deployment facts visibly separate, then produces a concise sanitized report in the required order.

## Run

Open `index.html` or serve this directory with any static file server. There is no build step, package manager, database, or backend. The directly deployable runtime files are `index.html`, `styles.css`, and `script.js`; this README is supporting documentation. That distinction resolves the supplied “four created artifacts” versus “three implementation files” discrepancy for the current project structure.

## What the static application implements

- Authorized-scope URL validation and credential-free, exact-target GET attempts
- Nine-stage inspection progress that continues when deployment verification is unavailable
- Artifact, project, deployment, comparison, evidence, conflicts, and limitation reporting
- Filterable evidence, searchable browser-local records, copy, text export, and re-run
- Explicit unknown/unavailable values and an initial evidence record based on the supplied build log
- Responsive keyboard-friendly UI with non-color status labels

## Security boundary

All persisted strings pass through redaction for secret-like values, authorization/cookie fields, personal contact data, internal addresses, and absolute internal paths. Sensitive URL query values are replaced. Only sanitized reports are retained in `localStorage` (maximum 50); raw response bodies, headers, credentials, cookies, project roots, and protected identifiers are never stored.

This static client cannot implement platform sign-in, tenant authorization, server-side project-reference resolution, unrestricted filesystem inspection, reliable redirect-chain capture, or full browser automation. Browser CORS may also prevent deployment verification. Those capabilities require approved platform services; the UI reports them as limitations and never simulates successful authentication or deployment verification.
