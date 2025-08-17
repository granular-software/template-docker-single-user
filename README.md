# {{PROJECT_NAME}}

{{PROJECT_DESCRIPTION}}

This template is a Docker-first MCP server that uses a single user with API key authentication.
It implements a full OAuth2.1 flow using SQLite database for token storage, but simplifies
the login to just ask for the API key.

## Quick Start

1. **Install dependencies**
   ```bash
   npm install
   ```

2. **Set up environment variables**
   ```bash
   cp env.example .env
   # Edit .env with your configuration
   ```

3. **Generate JWT secret**
   ```bash
   npm run secret:generate
   ```

4. **Set your API key**
   ```bash
   # Edit .env and set your API_KEY
   API_KEY=your-secure-api-key-here
   ```

5. **Initialize database**
   ```bash
   npm run db:init
   ```

6. **Start development server**
   ```bash
   npm run dev
   ```

7. **Build for production**
   ```bash
   npm run build
   npm start
   ```

## Features

- Docker-ready
- Single user, API-key based authentication
- Full OAuth2.1 implementation with SQLite database
- TypeScript support, dev and prod builds
- Refresh token support
- Dynamic client registration

## Project Structure

```
src/
├── server.ts             # Main server file
├── auth/
│   └── oauth.ts          # OAuth2.1 server with API key authentication
├── storage/
│   └── sqlite-storage.ts # SQLite-based OAuth storage
└── resources/
    ├── schemas/          # Resource schemas
    │   └── Note.ts
    └── handlers/
        └── note.ts
```

## Environment Variables

| Variable | Description | Required | Default |
|----------|-------------|----------|---------|
| JWT_SECRET | Secret key for JWT tokens | Yes | - |
| API_KEY | API key for single user authentication | Yes | - |
| PORT | Server port | No | 3000 |
| SERVER_URL | Base URL of your server | Yes | - |
| DB_PATH | Path to SQLite database file | No | data/app.db |

## Database

The template uses SQLite for OAuth token storage. The database includes:

- `oauth_users` - User accounts
- `oauth_clients` - OAuth client metadata
- `oauth_authorization_codes` - Authorization codes
- `oauth_access_tokens` - Access tokens
- `oauth_refresh_tokens` - Refresh tokens
- `notes` - Example resource data

## Development

- `npm run dev` - Start development server with hot reload
- `npm run build` - Build for production
- `npm run typecheck` - Type check without building
- `npm run db:init` - Initialize SQLite database
- `npm run secret:generate` - Generate JWT secret

## License

MIT
