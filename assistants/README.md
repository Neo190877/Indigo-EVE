# Assistants Directory

This directory contains configuration templates for AI assistants deployed through the Indigo-EVE framework.

## Overview

The Indigo-EVE framework supports multiple AI assistant types, each optimized for specific use cases:

- **EVE (Operations)** - Operational voice assistant via Vapi
- **Ren (Brand)** - Brand voice assistant via ElevenLabs

## File Structure

```
assistants/
├── README.md                          # This file
├── vapi-ops-assistant.yaml           # Vapi configuration template for EVE (Ops)
├── vapi-ops-assistant.json           # JSON alternative for Vapi
├── elevenlabs-ren-assistant.yaml     # ElevenLabs configuration for Ren (Brand)
└── elevenlabs-ren-assistant.json     # JSON alternative for ElevenLabs
```

## Configuration Format

Both YAML and JSON formats are supported. Choose the format that best fits your deployment workflow.

### YAML Format
- Human-readable
- Supports comments
- Recommended for manual configuration

### JSON Format
- Machine-parseable
- Recommended for API integrations
- Better for automated deployments

## Usage

### 1. Clone for Client Project

When forking this framework for a client project:

```bash
# Copy template to client-specific config
cp vapi-ops-assistant.yaml ../client-project/vapi-ops-assistant.yaml
```

### 2. Replace Variables

Update all `{{CLIENT_NAME}}` variables with actual client name:

```bash
sed -i 's/{{CLIENT_NAME}}/AcmeCorp/g' vapi-ops-assistant.yaml
```

### 3. Configure API Keys

Add your API credentials to environment variables or secrets management:

```bash
export VAPI_API_KEY="your-vapi-key"
export ELEVENLABS_API_KEY="your-elevenlabs-key"
```

### 4. Deploy Assistant

Use the deployment scripts or CI/CD pipeline to deploy your configured assistant.

## Template Variables

All templates support the following variables:

- `{{CLIENT_NAME}}` - Client/project name
- `{{ASSISTANT_VERSION}}` - Version number
- `{{ENVIRONMENT}}` - Environment (dev/staging/prod)

## Customization Guidelines

### EVE (Operations Assistant)

**When to customize:**
- Changing operational workflows
- Adding new function capabilities
- Modifying call handling logic
- Integrating with client CRM systems

**Key configuration areas:**
- `conversation.first_message` - Opening greeting
- `functions` - Available tools/capabilities
- `integrations` - External system connections

### Ren (Brand Assistant)

**When to customize:**
- Adapting brand voice and tone
- Defining content generation rules
- Setting brand-specific guidelines
- Configuring content management integrations

**Key configuration areas:**
- `brand_voice` - Brand personality attributes
- `content.use_cases` - Supported content types
- `voice_settings` - Voice characteristics

## Integration with Other Directories

- **Prompts:** System instructions referenced via `prompt_file`
- **Knowledge:** Documentation and context via `knowledge_base`
- **Workflows:** Deployment automation via `.github/workflows`

## Best Practices

1. **Version Control:** Always version your configurations
2. **Environment Separation:** Use different configs for dev/staging/prod
3. **Secrets Management:** Never commit API keys to version control
4. **Testing:** Validate configurations before production deployment
5. **Documentation:** Document any client-specific customizations

## Support

For questions about assistant configuration, refer to:
- Main README.md for framework overview
- /prompts/README.md for prompt engineering guidance
- /knowledge/README.md for knowledge base structure
