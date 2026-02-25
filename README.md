# Architecture Workflow

> Automated blockchain architecture documentation with commit linking and technical diagram generation

[![Architecture Validation](https://github.com/0xSoftBoi/architecture-workflow/actions/workflows/validate-architecture.yml/badge.svg)](https://github.com/0xSoftBoi/architecture-workflow/actions/workflows/validate-architecture.yml)
[![Generate Diagrams](https://github.com/0xSoftBoi/architecture-workflow/actions/workflows/generate-diagrams.yml/badge.svg)](https://github.com/0xSoftBoi/architecture-workflow/actions/workflows/generate-diagrams.yml)
[![Link Commits](https://github.com/0xSoftBoi/architecture-workflow/actions/workflows/link-commits-to-docs.yml/badge.svg)](https://github.com/0xSoftBoi/architecture-workflow/actions/workflows/link-commits-to-docs.yml)

## Overview

A comprehensive system for managing blockchain architecture documentation with automated workflows for:

✅ **Automated commit linking** to architecture changes  
✅ **Technical diagram generation** from PlantUML and Mermaid  
✅ **Architecture Decision Records (ADRs)** with validation  
✅ **Blockchain-specific documentation** templates  
✅ **CI/CD integration** for documentation workflows  

## Features

### 🔗 Automated Commit Linking

- Automatically detects architecture-related commits
- Creates commit log entries linked to documentation
- Updates architecture index with changes
- Comments on PRs with architecture change summaries

### 🎨 Technical Diagram Generation

- **PlantUML support** for UML, sequence, and component diagrams
- **Mermaid support** for flowcharts and state diagrams
- Automatic generation on commit
- Multiple export formats (PNG, SVG)
- Diagram index generation

### 📝 Architecture Decision Records

- Standardized ADR template
- Blockchain-specific considerations
- Automated format validation
- Decision tracking and history

### 🏗️ Blockchain Architecture Documentation

- Comprehensive architecture templates
- Consensus mechanism documentation
- Smart contract architecture
- Network topology and security
- Performance and scalability considerations

## Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/0xSoftBoi/architecture-workflow.git
cd architecture-workflow
```

### 2. Explore the Documentation

- **Architecture Index**: [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md)
- **ADR Guide**: [docs/adr/README.md](docs/adr/README.md)
- **Diagram Guide**: [docs/diagrams/README.md](docs/diagrams/README.md)
- **Contributing Guide**: [CONTRIBUTING.md](CONTRIBUTING.md)

### 3. Create Your First ADR

```bash
# Copy the template
cp .github/ADR_TEMPLATE.md docs/adr/0001-your-first-decision.md

# Edit the ADR with your decision
vim docs/adr/0001-your-first-decision.md

# Commit and push
git checkout -b architecture-docs
git add docs/adr/0001-your-first-decision.md
git commit -m "docs: Add ADR-0001 for [your decision]"
git push origin architecture-docs
```

### 4. Create Diagrams

```bash
# Create a PlantUML diagram
cat > diagrams/architecture/system-overview.plantuml << 'EOF'
@startuml
!theme blueprint
title System Architecture

[Component A] --> [Component B]
[Component B] --> [Component C]

@enduml
EOF

# Commit - diagrams generate automatically
git add diagrams/architecture/system-overview.plantuml
git commit -m "docs: Add system architecture diagram"
git push
```

## Repository Structure

```
architecture-workflow/
├── .github/
│   ├── workflows/
│   │   ├── link-commits-to-docs.yml     # Commit linking workflow
│   │   ├── generate-diagrams.yml         # Diagram generation
│   │   └── validate-architecture.yml     # Documentation validation
│   ├── ARCHITECTURE_TEMPLATE.md          # Architecture doc template
│   └── ADR_TEMPLATE.md                   # ADR template
├── docs/
│   ├── ARCHITECTURE.md                   # Main architecture index
│   ├── adr/                             # Architecture Decision Records
│   │   ├── README.md
│   │   └── NNNN-decision-title.md
│   ├── architecture/                    # Detailed architecture docs
│   │   ├── blockchain/
│   │   │   └── README.md
│   │   └── commit-log/                 # Auto-generated commit logs
│   └── diagrams/                       # Technical diagrams
│       ├── architecture/
│       ├── blockchain/
│       ├── contracts/
│       ├── flows/
│       ├── generated/                  # Auto-generated images
│       ├── INDEX.md                    # Auto-generated diagram index
│       └── README.md
├── CONTRIBUTING.md                      # Contribution guidelines
└── README.md                           # This file
```

## Workflows

### 1. Link Commits to Documentation

**Trigger**: Push to main, architecture-docs, or diagram-updates branches

**Actions**:
- Extracts commit information
- Detects architecture-related changes
- Creates commit log entries
- Updates documentation index
- Comments on PRs with summaries

### 2. Generate Technical Diagrams

**Trigger**: Changes to `.plantuml`, `.puml`, or `.mermaid` files

**Actions**:
- Installs diagram generation tools
- Generates PNG and SVG from source files
- Creates diagram index
- Commits generated files
- Uploads artifacts

### 3. Validate Architecture Documentation

**Trigger**: PRs affecting architecture documentation

**Actions**:
- Validates ADR format and naming
- Checks blockchain architecture sections
- Verifies diagram references
- Validates diagram syntax
- Comments validation results

## Branches

### Main Branches

- **main**: Production-ready documentation
- **architecture-docs**: For architecture changes and ADRs
- **diagram-updates**: For diagram additions and updates
- **templates**: For template updates

### Branch Workflow

1. Create feature branch from appropriate base
2. Make changes
3. Submit PR to base branch
4. Automated workflows run
5. Review and merge

## Templates

### Architecture Documentation Template

Comprehensive template for blockchain architecture docs:
- [.github/ARCHITECTURE_TEMPLATE.md](.github/ARCHITECTURE_TEMPLATE.md)

**Sections include**:
- Overview and ADR references
- Blockchain architecture (consensus, contracts, network)
- Security and performance
- Integration and deployment
- Monitoring and testing

### ADR Template

Standardized template for Architecture Decision Records:
- [.github/ADR_TEMPLATE.md](.github/ADR_TEMPLATE.md)

**Sections include**:
- Context and problem statement
- Options considered with pros/cons
- Decision rationale
- Consequences and validation
- Blockchain-specific considerations

## Commit Message Conventions

Use these conventions for automatic linking:

```bash
# Reference an ADR
git commit -m "feat: implement consensus mechanism (ADR-0001)"

# Reference architecture document
git commit -m "docs: update network topology (ARCH-0015)"

# Multiple references
git commit -m "refactor: optimize contract (ADR-0002, ADR-0003)"
```

**Prefixes**:
- `ADR-NNNN`: Architecture Decision Record
- `ARCH-NNNN`: Architecture document
- `DOC-NNNN`: Documentation issue

## Tools

### Required (CI/CD)

- GitHub Actions
- PlantUML
- Mermaid CLI
- Node.js

### Optional (Local Development)

```bash
# Install PlantUML
sudo apt-get install plantuml
# or
brew install plantuml

# Install Mermaid CLI
npm install -g @mermaid-js/mermaid-cli

# Generate diagrams locally
plantuml -tsvg diagrams/**/*.plantuml
mmdc -i diagram.mermaid -o diagram.svg
```

### IDE Plugins

**VS Code**:
- PlantUML (jebbs.plantuml)
- Mermaid (bierner.markdown-mermaid)

**JetBrains**:
- PlantUML Integration
- Mermaid plugin

## Best Practices

### Documentation

✅ Keep documentation in sync with code  
✅ Use templates for consistency  
✅ Include diagrams for complex systems  
✅ Reference ADRs in commit messages  
✅ Update architecture index regularly  

### ADRs

✅ Create ADRs for significant decisions  
✅ Evaluate multiple alternatives  
✅ Address blockchain implications  
✅ Include security considerations  
✅ Plan for change and migration  

### Diagrams

✅ Use consistent styling  
✅ Keep diagrams simple and focused  
✅ Generate multiple formats  
✅ Update with architecture changes  
✅ Reference in documentation  

## Examples

### Example ADR

See [ADR template](.github/ADR_TEMPLATE.md) for a complete example.

### Example Architecture Document

See [Architecture template](.github/ARCHITECTURE_TEMPLATE.md) for a complete example.

### Example Diagrams

Check [docs/diagrams/README.md](docs/diagrams/README.md) for diagram examples.

## Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

**Quick contribution steps**:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request
5. Respond to review feedback

## Support

- 📖 **Documentation**: Check [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md)
- 🐛 **Issues**: [Open an issue](https://github.com/0xSoftBoi/architecture-workflow/issues)
- 💬 **Discussions**: Use GitHub Discussions
- 📧 **Contact**: @0xSoftBoi

## License

This project is open source. Feel free to use, modify, and distribute.

## Roadmap

### Current Features

- ✅ Automated commit linking
- ✅ Diagram generation (PlantUML, Mermaid)
- ✅ ADR templates and validation
- ✅ Blockchain architecture templates
- ✅ CI/CD workflows

### Planned Features

- 🔜 Architecture metrics dashboard
- 🔜 Automated ADR status tracking
- 🔜 Diagram versioning and diff
- 🔜 Integration with project management tools
- 🔜 Architecture change impact analysis

## Acknowledgments

Built with:
- GitHub Actions for CI/CD
- PlantUML for diagram generation
- Mermaid for diagram generation
- Markdown for documentation

Inspired by:
- [Architecture Decision Records](https://adr.github.io/)
- [C4 Model](https://c4model.com/)
- Blockchain architecture best practices

---

**Maintained by**: [@0xSoftBoi](https://github.com/0xSoftBoi)  
**Last Updated**: 2026-02-25  
**Status**: Active Development  

🌟 Star this repo if you find it useful!