# FEP-FEM-full - Development Context

## Project Overview
FEP-FEM is a complete implementation of the Federated Embodiment Protocol, enabling secure hosted embodiment for AI agents. The system allows guest "minds" to securely inhabit "bodies" offered by host environments through delegated control mechanisms.

## Git Workflow Strategy
**Strategy**: Development Branch Strategy

### Workflow Details
- **Main Branch**: `main` - Stable protocol releases and production-ready versions
- **Development Branch**: `development` - All active development and feature integration
- **Feature Branches**: `feature/*` or `phase-*` - Created from and merged back to `development`

### Branch Usage Guidelines
- **Never commit directly to `main`** - Use pull requests from `development`
- **All development happens on `development` branch**
- **Phase branches** for major protocol milestones
- **Merge flow**: `feature/*` → `development` → `main` (via PR)

## Development Guidelines
- Follow Go module conventions and best practices
- Update protocol documentation when changing specs
- Run comprehensive tests before merging (`make test`)
- Update security model documentation for protocol changes
- Use descriptive commit messages following existing patterns

## Architecture Notes
- **Go-based protocol implementation** with broker, router, and agent components
- **Cryptographic security** using Ed25519 signatures
- **MCP integration** for tool federation and embodiment
- **Zero-trust security model** with capability-based permissions
- **Four-phase development roadmap** for production readiness
- **Cross-platform deployment** (Linux, macOS, Windows)

## Development Environment
```bash
# Build all components
make build

# Generate development certificates
make gen-certs

# Run comprehensive test suite
make test

# Run the embodiment demo
./demo-hosted-embodiment.sh

# Start development broker
./fem-broker --listen :8443

# Run agent with embodiment
./fem-coder --broker https://localhost:8443 --agent test-agent
```

## Key Files and Directories
- `broker/` - FEM broker implementation (embodiment coordinator)
- `router/` - Mesh networking for multi-broker federation
- `agents/` - Reference agent implementations
- `docs/` - Protocol specification and architecture documentation
- `Makefile` - Build system and development workflows
- `demo-hosted-embodiment.sh` - Interactive embodiment demonstration

## Current Development Focus
Development Branch Strategy with active protocol development:
- **Phase F-I implementation**: Complete MCP federation capabilities
- **Secure hosted embodiment**: Guest minds controlling host bodies
- **Protocol v0.3.0**: Production-ready core with security model
- **Four-phase roadmap**: Systematic development toward ecosystem maturity

## Dependencies and Integration
- **Go modules**: broker, router, agents with independent versioning
- **Ed25519 cryptography**: Cryptographic signatures and identity
- **MCP Protocol**: Model Context Protocol for tool interfaces
- **Docker support**: Containerized deployment capabilities
- **Cross-platform builds**: Linux, macOS, Windows releases
- **Protocol specifications**: Complete federation and embodiment specs

## Notes and Context
- **Production-ready protocol** with complete security model
- **Active development** following four-phase roadmap
- **Well-documented** with comprehensive protocol specifications
- **Cross-platform** with automated build and release pipeline
- **Security-first design** with zero-trust principles
- **MCP federation** enabling global tool marketplace vision
- **Hosted embodiment** representing novel AI interaction paradigm