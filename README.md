# Volumez Common Public

This repository contains common OpenAPI (OAS) schemas and specifications used across the Volumez platform.

## Overview

This repository serves as the central location for shared OpenAPI schemas that define common data models, request/response structures, and API specifications used by multiple Volumez services.

## Purpose

The `common-public` repository contains:

- **Common OAS Schemas**: Shared OpenAPI specifications and data models
- **Reusable Components**: Common schema definitions used across multiple services
- **API Specifications**: Standardized request/response formats and data structures
- **Shared Types**: Common data models and interfaces for consistent API contracts

## Repository Structure

```
common-public/
├── schemas/          # OpenAPI schemas and data models
├── .gitignore       # Git ignore rules for public artifacts
└── README.md        # This file
```

## Key Features

### OpenAPI Schema Management
- **Centralized Schemas**: Single source of truth for common API definitions
- **Reusable Components**: Shared data models used across multiple services
- **Consistent API Contracts**: Standardized request/response formats
- **Version Control**: Managed evolution of API schemas and specifications

### Schema Components
- **Common Data Models**: Shared entity definitions and data structures
- **Standard Response Formats**: Consistent error handling and response patterns
- **Authentication Schemas**: Common auth-related data models
- **Validation Rules**: Shared input validation and constraints

## Usage

This repository is primarily consumed by:

1. **Volumez Services**: Microservices importing common schema definitions
2. **API Client Generation**: Tools generating client SDKs from shared schemas
3. **Documentation Tools**: Systems generating API documentation
4. **Integration Testing**: Validation of API contracts across services

## Schema Usage Examples

### Referencing Common Schemas
```yaml
# In a service's OpenAPI spec
components:
  schemas:
    UserResponse:
      allOf:
        - $ref: 'https://github.com/volumez/common-public/schemas/common.yaml#/components/schemas/BaseResponse'
        - type: object
          properties:
            data:
              $ref: '#/components/schemas/User'
```

### API Client Generation
```bash
# Generate client using common schemas
openapi-generator generate -i schemas/common.yaml -g go -o ./client
```

## Schema Development

### Adding New Common Schemas
1. Create or update schema files in the `schemas/` directory
2. Follow OpenAPI 3.0+ specification standards
3. Use consistent naming conventions and data types
4. Include comprehensive descriptions and examples
5. Version schemas appropriately when making breaking changes

### Best Practices
- Keep schemas focused and reusable
- Use clear, descriptive names for components
- Include validation constraints where appropriate
- Document schema purpose and usage
- Maintain backward compatibility when possible

## Support

For questions about schema usage or contributions:

- **Schema Documentation**: See individual YAML files in `/schemas`
- **Integration Guidelines**: Follow OpenAPI best practices
- **Development Team**: Contact the platform architecture team

---

**Note**: This repository contains common OpenAPI schemas shared across Volumez services. For service-specific APIs, refer to individual service repositories.
