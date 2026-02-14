# Client Knowledge Templates

This directory contains templates and starter files for creating client-specific knowledge bases.

## Overview

When onboarding a new client, use these templates as starting points for building their custom knowledge base.

## Template Categories

### Operations Templates
Templates for operational procedures and workflows:
- Call handling procedures
- Appointment scheduling
- Customer service policies
- FAQ databases

### Brand Templates
Templates for brand guidelines and messaging:
- Brand voice guide
- Messaging framework
- Content style guide
- Brand values documentation

### Technical Templates
Templates for technical documentation:
- Integration checklists
- Configuration guides
- API documentation
- System requirements

## Usage

### 1. Create Client Directory
```bash
mkdir knowledge/{{CLIENT_NAME}}
cd knowledge/{{CLIENT_NAME}}
```

### 2. Copy Relevant Templates
```bash
# Copy all templates
cp -r ../client-templates/* .

# Or copy specific categories
cp -r ../client-templates/operations .
cp -r ../client-templates/brand .
```

### 3. Customize Templates
- Replace all `{{CLIENT_NAME}}` variables
- Fill in client-specific information
- Remove non-applicable sections
- Add additional content as needed

### 4. Update Assistant Configuration
```yaml
knowledge_base:
  - "../knowledge/operations"      # Shared operational knowledge
  - "../knowledge/brand"            # Shared brand knowledge  
  - "../knowledge/{{CLIENT_NAME}}"  # Client-specific knowledge
```

## Template Files

### Operations
- `operations-procedures-template.md`
- `faq-template.md`
- `escalation-matrix-template.md`
- `service-policies-template.md`

### Brand
- `brand-voice-template.md`
- `messaging-framework-template.md`
- `content-guidelines-template.md`
- `brand-values-template.md`

### Technical
- `integration-guide-template.md`
- `configuration-template.md`
- `api-reference-template.md`
- `troubleshooting-template.md`

## Customization Checklist

When creating client knowledge base:

- [ ] Create client directory structure
- [ ] Copy relevant templates
- [ ] Replace all variable placeholders
- [ ] Gather client-specific information
- [ ] Complete all template sections
- [ ] Review for accuracy
- [ ] Add client-specific documents
- [ ] Test with assistant configuration
- [ ] Get client approval
- [ ] Deploy to production

## Best Practices

1. **Start Minimal:** Begin with core templates, expand as needed
2. **Iterate:** Update based on assistant performance and feedback
3. **Version Control:** Track all changes to client knowledge
4. **Regular Reviews:** Schedule quarterly reviews with client
5. **Document Sources:** Note where information comes from
6. **Test Thoroughly:** Validate with real scenarios before launch

## Support

For questions about using templates or creating client knowledge bases, refer to:
- Main knowledge README: `/knowledge/README.md`
- Framework README: `/README.md`
- Template documentation within each file
