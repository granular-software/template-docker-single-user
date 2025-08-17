# {{PROJECT_NAME}}

{{PROJECT_DESCRIPTION}}

Single-user docker template with SQLite database: API key authentication with full OAuth2.1 implementation.

## Quick Start

```bash
npm install
cp env.example .env
npm run secret:generate
# Set your API_KEY in .env
npm run db:init
npm run dev
```

## Features

- Docker-ready
- Single user with API key authentication
- Full OAuth2.1 implementation
- SQLite database for token storage

## License

MIT
