# Contributing to IQ:NS Ontologies

Thank you for your interest in contributing to IQ:NS! This document explains how to get involved.

## How to Contribute

### Reporting Issues

- Use [GitHub Issues](https://github.com/iqns-org/ontologies/issues) to report bugs or suggest improvements.
- Include a clear description and, where possible, a minimal example.

### Suggesting New Domains or Frameworks

- Open an issue with the label `enhancement` describing the domain, framework, or standard you'd like covered.
- Explain why it's relevant and link to authoritative sources.

### Submitting Changes

1. **Fork** the repository and create a feature branch from `main`.
2. Make your changes in a logically grouped commit.
3. Ensure all Turtle (`.ttl`) files are valid and follow the existing naming conventions.
4. Open a **Pull Request** against `main` with a clear description of what changed and why.

### Ontology Conventions

- Use Turtle (`.ttl`) as the primary serialisation format.
- Follow the existing directory layout: `v1/<domain>/vocabulary/`, `v1/<domain>/frameworks/`, etc.
- Prefix IRIs with the IQ:NS namespace unless referencing external vocabularies.
- Include `rdfs:label` and `rdfs:comment` for every new class and property.
- Align to existing SKOS concept schemes where cross-domain mappings apply.

### Commit Messages

Use clear, descriptive commit messages:

```
feat(ai): add ISO 42001 framework alignment
fix(finance): correct Basel III property range
docs(health): update HIPAA example queries
```

### Code of Conduct

All contributors are expected to follow our [Code of Conduct](CODE_OF_CONDUCT.md).

## License

By contributing, you agree that your contributions will be licensed under the [Apache License 2.0](LICENSE).
