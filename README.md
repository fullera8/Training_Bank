# Training_Bank

A mock banking application demonstrating cloud-native development patterns using free-tier services for learning scalable banking system architecture.

## Project Overview

We are creating a mock banking app using the following tech stack:
- **.NET 8** (backend with Kestrel web server)
- **Angular** (frontend with Node.js 20)
- **Docker** (containerization with multi-stage builds)
- **Kubernetes** (container orchestration with AKS)
- **Azure** (cloud hosting with free tier services)
- **GitHub** (repository, container registry, and CI/CD)

**Requirement:** All services must be free to use for learning scalable banking system architecture.

**Key Architecture Features:**
- **Multi-architecture container builds** (AMD64/ARM64 compatibility)
- **OpenID Connect (OIDC) authentication** for secure GitHub Actions → Azure integration
- **GitHub Container Registry (GHCR)** for private container image storage
- **VS Code dev containers** for consistent development environments
- **Automated CI/CD pipeline** with GitHub Actions

## Documentation Architecture

This project uses a **tiered documentation system** optimized for both human developers and AI assistance:

### For Developers Using AI Assistants

#### Query Optimization Guidelines

**For Simple/Quick Questions:**
```
Examples: "What port?", "What .NET version?", "Start command?"
Recommended: Use Quick Reference docs for token efficiency
- 🔧 Backend-Quick.md
- 🎨 Frontend-Quick.md  
- 📦 Container-Quick.md
- ⚙️ DevEnv-Quick.md
```

**For Implementation Questions:**
```
Examples: "How to setup?", "Step-by-step guide?", "Configuration help?"
Recommended: Use Implementation Guides
- 🏗️ Backend.md
- 🖼️ Frontend.md
- 🚀 ContainerOrchestration.md
- 🛠️ DevelopmentEnvironmentSetup.md
```

**For Complex Debugging/Architecture:**
```
Examples: "Debug build failures?", "Why this approach?", "Troubleshooting?"
Recommended: Use Comprehensive Reference
- 💬 ChatLog.md (Primary technical reference with debugging scenarios)
```

#### Token-Efficient AI Prompting Examples

**Efficient Query:**
```
Context: Backend-Quick.md only
Question: What port does the backend use?
```

**Implementation Query:**
```
Context: Backend.md
Question: How do I set up multi-stage Docker builds?
```

**Rich-Context Query:**
```
Context: ChatLog.md#backend-development-and-containerization
Question: Debug ImagePullBackOff error with platform architecture mismatch
```

### Documentation Structure

```
Training_Bank.wiki/
├── 🏷️ Metadata-Legend.md          # Metadata interpretation guide
├── 💬 ChatLog.md                  # Comprehensive technical reference
├── ⚡ *-Quick.md                  # Token-optimized quick references
├── 📋 *.md                        # Implementation guides
└── 🏠 Home.md                     # Navigation hub
```

## Quick Start

### Prerequisites
- **Visual Studio Code** with Dev Containers extension
- **Docker Desktop** running on host machine
- **GitHub account** for repository hosting

### Development Setup
1. **Clone the repository:**
   ```bash
   git clone https://github.com/fullera8/Training_Bank.git
   cd Training_Bank
   ```

2. **Open in VS Code dev container:**
   - Open VS Code in the project directory
   - When prompted, click "Reopen in Container"
   - Or use Command Palette: `Dev Containers: Reopen in Container`

3. **Run the application:**
   ```bash
   # Start both backend and frontend services
   docker compose up --build
   ```

4. **Access the application:**
   - **Frontend:** [🌐 http://localhost:4200](http://localhost:4200)
   - **Backend API:** [🔗 http://localhost:8080](http://localhost:8080)

## Architecture Overview

### Backend
.NET 8 MVC application with ASP.NET Core and Kestrel web server. Uses multi-stage Docker builds for optimized production images and includes automated MSTest unit testing.

**Key Technologies:** .NET 8, ASP.NET Core MVC, Kestrel, Docker, MSTest, GHCR

### Frontend
Angular application with Node.js 20 LTS, fully containerized with hot reload support. Communicates with backend through Docker Compose networking.

**Key Technologies:** Angular (latest), Node.js 20, npm, Docker, ng serve, GHCR

### Container Orchestration
Leverages GitHub Container Registry (GHCR) and Azure Kubernetes Service (AKS) for cloud-native deployments. Uses OpenID Connect (OIDC) for secure GitHub Actions authentication.

**Key Technologies:** GitHub Actions, GHCR, AKS, OIDC, Kubernetes, Multi-architecture builds

### Development Environment
VS Code dev containers with all required tools pre-installed: Git, Node.js, .NET SDK, Azure CLI, Docker CLI, GitHub CLI, kubectl, and Helm.

**Key Technologies:** VS Code, Dev Containers, Docker, Cloudflare Tunnel, Multi-tool integration

## Project Structure

```
Training_Bank/
├── .devcontainer/           # VS Code dev container configuration
├── .github/workflows/       # GitHub Actions CI/CD pipelines
├── backend/                 # .NET 8 MVC backend application
├── frontend/                # Angular frontend application
├── k8s/                     # Kubernetes deployment manifests
├── Training_Bank.wiki/      # Comprehensive project documentation
├── docker-compose.yml       # Multi-service orchestration
└── README.md               # This file
```

## Contributing

This project serves as a learning resource for cloud-native banking application development. Contributions are welcome!

1. **Fork the repository**
2. **Create a feature branch:** `git checkout -b feature/your-feature-name`
3. **Commit your changes:** `git commit -m 'Add some feature'`
4. **Push to the branch:** `git push origin feature/your-feature-name`
5. **Submit a pull request**

## Learning Resources

For detailed technical procedures, debugging scenarios, and architectural decisions, refer to the comprehensive [📚 Project Wiki](../../wiki).

**Recommended Learning Path:**
1. [🛠️ Development Environment Setup](../../wiki/DevelopmentEnvironmentSetup) - Foundation setup
2. [🔧 Backend Development](../../wiki/Backend) - Core business logic and API design
3. [🎨 Frontend Development](../../wiki/Frontend) - User interface and client-side architecture
4. [🚀 Container Orchestration](../../wiki/ContainerOrchestration) - Deployment and scaling

## AI-Enhanced Documentation

This project's documentation includes specialized metadata fields designed for advanced Large Language Models (LLMs) with high-end coding and reasoning capabilities, such as Gemini 2.5 Pro, Claude 4, or o4-mini High.

**Purpose of Metadata Fields:**
- **Structured Context:** The metadata annotations provide LLMs with deeper, structured understanding of technical concepts, debugging workflows, and architectural decisions
- **Enhanced Assistance:** This structured approach enables AI models to provide more effective, context-aware assistance to developers working with the codebase
- **AI-Driven Development:** The metadata supports advanced AI-assisted development workflows, including automated code generation, debugging assistance, and architectural guidance
- **Token Optimization:** Tiered documentation structure allows developers to choose appropriate context level for efficient AI interactions

**Target Audience:** These enhancements are specifically designed for developers using cutting-edge AI coding assistants and automated development tools.

**Metadata Interpretation:** See [🏷️ Metadata Legend](../../wiki/Metadata-Legend) for complete tag definitions and usage guidelines.

For the latest AI model performance benchmarks in coding tasks, refer to the [📊 LiveBench AI Coding Leaderboard](https://livebench.ai/#/?Coding=a).

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Built with free-tier services to demonstrate enterprise architecture patterns
- Designed for educational purposes and skill development
- Comprehensive documentation for both human developers and AI model training
- Tiered documentation system optimized for token-efficient AI interactions

---