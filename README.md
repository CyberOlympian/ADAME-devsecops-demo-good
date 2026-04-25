# Secure App - Advanced DevSecOps Pipeline

This repository demonstrates an advanced, artifact-driven DevSecOps pipeline using GitHub Actions.

## Security & Quality Gates
1. **Source Checks**: Semgrep (Secrets/Logic), Bandit (SAST), pip-audit (SCA).
2. **Testing**: Pytest unit tests.
3. **Container**: Docker build with Trivy (Vulnerability scanning) and Syft (SBOM generation).

## Artifact Readiness
Unlike basic pipelines that only pass/fail, this workflow generates auditable artifacts attached to every successful run:
- JSON reports for SAST and SCA.
- A CycloneDX Software Bill of Materials (SBOM) for the container.
- A `provenance.txt` file explicitly marking the container build as "Trusted" for downstream deployment.
