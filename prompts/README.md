# Prompts Directory

This directory contains system instruction templates for Indigo-EVE AI assistants.

## Overview

System prompts define the personality, capabilities, and behavioral guidelines for each AI assistant. These templates use variable substitution to enable easy customization for different client deployments.

## File Structure

```
prompts/
├── README.md                       # This file
├── eve-ops-system-prompt.md       # EVE operational assistant prompt
├── ren-brand-system-prompt.md     # Ren brand assistant prompt
└── templates/                      # Additional prompt templates (optional)
```

## Prompt Engineering Principles

### 1. Clear Identity
Every prompt establishes:
- Who the assistant is
- What their role is
- Who they serve
- What platform they use

### 2. Mission and Capabilities
Define:
- Core mission statement
- Primary functions
- Operational boundaries
- Success criteria

### 3. Communication Guidelines
Specify:
- Voice and tone
- Language style
- Conversation structure
- Opening/closing scripts

### 4. Behavioral Rules
Establish:
- What to always do
- What to never do
- When to escalate
- How to handle edge cases

## Variable System

### Available Variables

All prompts support dynamic variable substitution:

| Variable | Description | Example |
|----------|-------------|---------|
| `{{CLIENT_NAME}}` | Client organization name | "Acme Corp" |
| `{{PRODUCT_NAME}}` | Product/service name | "CloudSync" |
| `{{DEPARTMENT}}` | Department name | "Sales" |
| `{{APPOINTMENT_TYPE}}` | Appointment category | "Consultation" |
| `{{TARGET_AUDIENCE}}` | Intended audience | "Enterprise clients" |
| `{{BRAND_VALUES}}` | Brand value list | "Innovation, Trust" |
| `{{TICKET_ID}}` | Reference number | "TKT-12345" |

### Using Variables

**In Configuration Files:**
```yaml
prompt_file: "../prompts/eve-ops-system-prompt.md"
variables:
  CLIENT_NAME: "Acme Corp"
  DEPARTMENT: "Customer Support"
```

**In Deployment Scripts:**
```bash
# Replace variables before deployment
sed -i 's/{{CLIENT_NAME}}/Acme Corp/g' eve-ops-system-prompt.md
```

**In Application Code:**
```javascript
const prompt = template
  .replace(/{{CLIENT_NAME}}/g, clientName)
  .replace(/{{PRODUCT_NAME}}/g, productName);
```

## Customizing Prompts

### For EVE (Operations)

**When to Customize:**
- Different industry vertical (healthcare, finance, retail)
- Specific operational workflows
- Unique compliance requirements
- Custom function integrations

**Key Sections to Modify:**
1. **Operational Capabilities** - Add/remove functions
2. **Communication Guidelines** - Adjust tone for industry
3. **Escalation Protocol** - Define client-specific rules
4. **Compliance** - Add industry regulations

**Example Customization:**
```markdown
## Healthcare Compliance (HIPAA)

### Additional Rules for {{CLIENT_NAME}}
- Never discuss patient information without verification
- Use secure channels for sensitive data
- Document all PHI access
- Follow HIPAA guidelines strictly
```

### For Ren (Brand)

**When to Customize:**
- Unique brand personality
- Industry-specific messaging
- Different content types
- Specialized audience segments

**Key Sections to Modify:**
1. **Brand Voice Principles** - Define brand personality
2. **Content Types** - Add specific deliverables
3. **Brand Guidelines** - Incorporate brand book rules
4. **Target Audiences** - Define audience segments

**Example Customization:**
```markdown
## {{CLIENT_NAME}} Brand Personality

### Voice Characteristics
- Playful yet professional
- Tech-savvy but accessible
- Bold and confident
- Community-focused

### Brand Lexicon
- Use: "innovate", "transform", "empower"
- Avoid: "leverage", "synergy", "disrupt"
```

## Prompt Structure Best Practices

