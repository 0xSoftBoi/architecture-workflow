# Architecture Decision Records (ADRs)

## What is an ADR?

An Architecture Decision Record (ADR) is a document that captures an important architectural decision made along with its context and consequences.

## Why ADRs?

ADRs help teams:
- **Remember** why decisions were made
- **Onboard** new team members effectively  
- **Avoid** revisiting settled discussions
- **Track** evolution of architectural thinking
- **Audit** decision-making process

## ADR Lifecycle

```
Proposed → Under Review → Accepted → Implemented
                              ↓
                         Deprecated
                              ↓
                        Superseded by ADR-XXXX
```

## Creating an ADR

1. **Copy the template**: Use `.github/ADR_TEMPLATE.md`
2. **Number it sequentially**: `NNNN-short-title.md` (e.g., `0001-consensus-mechanism.md`)
3. **Fill in all sections**: Don't skip the blockchain considerations
4. **Submit for review**: Create PR to `architecture-docs` branch
5. **Update status**: Change to "Accepted" after approval

## ADR Index

### Active ADRs

*No ADRs have been created yet. Create your first one using the template!*

### Deprecated ADRs

*None*

## Blockchain-Specific Sections

For blockchain projects, every ADR must address:

- **Gas Costs**: Impact on transaction costs
- **Immutability**: Upgradeability considerations
- **Decentralization**: Effect on network properties
- **Security**: Security implications and mitigations

## Template Usage

### Required Sections

✅ All sections in the template are required unless marked optional
✅ Include concrete examples and estimates
✅ Reference related ADRs and documentation
✅ Add diagrams to clarify complex decisions

### Optional Sections

- Additional notes
- Extended references
- Detailed meeting minutes

## Naming Convention

Format: `NNNN-short-kebab-case-title.md`

Examples:
- `0001-choose-consensus-mechanism.md`
- `0002-smart-contract-upgrade-pattern.md`
- `0003-layer-2-scaling-solution.md`

## Review Process

1. **Author** creates ADR and submits PR
2. **Automated validation** checks format and completeness
3. **Team review** discusses implications and alternatives
4. **Approval** requires sign-off from technical leads
5. **Merge** to main branch
6. **Implementation** begins with ADR reference in commits

## Tools

- **Template**: `.github/ADR_TEMPLATE.md`
- **Validation**: `.github/workflows/validate-architecture.yml`
- **Auto-linking**: `.github/workflows/link-commits-to-docs.yml`

## Best Practices

### DO ✅

- Create ADRs for significant decisions
- Include enough context for future readers
- Evaluate multiple alternatives
- Address blockchain-specific concerns
- Update status as situations change
- Reference ADRs in commit messages

### DON'T ❌

- Skip the template sections
- Make ADRs too granular (implementation details)
- Leave status ambiguous
- Forget to link related ADRs
- Ignore gas cost implications
- Create ADRs after implementation

## Examples of ADR Topics

### Blockchain Projects

- Consensus mechanism selection
- Smart contract upgrade patterns
- Token economics model
- Cross-chain bridge architecture
- Layer 2 scaling solution
- Oracle integration strategy
- Key management approach
- Multi-signature wallet implementation

### General Architecture

- Database technology selection
- API design approach
- Caching strategy
- Deployment architecture
- Monitoring and observability

## FAQ

**Q: When should I create an ADR?**
A: When a decision will have significant impact, is difficult to reverse, or affects multiple components.

**Q: How detailed should an ADR be?**
A: Detailed enough that someone unfamiliar with the project can understand the decision and its reasoning.

**Q: Can I update an ADR?**
A: Only to fix typos or clarify. For new decisions, create a new ADR that supersedes the old one.

**Q: What if we change our mind?**
A: Mark the ADR as "Deprecated" or "Superseded by ADR-XXXX" and create a new ADR.

**Q: Do all blockchain decisions need ADRs?**
A: Major architectural decisions yes, minor implementation details no.

## Resources

- [Architecture Decision Records](https://adr.github.io/)
- [Template Guide](.github/ADR_TEMPLATE.md)
- [Validation Workflow](.github/workflows/validate-architecture.yml)
- [Blockchain ADR Examples](https://github.com/ethereum/EIPs)

---

**Last Updated**: 2026-02-25
**Maintained by**: @0xSoftBoi