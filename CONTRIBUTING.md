# Contributing to Architecture Workflow

Thank you for your interest in contributing! This document provides guidelines for contributing to the architecture workflow system.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Architecture Documentation](#architecture-documentation)
- [Creating ADRs](#creating-adrs)
- [Working with Diagrams](#working-with-diagrams)
- [Pull Request Process](#pull-request-process)
- [Commit Message Guidelines](#commit-message-guidelines)

## Code of Conduct

### Our Standards

- Be respectful and inclusive
- Provide constructive feedback
- Focus on what is best for the community
- Show empathy towards others

## Getting Started

### Prerequisites

- Git
- GitHub account
- (Optional) PlantUML for diagram generation
- (Optional) Node.js and Mermaid CLI for diagram generation

### Setup

1. Fork the repository
2. Clone your fork:
   ```bash
   git clone https://github.com/YOUR_USERNAME/architecture-workflow.git
   cd architecture-workflow
   ```

3. Add upstream remote:
   ```bash
   git remote add upstream https://github.com/0xSoftBoi/architecture-workflow.git
   ```

4. Create a branch:
   ```bash
   git checkout -b feature/your-feature-name
   ```

## Architecture Documentation

### When to Create Documentation

Create architecture documentation when:
- Introducing a new component or subsystem
- Making significant changes to existing architecture
- Documenting blockchain-specific implementations
- Explaining complex interactions between components

### Documentation Standards

1. **Use templates**: Start with `.github/ARCHITECTURE_TEMPLATE.md`
2. **Be comprehensive**: Include all required sections
3. **Add diagrams**: Visual aids improve understanding
4. **Link related docs**: Reference ADRs and other documentation
5. **Keep it current**: Update docs with code changes

### File Organization

```
docs/
├── ARCHITECTURE.md          # Main architecture index
├── adr/                     # Architecture Decision Records
│   ├── README.md
│   └── NNNN-title.md
├── architecture/            # Detailed architecture docs
│   ├── blockchain/
│   └── commit-log/
└── diagrams/               # Technical diagrams
    ├── architecture/
    ├── blockchain/
    └── generated/
```

## Creating ADRs

### When to Create an ADR

Create an ADR for decisions that:
- Have significant impact on the system
- Are difficult or expensive to change
- Affect multiple components
- Involve trade-offs between alternatives
- Set precedents for future decisions

### ADR Creation Process

1. **Copy template**:
   ```bash
   cp .github/ADR_TEMPLATE.md docs/adr/NNNN-your-decision.md
   ```

2. **Fill in all sections**:
   - Context: Why this decision is needed
   - Options: What alternatives were considered
   - Decision: What was chosen and why
   - Consequences: What impacts will this have

3. **Add blockchain considerations**:
   - Gas costs
   - Immutability implications
   - Security concerns
   - Decentralization impact

4. **Create diagrams if needed**:
   - Add supporting diagrams to `diagrams/adr/`
   - Reference them in the ADR

5. **Submit for review**:
   ```bash
   git checkout -b architecture-docs
   git add docs/adr/NNNN-your-decision.md
   git commit -m "docs: Add ADR-NNNN for [decision title]"
   git push origin architecture-docs
   ```

### ADR Review Process

1. Submit PR to `architecture-docs` branch
2. Automated validation runs
3. Team reviews and discusses
4. Address feedback
5. Approval and merge
6. ADR status updated to "Accepted"

## Working with Diagrams

### Creating Diagrams

#### PlantUML Diagrams

1. Create `.plantuml` or `.puml` file:
   ```plantuml
   @startuml
   !theme blueprint
   
   title Your Diagram Title
   
   ' Your diagram content here
   
   @enduml
   ```

2. Place in appropriate directory:
   - `diagrams/architecture/` - System architecture
   - `diagrams/blockchain/` - Blockchain diagrams
   - `diagrams/contracts/` - Smart contract diagrams
   - `diagrams/flows/` - Process flows

3. Commit and push - diagrams generate automatically

#### Mermaid Diagrams

1. Create `.mermaid` file:
   ```mermaid
   graph TD
       A[Start] --> B[Process]
       B --> C[End]
   ```

2. Place in appropriate directory
3. Commit and push for auto-generation

### Diagram Standards

- **Consistent naming**: Use kebab-case
- **Clear titles**: Include title in every diagram
- **Appropriate complexity**: Split complex diagrams
- **Legends**: Add legends when needed
- **Colors**: Use consistent color scheme

### Local Diagram Generation

```bash
# Install tools
sudo apt-get install plantuml
npm install -g @mermaid-js/mermaid-cli

# Generate locally
plantuml -tsvg diagrams/**/*.plantuml -o generated/
mmdc -i diagrams/your-file.mermaid -o generated/your-file.svg
```

## Pull Request Process

### Before Submitting

1. **Update documentation** if needed
2. **Run validation locally** if possible
3. **Test diagram generation** if you added diagrams
4. **Review your changes** thoroughly
5. **Write clear commit messages**

### PR Guidelines

1. **Use descriptive title**: Clearly describe what the PR does
2. **Fill in description**: Explain the why and what
3. **Reference issues**: Link related issues
4. **Tag reviewers**: Request review from appropriate team members
5. **Keep it focused**: One PR per feature/fix

### PR Template

```markdown
## Description

Brief description of changes

## Type of Change

- [ ] Architecture documentation
- [ ] ADR creation/update
- [ ] Diagram addition/update
- [ ] Workflow improvement
- [ ] Bug fix

## Related Issues

Closes #123
Relates to #456

## Architecture Impact

- [ ] No architecture impact
- [ ] Minor architecture change
- [ ] Major architecture change (requires ADR)

## Checklist

- [ ] Documentation updated
- [ ] Diagrams added/updated
- [ ] ADR created if needed
- [ ] Commit messages follow guidelines
- [ ] All checks passing
```

### After Submission

1. Monitor automated checks
2. Respond to review comments
3. Make requested changes
4. Request re-review when ready
5. Celebrate when merged! 🎉

## Commit Message Guidelines

### Format

```
type(scope): subject

body (optional)

footer (optional)
```

### Types

- `feat`: New feature or architecture component
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Formatting, missing semicolons, etc.
- `refactor`: Code restructuring
- `test`: Adding tests
- `chore`: Maintenance tasks

### Examples

```bash
# Simple commit
git commit -m "docs: Add consensus mechanism architecture"

# With ADR reference
git commit -m "feat: implement new consensus (ADR-0001)

Implements the Byzantine Fault Tolerant consensus as decided
in ADR-0001. Includes validator selection and block production."

# With multiple references
git commit -m "docs: Update smart contract architecture (ADR-0002, ARCH-0015)

Updates documentation to reflect the new upgrade pattern
decided in ADR-0002 and implemented in ARCH-0015."
```

### ADR/Doc References

Use these prefixes in commit messages for automatic linking:

- `ADR-NNNN`: Architecture Decision Record
- `ARCH-NNNN`: Architecture document
- `DOC-NNNN`: General documentation issue

## Branch Strategy

### Main Branches

- `main`: Production-ready documentation
- `architecture-docs`: Architecture changes and ADRs
- `diagram-updates`: Diagram additions and updates
- `templates`: Template updates

### Feature Branches

Create from appropriate base branch:

```bash
# For ADRs and architecture docs
git checkout -b architecture-docs
git checkout -b feature/adr-consensus-mechanism

# For diagrams
git checkout -b diagram-updates
git checkout -b feature/add-network-diagram

# For workflows or templates
git checkout -b main
git checkout -b feature/improve-workflow
```

## Review Process

### For Reviewers

1. **Check completeness**: All sections filled
2. **Verify accuracy**: Technical details correct
3. **Assess clarity**: Understandable to newcomers
4. **Review diagrams**: Visuals match description
5. **Check links**: All references work
6. **Validate format**: Follows templates and guidelines

### Review Comments

Be constructive and specific:

✅ **Good**: "The consensus section should include Byzantine fault tolerance guarantees. See Tendermint docs for examples."

❌ **Bad**: "This is incomplete."

## Questions and Support

- **General questions**: Open a GitHub issue with label `question`
- **Architecture discussion**: Label issue with `architecture`
- **Bug reports**: Label issue with `bug`
- **Feature requests**: Label issue with `enhancement`

## Recognition

Contributors are recognized in:
- Commit history
- ADR authorship
- Documentation authorship
- Release notes

---

**Thank you for contributing!**

Your contributions help improve the architecture documentation workflow for everyone. Whether it's a typo fix, a new ADR, or a comprehensive architecture document, every contribution matters.

Questions? Open an issue or reach out to @0xSoftBoi