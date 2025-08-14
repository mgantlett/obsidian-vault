---
tags: [memory-bank, core, technology, development, stack]
project: finance-apps
type: tech-context
status: current
priority: medium
workstream: development
created: 2025-08-13
last-updated: 2025-08-13
last-action: 2025-08-13
next-milestone: development-environment-optimization
managed-by: obsidian-mcp
related-projects: [obsidian-workflow-enhancement]
---

# Tech Context

## Technology Stack

### 🐍 **Backend Stack (Markbot)**

#### **Core Framework**
- **Python 3.10+**: Modern Python with type hints and performance improvements
- **Flask**: Lightweight web framework for REST API
- **Flask-RESTX**: API documentation and validation
- **Flask-CORS**: Cross-origin resource sharing for frontend integration

#### **Database & ORM**
- **SQLite**: Embedded database for development and small deployments
- **SQLAlchemy**: Python ORM for database abstraction
- **Alembic**: Database migration management
- **Pydantic**: Data validation and serialization with [[domain-models]]

#### **Data Science & Analysis**
- **pandas**: Data manipulation and analysis
- **numpy**: Numerical computing foundation
- **TA-Lib**: Technical analysis indicators
- **quantstats**: Portfolio performance analytics
- **yfinance**: Historical market data (retained for historical data)

#### **Optimization & ML**
- **Optuna**: Hyperparameter optimization framework
- **scikit-learn**: Machine learning utilities (future expansion)

#### **Trading Integration**
- **snaptrade-python-sdk**: Core brokerage API integration
- **matrix-nio**: Matrix/Element notifications for human-in-the-loop

#### **CLI & UI**
- **click**: Command-line interface framework
- **rich**: Rich terminal output with colors and formatting

#### **Development Tools**
- **ruff**: Fast Python linter and formatter
- **mypy**: Static type checking
- **pytest**: Testing framework
- **pre-commit**: Git hook management
- **pytest-asyncio**: Async testing support

### 🌐 **Frontend Stack (SpendViz)**

#### **Core Framework**
- **React 18**: Modern React with hooks and concurrent features
- **TypeScript**: Type-safe JavaScript development
- **Vite**: Fast development server and build tool

#### **State Management**
- **Zustand**: Lightweight state management
- **Custom hooks**: React hooks for API integration

#### **Styling & UI**
- **Tailwind CSS**: Utility-first CSS framework
- **Custom Components**: TypeScript component library
- **Responsive Design**: Mobile-first grid layouts

#### **Backend Proxy**
- **Express.js**: Node.js web framework for API proxying
- **node-fetch**: HTTP client for API requests
- **CORS middleware**: Cross-origin request handling

#### **Development Tools**
- **ESLint**: JavaScript/TypeScript linting
- **Prettier**: Code formatting
- **Hot Module Replacement**: Instant development feedback

### 🐳 **Infrastructure & Deployment**

#### **Containerization**
- **Docker**: Container platform for consistent environments
- **Docker Compose**: Multi-container orchestration
- **Volume mounting**: Live code reloading during development

#### **Development Environment**
- **VSCode**: Recommended IDE with extensions
- **Git**: Version control with conventional commits
- **Poetry**: Python dependency management (hybrid approach)

## Development Setup & Patterns

### 🏗️ **Project Structure**

```
finance-apps/
├── markbot/                    # Python Backend
│   ├── src/markbot/           # Source code
│   │   ├── api/               # Flask REST API
│   │   ├── cli/               # Command line interface
│   │   ├── core/              # Application core
│   │   ├── domain/            # Business logic
│   │   ├── infrastructure/    # External integrations
│   │   └── services/          # Application services
│   ├── configs/               # Configuration files
│   ├── data/                  # Local data storage
│   ├── stubs/                 # Type stubs for third-party libs
│   ├── pyproject.toml         # Python project configuration
│   ├── Dockerfile             # Backend container
│   └── markbot.db            # SQLite database
├── spendviz/                  # TypeScript Frontend
│   ├── src/                   # React source code
│   ├── backend/               # Express.js proxy
│   ├── public/                # Static assets
│   ├── package.json           # Node.js dependencies
│   └── Dockerfile             # Frontend container
├── docker-compose.yml         # Orchestration
└── .clinerules/              # Cline AI instructions
```

### ⚙️ **Configuration Management**

#### **Environment Configuration**
- **config.json**: Main configuration file (gitignored for secrets)
- **Environment Variables**: Docker Compose environment injection
- **Multi-Environment**: Development, testing, production configurations

#### **Configuration Patterns**
```python
# Core configuration in markbot/configs/config.json
{
  "snaptrade": {
    "client_id": "...",
    "consumer_key": "..."
  },
  "strategies": {
    "momentum": {
      "period": 10,
      "threshold": 0.05
    }
  }
}
```

### 🔄 **Development Workflow**

#### **Local Development Commands**
```bash
# Start full stack
docker compose up

# Backend only development
cd markbot && poetry install && poetry run python -m markbot.cli

# Frontend only development  
cd spendviz && npm install && npm run dev

# Run tests
poetry run pytest

# Code formatting
poetry run ruff check --fix .
```

#### **Git Workflow**
- **Conventional Commits**: Structured commit messages
- **Pre-commit Hooks**: Automatic linting and type checking
- **Branch Protection**: Main branch requires PR review

### 🏛️ **Architectural Patterns**

