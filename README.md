# Decentralized Website Uptime Monitor

A modern web3-enabled application that monitors website uptime using a distributed network of validators. This system provides real-time monitoring, status updates, and performance metrics while leveraging blockchain technology for trustless verification.

## Architecture Overview

The project is built using a Turborepo monorepo structure with multiple applications:

- `frontend`: A Next.js web application for the user interface
- `hub`: A central coordination server
- `validator`: A service that performs actual website checks
- `api`: Backend API service
- `db`: Database layer using Prisma with PostgreSQL

## Core Components

### Frontend (Next.js)
- Modern, responsive UI with dark mode support
- Real-time monitoring dashboard showing:
  - Website status (up/down)
  - Uptime percentage
  - Last 30 minutes of status history
  - Latency metrics
- Ability to add/remove websites to monitor

### Hub Server
- Manages a network of validators
- Distributes monitoring tasks to available validators
- Handles validator authentication and verification
- Implements a reward system (validators earn lamports for their work)

### Validator Service
- Performs actual website checks
- Reports status, latency, and signed results
- Uses cryptographic signatures for verification
- Distributed across different locations

## Key Features

- **Decentralized Monitoring**: Uses a network of validators instead of a single central server
- **Web3 Integration**: 
  - Validators are authenticated using public/private key pairs
  - Results are cryptographically signed
  - Implements a token-based reward system
- **Real-time Updates**: 
  - Status updates every minute
  - Visual representation of uptime history
- **Security**:
  - Cryptographic verification of results
  - User authentication
  - Secure WebSocket connections

## Data Model

- `User`: Stores user information
- `Website`: Tracks monitored websites
- `Validator`: Manages validator nodes
- `WebsiteTick`: Records individual status checks

## Monitoring Process

1. Users add websites to monitor through the frontend
2. Hub server distributes monitoring tasks to available validators
3. Validators perform checks and report results with signatures
4. Results are stored and displayed in real-time
5. Validators are rewarded for their work

## Technical Stack

- Frontend: Next.js, React, TailwindCSS
- Backend: Node.js, Bun runtime
- Database: PostgreSQL with Prisma ORM
- Web3: Solana integration for validator authentication
- Real-time: WebSocket for live updates

## Getting Started

### Prerequisites

- Node.js >= 18
- Bun >= 1.2.2
- PostgreSQL database
- Solana wallet (for validators)

### Installation

1. Clone the repository:
```bash
git clone [repository-url]
cd dpin-uptime
```

2. Install dependencies:
```bash
bun install
```

3. Set up environment variables:
```bash
cp .env.example .env
# Edit .env with your configuration
```

4. Run database migrations:
```bash
bun run db:migrate
```

5. Start the development servers:
```bash
bun run dev
```

## Development

- `bun run build`: Build all apps and packages
- `bun run dev`: Start development servers
- `bun run lint`: Run linting
- `bun run format`: Format code with Prettier
- `bun run check-types`: Check TypeScript types

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a new Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.
