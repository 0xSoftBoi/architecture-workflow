# Architecture Documentation Index

> **Project**: Architecture Workflow System
> **Last Updated**: 2026-02-25
> **Maintainer**: @0xSoftBoi

This document serves as the central index for all architecture documentation, including blockchain architecture, architecture decision records (ADRs), and technical diagrams.

## 📋 Quick Links

- [Architecture Decision Records (ADRs)](adr/README.md)
- [Technical Diagrams](diagrams/INDEX.md)
- [Blockchain Architecture](architecture/blockchain/README.md)
- [Commit Log](architecture/commit-log/)

## 🏗️ Architecture Overview

### System Components

1. **Documentation Automation**
   - Automated commit linking to architecture changes
   - Auto-generated diagram compilation
   - Documentation validation workflows

2. **Blockchain Architecture**
   - Consensus mechanism documentation
   - Smart contract architecture
   - Network topology
   - Security architecture

3. **Technical Diagrams**
   - PlantUML support
   - Mermaid diagram support
   - Automated generation and indexing

## 📚 Architecture Decision Records

ADRs document significant architectural decisions made during the project. Use the [ADR template](.github/ADR_TEMPLATE.md) for new decisions.

### Active ADRs

*ADRs will be listed here as they are created*

### Creating a New ADR

1. Copy the ADR template: `.github/ADR_TEMPLATE.md`
2. Name it using the convention: `docs/adr/NNNN-short-title.md`
3. Fill in all required sections
4. Submit a PR to the `architecture-docs` branch
5. Tag reviewers for approval

## 🎨 Diagrams

### Diagram Types

- **PlantUML** (`.plantuml`, `.puml`): For UML diagrams, sequence diagrams, component diagrams
- **Mermaid** (`.mermaid`): For flowcharts, state diagrams, Gantt charts

### Creating Diagrams

1. Place diagram source files in appropriate directories:
   - `diagrams/architecture/` - System architecture diagrams
   - `diagrams/blockchain/` - Blockchain-specific diagrams
   - `diagrams/contracts/` - Smart contract diagrams
   - `diagrams/flows/` - Process flow diagrams

2. Diagrams are automatically generated on commit
3. Generated images are placed in `docs/diagrams/generated/`

### Diagram Standards

- Use clear, descriptive filenames
- Include a title in each diagram
- Add legends where necessary
- Reference diagrams in related documentation

## 🔗 Commit Linking System

### Automatic Documentation Updates

The repository includes automated workflows that:

1. **Detect architecture changes** in commits
2. **Create commit log entries** linking commits to documentation
3. **Update this index** with new commits
4. **Comment on PRs** with architecture change summaries

### Commit Message Conventions

To ensure proper linking, reference architecture elements in commit messages:

- `ADR-NNNN`: Link to Architecture Decision Record
- `ARCH-NNNN`: Link to general architecture document
- `DOC-NNNN`: Link to documentation issue

Example:
```
feat: implement new consensus mechanism (ADR-0001)

Implements the Byzantine Fault Tolerant consensus as decided
in ADR-0001.
```

## 🔐 Blockchain-Specific Documentation

### Required Sections for Blockchain Components

All blockchain architecture documents must include:

1. **Consensus Mechanism**
2. **Smart Contracts**
3. **Network Architecture**
4. **Security Model**
5. **Performance Characteristics**
6. **Deployment Strategy**

Use the [Architecture Template](.github/ARCHITECTURE_TEMPLATE.md) as a starting point.

## 🔄 Workflow Processes

### Architecture Documentation Workflow

1. **Proposal Phase**
   - Create issue describing architecture need
   - Draft ADR using template
   - Submit PR to `architecture-docs` branch

2. **Review Phase**
   - Team reviews ADR
   - Validation workflow checks format
   - Discussions and refinements

3. **Approval Phase**
   - ADR status updated to "Accepted"
   - Merged to main branch
   - Implementation work begins

4. **Implementation Phase**
   - Code changes reference ADR number
   - Automated linking tracks progress
   - Diagrams updated as needed

### Diagram Update Workflow

1. Create or update diagram source files (`.plantuml` or `.mermaid`)
2. Commit to `diagram-updates` branch
3. Automated workflow generates images
4. Review generated diagrams
5. Merge to main branch

## 📊 Architecture Metrics

### Documentation Coverage

- **Total ADRs**: 0
- **Active ADRs**: 0
- **Deprecated ADRs**: 0
- **Diagrams**: 0
- **Architecture Documents**: 0

*Metrics updated automatically by CI/CD*

## 🛠️ Tools and Setup

### Required Tools

- **PlantUML**: For UML diagram generation
- **Mermaid CLI**: For Mermaid diagram generation
- **GitHub Actions**: For automated workflows

### Local Development

```bash
# Install PlantUML
sudo apt-get install plantuml

# Install Mermaid CLI
npm install -g @mermaid-js/mermaid-cli

# Generate diagrams locally
plantuml -tsvg diagrams/**/*.plantuml
mmdc -i diagrams/**/*.mermaid
```

## 📖 Best Practices

### Documentation

1. **Keep it current**: Update docs with code changes
2. **Be specific**: Include concrete examples
3. **Link everything**: Reference related ADRs and documents
4. **Use diagrams**: Visual representations clarify complex systems

### Architecture Decisions

1. **Document context**: Explain why decision was needed
2. **Consider alternatives**: Show what options were evaluated
3. **Address blockchain implications**: Gas costs, immutability, security
4. **Plan for change**: Include migration and rollback strategies

### Diagrams

1. **Consistent style**: Use similar notation across diagrams
2. **Layer appropriately**: High-level and detailed views
3. **Update promptly**: Keep diagrams in sync with implementation
4. **Export multiple formats**: PNG for viewing, SVG for scaling

## 🤝 Contributing

See [CONTRIBUTING.md](../CONTRIBUTING.md) for detailed contribution guidelines.

### Quick Start for Contributors

1. Review existing ADRs and architecture docs
2. Create feature branch from `architecture-docs`
3. Use provided templates
4. Submit PR with clear description
5. Address review feedback

## 📅 Recent Architecture Changes

*This section is automatically updated by the commit linking workflow*

---

**Last Manual Update**: 2026-02-25  
**Auto-Updated**: Via GitHub Actions  
**Questions**: Create an issue or contact @0xSoftBoi