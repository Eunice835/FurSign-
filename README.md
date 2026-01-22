
The full project folder with all assets can be downloaded here:  
[Download Project Folder](https://drive.google.com/file/d/1e0oB89z3VJ_l7Y5viGtXaXrXBUPgIq2V/view?usp=sharing)

Preview images:  
![Screenshot](https://drive.google.com/drive/folders/1FjLi4ohV43m52G0lNITndNqsPsSge65B?usp=sharing)

# FurSign - Furniture Customization Web Application

## Overview

FurSign is a full-stack web application designed for customizing, ordering, and tracking bespoke furniture. It offers real-time 3D previews, rule-based design suggestions, secure user authentication with role-based access, and PDF export capabilities. The project's vision is to become a leading platform in the custom furniture industry by simplifying the design and procurement process through technology, catering to the growing demand for personalized home furnishings.

## Technology Requirements

### Hardware Requirements

#### Development Environment
| Component | Minimum | Recommended |
|-----------|---------|-------------|
| Processor | Dual-core 2.0 GHz | Quad-core 3.0 GHz or higher |
| RAM | 4 GB | 8 GB or higher |
| Storage | 2 GB free space | 5 GB SSD |
| Display | 1280 x 720 | 1920 x 1080 or higher |
| Network | Broadband internet connection | High-speed internet |

#### Production Server
| Component | Minimum | Recommended |
|-----------|---------|-------------|
| Processor | 2 vCPUs | 4 vCPUs or higher |
| RAM | 4 GB | 8 GB or higher |
| Storage | 20 GB SSD | 50 GB SSD |
| Network | 100 Mbps | 1 Gbps |

### Software Requirements

#### Development Tools
| Software | Version | Purpose |
|----------|---------|---------|
| Node.js | 20.x LTS | JavaScript runtime |
| npm | 10.x | Package manager |
| Git | 2.40+ | Version control |
| VS Code / IDE | Latest | Code editor |
| Docker | 24.x | Containerization (optional) |
| Docker Compose | 2.x | Container orchestration (optional) |

#### Runtime Environment
| Software | Version | Purpose |
|----------|---------|---------|
| Node.js | 20.x LTS | Server runtime |
| PostgreSQL | 15.x | Database server |
| Nginx | 1.24+ | Reverse proxy (production) |

#### Cloud Services
| Service | Provider | Purpose |
|---------|----------|---------|
| Database | Neon (PostgreSQL) | Managed database hosting |
| Hosting | Replit | Application hosting |
| Payments | PayPal | Payment processing |
| Email | Gmail SMTP | Transactional emails |

### Programming Languages

| Language | Version | Usage |
|----------|---------|-------|
| **TypeScript** | 5.x | Primary language for frontend and backend |
| **JavaScript** | ES2022+ | Runtime execution |
| **SQL** | PostgreSQL dialect | Database queries via Drizzle ORM |
| **HTML5** | - | Document structure |
| **CSS3** | - | Styling (via Tailwind CSS) |
| **GLSL** | - | 3D shader rendering (Three.js) |

### Frameworks & Libraries

#### Frontend Stack
| Technology | Version | Purpose |
|------------|---------|---------|
| React | 18.x | UI framework |
| Vite | 5.x | Build tool & dev server |
| Tailwind CSS | 3.x | Utility-first CSS framework |
| shadcn/ui | Latest | Component library |
| Radix UI | Latest | Accessible UI primitives |
| Three.js | Latest | 3D graphics rendering |
| @react-three/fiber | Latest | React renderer for Three.js |
| TanStack Query | 5.x | Server state management |
| Zustand | 4.x | Client state management |
| Wouter | 3.x | Client-side routing |
| React Hook Form | 7.x | Form management |
| Zod | 3.x | Schema validation |

#### Backend Stack
| Technology | Version | Purpose |
|------------|---------|---------|
| Express.js | 4.x | Web framework |
| Drizzle ORM | Latest | Database ORM |
| Passport.js | 0.7.x | Authentication middleware |
| bcrypt | 5.x | Password hashing |
| express-session | 1.x | Session management |
| connect-pg-simple | 9.x | PostgreSQL session store |
| ws | 8.x | WebSocket server |
| nodemailer | 6.x | Email sending |
| node-cron | 3.x | Task scheduling |

#### Utilities & Tools
| Technology | Purpose |
|------------|---------|
| jsPDF | PDF generation |
| html2canvas | HTML to canvas rendering |
| xlsx | Excel file generation |
| date-fns | Date manipulation |
| nanoid | Unique ID generation |
| multer | File upload handling |

## Key Features & Design Decisions

### Design Studio
- Interactive, component-based customization (Legs, Tops, Frames, Panels) with multi-design support and individual pricing
- Pure Three.js implementation for realistic furniture assembly with automatic component positioning and interactive controls
- Consolidated Component Library: Streamlined base component types (16 chair legs, 11 chair seats, 12 chair backs, 6 armrests) with material/color selection via MATERIAL_VARIANTS system

### Smart Design Systems
- **Smart Component Recommendations**: Rule-based system suggesting compatible components (12 rules across furniture types) with one-click addition and duplicate detection
- **AI Design Assistant**: Archetype-driven generation system with 12 curated signature blends, creating sample designs with rich naming, descriptions, and material metadata
- **AI Style Preference Selector**: Interactive style-based filtering system for sample designs with 5 curated styles (Modern, Traditional, Contemporary, Art Deco, Minimalism)
- **Comprehensive Automatic Arrangement System**: Intelligent component positioning for all furniture categories
- **Component-Based Assembly System**: Metadata-driven component compatibility and snap-to-fit logic for chairs and sofas
- **Universal Top Fitting System**: Unified positioning logic for tops (table, chair, sofa) across 3D rendering

### Payment & Invoicing
- **PayPal Payment Integration**: Secure payment processing via PayPal for credit/debit cards and PayPal balance with automatic database recording
- **Dual Payment Options**: PayPal for automated card/debit payments with international support, plus GCash/Maya e-wallet via QR code with manual verification
- **Consultation Payment Gateway**: Integrated PayPal payment for ₱1,500 consultation fee before design submissions are processed
- **Customer Invoice Display**: Users view invoice status and price breakdowns on Order Tracking and My Designs pages
- **Pricing Model**: Design consultation fee (₱1,500) prior to production pricing; component pricing integrated but not individually displayed during design

### User Management
- **Authentication System**: Session-based with bcrypt, supporting user/admin/consultant roles and password recovery
- **Address Auto-Save System**: Optional address and phone number fields during registration that auto-populate in checkout and consultation submission forms
- **User Management System**: Admin interface for creating and managing employee accounts (administrators and consultants)

### Consultation Workflow
- **Structured Design Rejection System**: Consultants can select from predefined rejection reasons via dropdown when rejecting designs
- **Consultation Messages**: Real-time chat between customers and consultants

### Reporting & Exports
- **Sales Reports**: Daily, weekly, monthly, yearly itemized reports with VAT (12%) calculations per item
- **PDF/Excel Export**: Clean exports matching on-screen layout
- **Inventory Management**: Track materials with low-stock alerts

### Legal & Compliance
- **Legal Compliance & Terms System**: Comprehensive Terms and Agreements meeting Philippine e-commerce legal requirements (RA 11967, RA 7394, RA 10173)

## System Architecture

### Frontend
- **Framework**: React with TypeScript
- **Build Tool**: Vite
- **UI Components**: shadcn/ui built on Radix UI primitives
- **Styling**: Tailwind CSS
- **State Management**: TanStack Query, Zustand
- **Routing**: Wouter
- **3D Visualization**: Three.js, @react-three/fiber, @react-three/drei

### Backend
- **Runtime**: Node.js with Express.js
- **Language**: TypeScript
- **Database ORM**: Drizzle ORM
- **Database**: PostgreSQL (Neon)
- **Authentication**: Session-based with bcrypt, Passport.js
- **Session Storage**: PostgreSQL-based using connect-pg-simple
- **Real-time**: WebSocket (ws)

### Monorepo Structure
```
fursign/
├── client/                 # React frontend
│   ├── src/
│   │   ├── components/     # Reusable UI components
│   │   │   ├── design/     # 3D design studio components
│   │   │   └── ui/         # shadcn/ui components
│   │   ├── pages/          # Page components
│   │   │   ├── admin/      # Admin dashboard pages
│   │   │   └── user/       # User-facing pages
│   │   ├── hooks/          # Custom React hooks
│   │   └── lib/            # Utilities and helpers
├── server/                 # Express.js backend
│   ├── routes.ts           # API route definitions
│   ├── storage.ts          # Database operations (IStorage interface)
│   ├── auth.ts             # Authentication logic
│   └── services/           # Email, backup, payment services
├── shared/                 # Shared types and schemas
│   └── schema.ts           # Drizzle ORM schema definitions
├── types/                  # Additional type definitions
└── attached_assets/        # User-uploaded files
```

## External Dependencies

### Core Technologies
- **React Ecosystem**: React, React DOM, React Query
- **UI Libraries**: Radix UI, shadcn/ui
- **Database**: PostgreSQL
- **ORM**: Drizzle ORM
- **Build Tools**: Vite, esbuild
- **Authentication**: bcrypt, express-session, Passport.js

### Third-party Integrations
- **3D Rendering**: Three.js
- **Color Picker**: react-color
- **Routing**: Wouter
- **Form Management**: React Hook Form, Zod
- **Email Service**: Gmail OAuth2 (nodemailer) via fursignccustom@gmail.com
- **Payment Processing**: PayPal payment gateway for international payments and credit/debit cards
- **PDF Generation**: jsPDF, html2canvas
- **Excel Export**: xlsx library

## Entity Relationship Diagram (ERD)

```
┌─────────────────┐       ┌─────────────────┐       ┌─────────────────┐
│     USERS       │       │    DESIGNS      │       │     ORDERS      │
├─────────────────┤       ├─────────────────┤       ├─────────────────┤
│ id (PK)         │──┐    │ id (PK)         │──┐    │ id (PK)         │
│ username        │  │    │ userId (FK)     │◄─┤    │ userId (FK)     │◄─┐
│ email           │  │    │ name            │  │    │ designId (FK)   │◄─┤
│ password        │  │    │ category        │  │    │ orderNumber     │  │
│ fullName        │  │    │ components      │  │    │ status          │  │
│ role            │  │    │ status          │  │    │ totalAmount     │  │
│ address         │  │    │ previewImage    │  │    │ paymentStatus   │  │
│ phone           │  └───►│ consultantNotes │  │    │ deliveryFee     │  │
└─────────────────┘       └─────────────────┘  │    └─────────────────┘  │
        │                         │            │            │            │
        │                         │            │            │            │
        ▼                         ▼            │            ▼            │
┌─────────────────┐       ┌─────────────────┐  │    ┌─────────────────┐  │
│  CONSULTANTS    │       │  CONSULTATIONS  │  │    │   ORDER_ITEMS   │  │
├─────────────────┤       ├─────────────────┤  │    ├─────────────────┤  │
│ id (PK)         │       │ id (PK)         │  │    │ id (PK)         │  │
│ userId (FK)     │◄──────│ consultantId(FK)│  │    │ orderId (FK)    │◄─┤
│ specialization  │       │ designId (FK)   │◄─┘    │ furnitureId(FK) │  │
│ expertise       │       │ customerId (FK) │       │ quantity        │  │
│ isAvailable     │       │ status          │       │ price           │  │
└─────────────────┘       │ priority        │       │ customizations  │  │
                          └─────────────────┘       └─────────────────┘  │
                                  │                                      │
                                  ▼                                      │
                          ┌─────────────────┐       ┌─────────────────┐  │
                          │ CONSULTATION_   │       │    PAYMENTS     │  │
                          │ MESSAGES        │       ├─────────────────┤  │
                          ├─────────────────┤       │ id (PK)         │  │
                          │ id (PK)         │       │ orderId (FK)    │◄─┤
                          │ consultationId  │       │ amount          │  │
                          │ senderId (FK)   │       │ method          │  │
                          │ content         │       │ status          │  │
                          │ timestamp       │       │ transactionId   │  │
                          └─────────────────┘       └─────────────────┘  │
                                                                         │
┌─────────────────┐       ┌─────────────────┐       ┌─────────────────┐  │
│   QUOTATIONS    │       │FURNITURE_ITEMS  │       │   CART_ITEMS    │  │
├─────────────────┤       ├─────────────────┤       ├─────────────────┤  │
│ id (PK)         │       │ id (PK)         │◄──────│ id (PK)         │  │
│ designId (FK)   │       │ name            │       │ userId (FK)     │◄─┘
│ userId (FK)     │       │ category        │       │ furnitureId(FK) │
│ adminId (FK)    │       │ basePrice       │       │ quantity        │
│ materialCost    │       │ description     │       │ customizations  │
│ laborCost       │       │ dimensions      │       └─────────────────┘
│ totalAmount     │       │ isTemplate      │
│ vatAmount       │       └─────────────────┘
│ status          │
└─────────────────┘       ┌─────────────────┐       ┌─────────────────┐
                          │   MATERIALS     │       │    BACKUPS      │
                          ├─────────────────┤       ├─────────────────┤
                          │ id (PK)         │       │ id (PK)         │
                          │ name            │       │ filename        │
                          │ category        │       │ sizeBytes       │
                          │ stockQuantity   │       │ status          │
                          │ lowStockThresh  │       │ createdAt       │
                          │ unit            │       └─────────────────┘
                          │ pricePerUnit    │
                          └─────────────────┘

┌─────────────────┐       ┌─────────────────┐       ┌─────────────────┐
│  NOTIFICATIONS  │       │ ACTIVITY_LOGS   │       │  SAVED_IMAGES   │
├─────────────────┤       ├─────────────────┤       ├─────────────────┤
│ id (PK)         │       │ id (PK)         │       │ id (PK)         │
│ userId (FK)     │       │ userId (FK)     │       │ userId (FK)     │
│ type            │       │ action          │       │ designId (FK)   │
│ message         │       │ details         │       │ imageUrl        │
│ isRead          │       │ timestamp       │       │ createdAt       │
└─────────────────┘       └─────────────────┘       └─────────────────┘
```

## Data Flow Diagram (DFD)

```
                                    ┌─────────────────────────────────────┐
                                    │           EXTERNAL SYSTEMS          │
                                    │  ┌─────────┐  ┌─────────┐  ┌──────┐│
                                    │  │ PayPal  │  │  Gmail  │  │ Neon ││
                                    │  │   API   │  │  SMTP   │  │  DB  ││
                                    │  └────┬────┘  └────┬────┘  └──┬───┘│
                                    └───────┼───────────┼──────────┼────┘
                                            │           │          │
                    ┌───────────────────────┴───────────┴──────────┴───────────────────────┐
                    │                                                                       │
                    │                        FURSIGN SERVER                                 │
                    │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  │
                    │  │  Payment    │  │   Email     │  │   Backup    │  │  WebSocket  │  │
                    │  │  Service    │  │   Service   │  │   Service   │  │   Server    │  │
                    │  └──────┬──────┘  └──────┬──────┘  └──────┬──────┘  └──────┬──────┘  │
                    │         │                │                │                │         │
                    │         └────────────────┴────────────────┴────────────────┘         │
                    │                                   │                                   │
                    │                          ┌────────┴────────┐                         │
                    │                          │   Express.js    │                         │
                    │                          │   REST API      │                         │
                    │                          └────────┬────────┘                         │
                    │                                   │                                   │
                    │         ┌─────────────────────────┼─────────────────────────┐        │
                    │         │                         │                         │        │
                    │  ┌──────┴──────┐          ┌───────┴───────┐         ┌───────┴──────┐ │
                    │  │    Auth     │          │   Storage     │         │   Drizzle    │ │
                    │  │   Module    │          │   Interface   │         │     ORM      │ │
                    │  └─────────────┘          └───────────────┘         └──────────────┘ │
                    │                                                                       │
                    └───────────────────────────────────┬───────────────────────────────────┘
                                                        │
                           ┌────────────────────────────┼────────────────────────────┐
                           │                            │                            │
                    ┌──────┴──────┐              ┌──────┴──────┐              ┌──────┴──────┐
                    │   CUSTOMER  │              │    ADMIN    │              │ CONSULTANT  │
                    │    CLIENT   │              │   CLIENT    │              │   CLIENT    │
                    ├─────────────┤              ├─────────────┤              ├─────────────┤
                    │ • Browse    │              │ • Dashboard │              │ • View      │
                    │   Furniture │              │ • Manage    │              │   Designs   │
                    │ • Design    │              │   Orders    │              │ • Review    │
                    │   Studio    │              │ • Reports   │              │   Requests  │
                    │ • Cart &    │              │ • Inventory │              │ • Send      │
                    │   Checkout  │              │ • Quotations│              │   Feedback  │
                    │ • Order     │              │ • User Mgmt │              │ • Forward   │
                    │   Tracking  │              │ • Backups   │              │   to Admin  │
                    └─────────────┘              └─────────────┘              └─────────────┘
```

## User Roles

| Role | Access |
|------|--------|
| **User** | Browse furniture, design studio, cart, orders, consultations |
| **Consultant** | Review designs, provide feedback, forward to admin |
| **Admin** | Full system access, reports, inventory, user management, backups |

## Environment Variables

| Variable | Description |
|----------|-------------|
| `DATABASE_URL` | PostgreSQL connection string |
| `SESSION_SECRET` | Session encryption key |
| `PAYPAL_CLIENT_ID` | PayPal API client ID |
| `PAYPAL_CLIENT_SECRET` | PayPal API secret |
| `GMAIL_USER` | Gmail address for sending emails |
| `GMAIL_APP_PASSWORD` | Gmail app password |

## Getting Started

### Development (Replit)

The application runs automatically on Replit. Just click "Run" and access at `http://localhost:5000`.

### Development (Local)

```bash
# Install dependencies
npm install

# Set up environment variables
cp .env.example .env
# Edit .env with your configuration

# Push database schema
npm run db:push

# Start development server
npm run dev
```

## Docker Deployment

### Dockerfile

Create a `Dockerfile` in the project root:

```dockerfile
# Build stage
FROM node:20-alpine AS builder

WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies
RUN npm ci

# Copy source code
COPY . .

# Build the application
RUN npm run build

# Production stage
FROM node:20-alpine AS production

WORKDIR /app

# Install dumb-init for proper signal handling
RUN apk add --no-cache dumb-init

# Create non-root user
RUN addgroup -g 1001 -S nodejs && \
    adduser -S nodejs -u 1001

# Copy package files and install production dependencies
COPY package*.json ./
RUN npm ci --only=production && npm cache clean --force

# Copy built application from builder stage
COPY --from=builder /app/dist ./dist
COPY --from=builder /app/shared ./shared

# Set ownership
RUN chown -R nodejs:nodejs /app

# Switch to non-root user
USER nodejs

# Expose port
EXPOSE 5000

# Health check
HEALTHCHECK --interval=30s --timeout=3s --start-period=5s --retries=3 \
  CMD wget --no-verbose --tries=1 --spider http://localhost:5000/api/health-check || exit 1

# Start the application
ENTRYPOINT ["dumb-init", "--"]
CMD ["node", "dist/server/index.js"]
```

### Docker Compose

Create a `docker-compose.yml`:

```yaml
version: '3.8'

services:
  app:
    build:
      context: .
      dockerfile: Dockerfile
    ports:
      - "5000:5000"
    environment:
      - NODE_ENV=production
      - DATABASE_URL=${DATABASE_URL}
      - SESSION_SECRET=${SESSION_SECRET}
      - PAYPAL_CLIENT_ID=${PAYPAL_CLIENT_ID}
      - PAYPAL_CLIENT_SECRET=${PAYPAL_CLIENT_SECRET}
      - GMAIL_USER=${GMAIL_USER}
      - GMAIL_APP_PASSWORD=${GMAIL_APP_PASSWORD}
    depends_on:
      db:
        condition: service_healthy
    restart: unless-stopped
    networks:
      - fursign-network

  db:
    image: postgres:15-alpine
    environment:
      - POSTGRES_USER=fursign
      - POSTGRES_PASSWORD=${POSTGRES_PASSWORD:-fursign123}
      - POSTGRES_DB=fursign
    volumes:
      - postgres_data:/var/lib/postgresql/data
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U fursign"]
      interval: 10s
      timeout: 5s
      retries: 5
    restart: unless-stopped
    networks:
      - fursign-network

volumes:
  postgres_data:

networks:
  fursign-network:
    driver: bridge
```

### Quick Docker Deployment

1. Copy environment example and configure:
   ```bash
   cp .env.example .env
   # Edit .env with your values
   ```

2. Build and start containers:
   ```bash
   docker-compose up -d --build
   ```

3. View logs:
   ```bash
   docker-compose logs -f
   ```

4. Access the application at `http://localhost:5000`

### Container Management

```bash
# View container status
docker-compose ps

# Stop services
docker-compose down

# Restart services
docker-compose restart

# View logs
docker-compose logs -f app

# Access container shell
docker-compose exec app sh

# Rebuild after code changes
docker-compose up -d --build
```

### Production Considerations

- Use a reverse proxy (Nginx) with SSL termination
- Set strong passwords in production `.env` file
- Configure volume backup strategy for PostgreSQL data
- Set up monitoring for container health checks
- Consider managed container services (AWS ECS, Google Cloud Run, etc.)

## API Endpoints

### Authentication
- `POST /api/register` - Create new user account
- `POST /api/login` - User login
- `POST /api/logout` - User logout
- `GET /api/user` - Get current user

### Furniture & Designs
- `GET /api/furniture-items` - List furniture items
- `GET /api/designs` - User's saved designs
- `POST /api/designs` - Save new design
- `GET /api/sample-designs` - Browse sample designs

### Orders & Payments
- `POST /api/orders` - Create order
- `GET /api/orders` - User's orders
- `POST /api/payments/paypal` - Process PayPal payment

### Admin
- `GET /api/admin/dashboard` - Dashboard statistics
- `GET /api/admin/sales-report` - Sales report data
- `GET /api/materials` - Inventory list
- `GET /api/quotations` - Quotation management
- `GET /api/admin/backups` - Backup management

## Design Preferences

- **Color Scheme**: Green and beige for a natural, earthy, furniture-friendly appearance
- **Company Email**: fursignccustom@gmail.com (sender address for all communications)
- **UI/UX**: Clean, intuitive, responsive interface

## License

This project is proprietary software. All rights reserved.
