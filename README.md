# Day 10 - Container Security & Image Scanning

> Day 10 of 14 in the **Zero to Production Infrastructure & Security** series.

Pipeline stage that scans built images for CVEs with Trivy before deployment is permitted.

| | |
|---|---|
| **Day** | 10 of 14 |
| **Status** | Under construction |
| **Verification** | `docker build -t scan-selftest:ci .` |
| **Tags** | `docker`  `trivy`  `supply-chain`  `security`  `cicd` |

## Focus

- Supply chain security controls
- Image minimisation with Alpine and distroless bases
- Severity gating and build failure policy
- Remediation tracking

## Status

Implementation lands during the Day 10 build session. Until then this
repository holds the agreed structure only - there is no placeholder code here
pretending to work.

The nightly pipeline appends the real verification result to [STATUS.md](STATUS.md).

## Layout

```
10-container-image-scanning/
  README.md        this file
  LICENSE          MIT
  STATUS.md        machine-written verification record
  .gitignore       shared from the series root
  .gitattributes   forces LF endings so bash scripts run on Windows
```

## Verify

```bash
docker build -t scan-selftest:ci .
```

The nightly job at 22:00 runs this command, records the result and
exit code in STATUS.md, then tags and pushes the repository.

## Licence

MIT. See [LICENSE](LICENSE).