### 1. Hierarchical Organization
```markdown
# Main Title
## Section
### Subsection
#### Detail
```

### 2. Clear Formatting
- Use bullet points for lists
- Use tables for structured data
- Use code blocks for examples
- Use blockquotes for important notes

### 3. Actionable Instructions
✓ **Good:** "Always verify caller identity before sharing account details"
✗ **Bad:** "Be careful with sensitive information"

### 4. Concrete Examples
Include specific examples of:
- Conversation flows
- Response templates
- Edge case handling
- Success scenarios

## Testing Prompts

### Validation Checklist

Before deploying a customized prompt:

- [ ] All variables are properly defined
- [ ] Instructions are clear and unambiguous
- [ ] Examples match client context
- [ ] Compliance requirements are included
- [ ] Escalation paths are defined
- [ ] Success criteria are measurable
- [ ] Tone matches brand personality
- [ ] Edge cases are addressed

### Testing Methods

1. **Unit Testing:** Test individual sections
2. **Integration Testing:** Test with assistant configuration
3. **User Testing:** Test with real scenarios
4. **A/B Testing:** Compare prompt variations
5. **Performance Testing:** Monitor success metrics

## Version Control

### Prompt Versioning

Track prompt changes systematically:

```markdown
---
version: 2.1.0
last_updated: 2026-02-14
changes:
  - Added healthcare compliance section
  - Updated escalation protocols
  - Refined brand voice guidelines
author: [Your Name]
client: {{CLIENT_NAME}}
---
```

### Change Log

Maintain a changelog for significant updates:
- Date of change
- What was changed
- Why it was changed
- Impact assessment
- Approval status

## Integration Points

### With Assistants
Prompts are referenced in assistant configs:
```yaml
prompt_file: "../prompts/eve-ops-system-prompt.md"
```

### With Knowledge Base
Prompts reference knowledge directories:
```markdown
You have access to {{CLIENT_NAME}} knowledge in:
- /knowledge/operations
- /knowledge/{{CLIENT_NAME}}
```

### With Workflows
CI/CD validates prompt syntax and variables:
```yaml
- name: Validate prompts
  run: python scripts/validate-prompts.py
```

## Common Pitfalls

### Avoid:
1. **Over-specification:** Too many rules can confuse the AI
2. **Contradictions:** Ensure instructions don't conflict
3. **Vague Language:** Be specific and concrete
4. **Missing Context:** Provide sufficient background
5. **Outdated Information:** Keep prompts current

### Best Practices:
1. **Iterate:** Start simple, add complexity as needed
2. **Test:** Validate with real-world scenarios
3. **Document:** Explain why instructions exist
4. **Simplify:** Remove unnecessary complexity
5. **Update:** Keep prompts aligned with client needs

## Performance Optimization

### Length Considerations
- Longer prompts = more context but higher costs
- Balance detail with token efficiency
- Use references to external knowledge when possible

### Clarity Optimization
- Use simple, direct language
- Break complex instructions into steps
- Provide examples for ambiguous cases
- Structure information hierarchically

### Response Quality
- Clear prompts = consistent responses
- Ambiguous prompts = unpredictable behavior
- Test prompts with edge cases
- Refine based on performance data

## Multi-Language Support

For international deployments:

```markdown
## Language: {{LANGUAGE_CODE}}

Communicate in {{LANGUAGE_NAME}} with:
- Native idioms and expressions
- Cultural awareness and sensitivity
- Localized examples and references
- Regional tone and formality levels
```

## Support and Resources

- **Main README:** Framework overview
- **Assistants README:** Configuration guidance
- **Knowledge README:** Content structure
- **Workflows:** Deployment automation

## Contributing

When creating new prompt templates:
1. Follow the established structure
2. Include comprehensive examples
3. Document all variables
4. Test thoroughly
5. Submit for review

---

**Remember:** Prompts are the foundation of AI behavior. Invest time in crafting clear, comprehensive, and context-aware instructions for the best results.
