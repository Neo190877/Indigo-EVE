# Indigo-EVE Framework

**The master framework for Indigo's Generative Media AI (GMAi) and operational voice agents.**

Orchestrating high-fidelity EVE and Ren units via Vapi and ElevenLabs to deliver exceptional AI-powered experiences.

[![Validate Configs](https://github.com/Neo190877/Indigo-EVE/actions/workflows/validate-configs.yml/badge.svg)](https://github.com/Neo190877/Indigo-EVE/actions/workflows/validate-configs.yml)
[![Deploy Assistants](https://github.com/Neo190877/Indigo-EVE/actions/workflows/deploy-assistants.yml/badge.svg)](https://github.com/Neo190877/Indigo-EVE/actions/workflows/deploy-assistants.yml)

---

## 📋 Table of Contents

- [Overview](#overview)
- [GMAi Standards](#gmai-standards)
- [Framework Architecture](#framework-architecture)
- [Quick Start](#quick-start)
- [Directory Structure](#directory-structure)
- [Assistant Types](#assistant-types)
- [Configuration Guide](#configuration-guide)
- [Deployment](#deployment)
- [Forking for Client Projects](#forking-for-client-projects)
- [Development Workflow](#development-workflow)
- [Best Practices](#best-practices)
- [Support](#support)

---

## Overview

Indigo-EVE is a production-ready framework for deploying and managing AI voice assistants powered by cutting-edge generative AI technologies. This master framework serves as a template for creating client-specific AI deployments with consistent quality, security, and maintainability.

### Key Features

✨ **Modular Architecture** - Cleanly separated concerns for easy customization  
🤖 **Multi-Platform Support** - Vapi (operations) and ElevenLabs (brand voice)  
📝 **Template-Based Configuration** - Reusable configs with variable substitution  
🔒 **Security-First** - Built-in compliance and privacy guidelines  
🚀 **CI/CD Ready** - Automated validation and deployment workflows  
📚 **Comprehensive Documentation** - Extensive guides and examples  
🎯 **Production-Ready** - Battle-tested patterns and best practices

---

## GMAi Standards

Indigo's Generative Media AI (GMAi) standards ensure consistent, high-quality AI deployments across all client projects.

### Core Principles

#### 1. Quality & Consistency
- **Standardized Frameworks:** Use Indigo-EVE as the foundation for all deployments
- **Configuration Management:** All settings managed through version-controlled configs
- **Template System:** Consistent structure across all client implementations
- **Documentation Requirements:** Every deployment fully documented

#### 2. Security & Compliance
- **Privacy by Design:** PII and sensitive data handling built into prompts
- **Access Control:** Role-based permissions for all configurations
- **Audit Trails:** All changes tracked in version control
- **Compliance Ready:** GDPR, HIPAA, SOC 2 guidelines integrated

#### 3. Scalability & Performance
- **Modular Design:** Components can be deployed independently
- **Resource Optimization:** Efficient prompt engineering and token usage
- **Load Management:** Designed for high-volume operations
- **Monitoring:** Performance metrics and quality tracking

#### 4. Maintainability
- **Clear Separation:** Assistants, prompts, and knowledge clearly separated
- **Version Control:** All artifacts versioned and tracked
- **Update Procedures:** Structured process for updates and improvements
- **Rollback Capability:** Safe deployment with rollback options

### Assistant Standards

#### EVE (Enhanced Voice Entity) - Operations
**Purpose:** Handle operational tasks with efficiency and professionalism

**Standards:**
- Clear, professional communication
- Consistent call handling procedures
- Defined escalation protocols
- Comprehensive documentation
- Privacy and security compliance
- Performance metrics tracking

**Platform:** Vapi Voice AI

#### Ren (Renaissance Entity) - Brand
**Purpose:** Create compelling, on-brand content and communications

**Standards:**
- Brand voice consistency
- Content quality assurance
- Multi-channel adaptability
- Creative while maintaining guidelines
- Measurable content performance
- Brand reputation protection

**Platform:** ElevenLabs Voice AI

### Configuration Standards

All Indigo-EVE deployments must include:

1. **Assistant Configuration** (YAML/JSON)
   - Metadata (name, version, type, description)
   - Platform-specific settings
   - Integration configurations
   - References to prompts and knowledge

2. **System Prompts** (Markdown)
   - Clear identity and mission
   - Comprehensive capabilities definition
   - Communication guidelines
   - Behavioral rules and boundaries
   - Integration with knowledge base

3. **Knowledge Base** (Organized directories)
   - Operational procedures
   - Brand guidelines
   - Technical documentation
   - Client-specific information

4. **CI/CD Workflows** (GitHub Actions)
   - Configuration validation
   - Automated testing
   - Deployment automation
   - Quality gates

---

## Framework Architecture

```
Indigo-EVE/
├── assistants/              # AI assistant configurations
│   ├── vapi-ops-assistant.{yaml,json}
│   ├── elevenlabs-ren-assistant.{yaml,json}
│   └── README.md
├── prompts/                 # System instruction templates
│   ├── eve-ops-system-prompt.md
│   ├── ren-brand-system-prompt.md
│   └── README.md
├── knowledge/               # Knowledge base and documentation
│   ├── operations/
│   ├── brand/
│   ├── technical/
│   ├── client-templates/
│   └── README.md
├── .github/
│   └── workflows/          # CI/CD automation
│       ├── validate-configs.yml
│       └── deploy-assistants.yml
└── README.md               # This file
```

### Component Relationships

```
┌─────────────────┐
│   Assistant     │
│  Configuration  │◄─── References
└────────┬────────┘
         │
         ├──────► System Prompt ◄─── Defines behavior
         │
         └──────► Knowledge Base ◄─── Provides context
```

---

## Quick Start

### Prerequisites

- Git
- Python 3.11+ (for validation scripts)
- GitHub account
- Vapi account (for EVE operations)
- ElevenLabs account (for Ren brand voice)

### Installation

```bash
# Clone the repository
git clone https://github.com/Neo190877/Indigo-EVE.git
cd Indigo-EVE

# Install Python dependencies for validation
pip install pyyaml jsonschema
```

### Quick Test

```bash
# Check directory structure
ls -R assistants/ prompts/ knowledge/

# View assistant configurations
cat assistants/vapi-ops-assistant.yaml

# View system prompts
cat prompts/eve-ops-system-prompt.md
```

---

## Directory Structure

### `/assistants` - AI Assistant Configurations

Contains configuration templates for AI assistants. Both YAML and JSON formats provided for flexibility.

### `/prompts` - System Instructions

Contains system instruction templates that define assistant personality and behavior.

### `/knowledge` - Knowledge Base

Organized documentation and reference materials for AI assistants.

### `.github/workflows` - CI/CD Automation

GitHub Actions workflows for validation and deployment.

---

## Forking for Client Projects

The Indigo-EVE framework is designed to be forked for each client project.

### Fork Process

1. Fork the repository on GitHub
2. Customize for client with `sed` commands
3. Create client knowledge base
4. Configure integrations
5. Set up secrets
6. Validate and deploy

See full documentation in the main README sections above.

---

## License

Copyright © 2026 Indigo AI. All rights reserved.

---

**Indigo-EVE Framework** - Empowering exceptional AI experiences, one voice at a time. 🚀