#### **Domain-Driven Design (DDD)**
- **Domain Models**: Pydantic models in `domain/models.py`
- **Service Layer**: Business logic orchestration
- **Anti-Corruption Layer**: [[snaptrade-mapper]] protects domain from external APIs
- **Repository Pattern**: Data access abstraction

#### **Dependency Injection**
- **AppInitializer**: Central DI container in `core/initializer.py`
- **Service Registration**: Automatic service discovery and injection
- **Interface Segregation**: Clear service boundaries

#### **API-First Architecture**
```
CLI → HTTP → Flask API (Port 5000) → Services → Domain → Infrastructure
Web → HTTP → Flask API (Port 5000) → Services → Domain → Infrastructure
```

## Integration Patterns

### 🔌 **SpendViz-Markbot Integration**

#### **Proxy Architecture**
```typescript
// SpendViz backend proxy pattern
app.get('/api/markbot/*', async (req, res) => {
  const response = await fetch(`http://localhost:5000${req.path}`); // Markbot now on port 5000
  const data = await response.json();
  res.json(data);
});
```

#### **Type Safety Bridge**
- **Frontend Interfaces**: TypeScript interfaces matching API responses
- **Runtime Validation**: Pydantic models ensure data integrity
- **Error Handling**: Unified error responses across stack

### 🎯 **SnapTrade Integration Patterns**

#### **SDK Usage Best Practices**
- **Model vs Type**: Use `snaptrade_client.model` for requests, `snaptrade_client.type` for typing
- **Type Stub Verification**: Always verify field access against stubs in `/stubs`
- **Error Handling**: Graceful handling of API rate limits and errors

#### **Data Flow Pattern**
```python
# Anti-corruption layer pattern
raw_data = snaptrade_handler.get_positions()  # Raw API response
domain_models = snaptrade_mapper.to_positions(raw_data)  # Domain models
service_result = account_service.process_positions(domain_models)  # Business logic
```

## Development Environment

### 🛠️ **IDE Configuration**

#### **VSCode Settings**
- **Python Extension**: IntelliSense and debugging
- **TypeScript Support**: Full type checking
- **Docker Extension**: Container management
- **Git Integration**: Built-in version control

#### **Type Safety Configuration**
```python
# mypy.ini - Strict type checking
[mypy]
strict = True
ignore_missing_imports = False  # Custom stubs required
```

### 📦 **Dependency Management**

#### **Python Dependencies (Poetry)**
```toml
# pyproject.toml
[tool.poetry.dependencies]
python = "^3.10"
flask = "^2.3.0"
snaptrade-python-sdk = "^2.0.0"
# ... other dependencies
```

#### **Node.js Dependencies (npm)**
```json
{
  "dependencies": {
    "react": "^18.0.0",
    "typescript": "^5.0.0",
    "express": "^4.18.0"
  }
}
```

### 🧪 **Testing Strategy**

#### **Python Testing**
- **Unit Tests**: Domain logic isolation
- **Integration Tests**: API endpoint testing
- **Contract Tests**: SnapTrade API validation
- **Mocking**: External dependency isolation

#### **TypeScript Testing**
- **Component Tests**: React component testing
- **API Tests**: Frontend-backend integration
- **Type Tests**: TypeScript compilation validation

## Performance & Optimization

### ⚡ **Backend Performance**
- **Database Indexing**: SQLite optimization for queries
- **Connection Pooling**: Efficient database connections
- **Caching Strategy**: Local caching for market data
- **Async Operations**: Non-blocking I/O for API calls

### 🚀 **Frontend Performance**
- **Code Splitting**: Lazy loading for route components
- **State Optimization**: Minimal re-renders with Zustand
- **Bundle Size**: Tree shaking and dead code elimination
- **Caching**: Browser caching for static assets

## Security Considerations

### 🔐 **Data Protection**
- **Environment Variables**: Secrets in environment, not code
- **API Key Management**: Secure credential storage
- **Input Validation**: Pydantic models prevent injection
- **CORS Configuration**: Controlled cross-origin access

### 🛡️ **API Security**
- **Authentication**: User credential validation
- **Authorization**: Role-based access control (future)
- **Rate Limiting**: Protection against abuse
- **Error Handling**: No sensitive data in error messages

## Monitoring & Observability

### 📊 **Logging Strategy**
- **Structured Logging**: JSON format for log aggregation
- **Debug Levels**: Configurable verbosity
- **Performance Tracking**: Request timing and metrics
- **Error Tracking**: Comprehensive error capture

### 🔍 **Health Monitoring**
- **API Health Checks**: Endpoint availability monitoring
- **Database Health**: Connection and query performance
- **External Dependencies**: SnapTrade API status
- **Resource Usage**: Memory and CPU monitoring

## Future Technology Considerations

### 🚀 **Planned Enhancements**
- **Redis**: Caching layer for improved performance
- **PostgreSQL**: Production database for scalability
- **Kubernetes**: Container orchestration for production
- **Prometheus**: Metrics collection and alerting
- **GraphQL**: More efficient API queries

### 🔮 **Technology Roadmap**
- **Machine Learning**: Enhanced strategy development
- **Real-time Streaming**: WebSocket integration for live data
- **Mobile Apps**: React Native for mobile access
- **Cloud Deployment**: AWS/GCP deployment automation

## 🔗 **Related Documentation**

- [[systemPatterns]] - Architecture and design patterns
- [[activeContext]] - Current development priorities
- [[progress]] - Technology implementation milestones
- [[projectbrief]] - Technical requirements and scope
- [[productContext]] - User-facing technology goals

---

*Technical context enhanced with Obsidian linking for comprehensive technology understanding and navigation*