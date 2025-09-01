# Contributing to SIMOVI Projects

Welcome to the **Intelligent Mobility Systems Lab** (SIMOVI) at the University of Costa Rica! We appreciate your interest in contributing to our open-source public transportation research projects.

> [!IMPORTANT]
> **Research Context**: Our projects focus on intelligent mobility systems, public transportation data analysis, and GTFS-based solutions. All contributions should align with our mission of improving transit accessibility and operational efficiency through digital technologies.

## Code of Conduct

By participating in this project, you agree to abide by our research ethics and maintain professional standards in all interactions. We foster an inclusive environment that welcomes contributors from the global transportation and software development communities.

## Getting Started

### Prerequisites

Before contributing, please:

1. 🗺️ Review the [SIMOVI Roadmap](https://github.com/simovilab/context/blob/main/roadmap.md)
1. 📚 Read our [System Design Principles](https://github.com/simovilab/context/blob/main/system_design_principles.md)
1. 📚 Read our [Data Principles](https://github.com/simovilab/context/blob/main/data_principles.md)
1. 🚀 Familiarize yourself with our [Technology Stack](https://github.com/simovilab/context/blob/main/tech_stack.md).
1. 🏗️ Understand our system architecture in the [Organization Profile](https://github.com/simovilab/.github/blob/main/profile/README.md)
1. 📊 Familiarize yourself with [Technology Readiness Levels](https://github.com/simovilab/.github/blob/main/TRL.md)

### Development Environment

- **Python**: Use Python 3.9+ for backend services
- **Node.js**: Use Node.js 18+ for frontend applications
- **Django**: Follow Django 4.2+ best practices for web applications
- **GTFS**: Understand GTFS and GTFS-Realtime specifications
- **API Standards**: Follow REST API design principles

## Development Standards

### Semantic Versioning (SemVer)

All SIMOVI projects **MUST** follow [Semantic Versioning 2.0.0](https://semver.org/):

```
MAJOR.MINOR.PATCH
```

- **MAJOR**: Breaking changes to APIs or core functionality
- **MINOR**: New features that are backward compatible
- **PATCH**: Bug fixes and maintenance updates

#### Examples for Transportation Systems:

- `1.0.0` → `2.0.0`: Breaking change to GTFS API structure
- `1.0.0` → `1.1.0`: New real-time vehicle tracking feature
- `1.0.0` → `1.0.1`: Fix for stop time calculation bug

### Commit Message Conventions

We use [Conventional Commits](https://www.conventionalcommits.org/) specification:

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

#### Allowed Types:

- `feat`: New feature (MINOR version)
- `fix`: Bug fix (PATCH version)
- `docs`: Documentation changes
- `style`: Code formatting, no logic changes
- `refactor`: Code restructuring without feature changes
- `perf`: Performance improvements
- `test`: Adding or updating tests
- `build`: Build system or dependency changes
- `ci`: CI/CD configuration changes
- `chore`: Maintenance tasks

#### Transportation-Specific Scopes:

- `gtfs`: GTFS data handling
- `realtime`: Real-time data processing
- `api`: API endpoints
- `mobile`: Mobile applications
- `web`: Web interfaces
- `data`: Data analysis components
- `mcp`: Model Context Protocol features

#### Examples:

```bash
feat(gtfs): add stop time estimation algorithm
fix(realtime): resolve vehicle position accuracy issue
docs(api): update endpoint documentation for v2.1
perf(data): optimize route calculation queries
```

### Branch Naming Conventions

Use descriptive branch names with prefixes:

- `feature/` - New features
- `fix/` - Bug fixes
- `docs/` - Documentation updates
- `refactor/` - Code refactoring
- `release/` - Release preparation

#### Examples:

```bash
feature/gtfs-realtime-integration
fix/stop-time-calculation-error
docs/api-endpoint-examples
refactor/database-query-optimization
release/v2.1.0
```

### CHANGELOG Requirements

Every repository **MUST** maintain a `CHANGELOG.md` file following [Keep a Changelog](https://keepachangelog.com/) format:

```markdown
# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- New GTFS-Realtime vehicle position tracking

### Changed

- Improved stop time estimation accuracy

### Fixed

- Route calculation performance issues

## [2.1.0] - 2025-01-15

### Added

- Real-time vehicle tracking dashboard
- MCP server integration for AI agents

### Changed

- Updated API response format for better compatibility

### Deprecated

- Legacy v1 API endpoints (will be removed in v3.0.0)

### Fixed

- Memory leak in data processing pipeline
```

#### CHANGELOG Categories:

- **Added**: New features
- **Changed**: Changes in existing functionality
- **Deprecated**: Features to be removed in future versions
- **Removed**: Features removed in this version
- **Fixed**: Bug fixes
- **Security**: Security improvements

## Pull Request Process

### Before Submitting

1. ✅ **Tests**: Ensure all tests pass
2. ✅ **Documentation**: Update relevant documentation
3. ✅ **CHANGELOG**: Add entry to `CHANGELOG.md`
4. ✅ **Version**: Update version if applicable
5. ✅ **TRL**: Update Technology Readiness Level if changed

### Pull Request Template

```markdown
## Description

Brief description of changes and motivation.

## Type of Change

- [ ] Bug fix (PATCH)
- [ ] New feature (MINOR)
- [ ] Breaking change (MAJOR)
- [ ] Documentation update
- [ ] Performance improvement

## Transportation Context

- [ ] GTFS data handling
- [ ] Real-time vehicle tracking
- [ ] User interface improvement
- [ ] Data analysis enhancement
- [ ] API endpoint modification

## Testing

- [ ] Unit tests added/updated
- [ ] Integration tests pass
- [ ] Manual testing completed

## Documentation

- [ ] Code comments updated
- [ ] API documentation updated
- [ ] README.md updated if needed
- [ ] CHANGELOG.md updated

## TRL Impact

Current TRL: [X] → New TRL: [Y]
Justification: Brief explanation of readiness level change.
```

### Review Process

1. **Automated Checks**: CI/CD pipeline must pass
2. **Code Review**: At least one maintainer approval required
3. **Research Alignment**: Verify alignment with SIMOVI research goals
4. **Documentation Review**: Ensure adequate documentation
5. **Testing Verification**: Confirm test coverage and quality

## Release Process

### Version Release Checklist

1. 📝 **Update CHANGELOG.md** with release notes
2. 🏷️ **Tag release** with semantic version
3. 📦 **Package release** (if applicable)
4. 📢 **Announce release** in appropriate channels
5. 📊 **Update TRL** if technology readiness changed

### Release Notes Format

```markdown
## SIMOVI [Project Name] v2.1.0

### 🚌 Public Transportation Features

- Enhanced GTFS-Realtime vehicle position accuracy
- New stop time prediction algorithms

### 🔧 Technical Improvements

- Optimized database queries for route calculations
- Updated API response formats

### 📊 Research Impact

- TRL advancement from 4 to 5 (validated in relevant environment)
- Integration with University of Costa Rica transit system

### 🐛 Bug Fixes

- Fixed memory leak in data processing pipeline
- Resolved calculation errors in arrival time estimates
```

## Code Quality Standards

### Python Projects

- **Style**: Follow PEP 8 with Black formatter
- **Type Hints**: Use type annotations for all functions
- **Documentation**: Docstrings for all public methods
- **Testing**: Minimum 80% code coverage

### JavaScript/TypeScript Projects

- **Style**: Use Prettier and ESLint
- **TypeScript**: Prefer TypeScript over JavaScript
- **Documentation**: JSDoc comments for public APIs
- **Testing**: Jest for unit tests, Cypress for E2E

### Django Applications

- **Models**: Clear field names and relationships
- **Views**: Use class-based views when appropriate
- **URLs**: RESTful URL patterns
- **Settings**: Environment-based configuration

## Documentation Requirements

### Code Documentation

- **README.md**: Clear setup and usage instructions
- **API Documentation**: OpenAPI/Swagger specifications
- **Architecture**: System design documentation
- **Examples**: Working code examples for key features

### Research Documentation

- **Methodology**: Document research methods used
- **Data Sources**: Cite transportation data sources
- **Algorithms**: Explain custom algorithms developed
- **Validation**: Document testing with real transit data

## Issue Reporting

Use our issue templates:

- 🐛 [Bug Report](https://github.com/simovilab/[repo]/issues/new?template=bug_report.yml)
- ✨ [Feature Request](https://github.com/simovilab/[repo]/issues/new?template=feature_request.yml)
- 📚 [Documentation](https://github.com/simovilab/[repo]/issues/new?template=documentation.yml)

## Community Guidelines

### Communication

- **Language**: Primary language is English for global collaboration
- **Respectful**: Maintain professional academic discourse
- **Constructive**: Provide actionable feedback
- **Research-Focused**: Keep discussions aligned with transportation research goals

### Attribution

- **Research**: Cite relevant academic sources
- **Code**: Acknowledge code contributors
- **Data**: Credit transportation data providers
- **Collaboration**: Recognize institutional partnerships

## Getting Help

- 📧 **Email**: Contact SIMOVI lab maintainers
- 💬 **Issues**: Use GitHub issues for technical questions
- 📚 **Documentation**: Check project README and wiki
- 🎓 **Research**: Review published papers and documentation

---

Thank you for contributing to advancing intelligent mobility systems research! Your contributions help improve public transportation accessibility and efficiency worldwide.

**Universidad de Costa Rica - SIMOVI Lab**  
_Intelligent Mobility Systems Laboratory_
