<p align="center">
  <img src="https://images.squarespace-cdn.com/content/v1/67dc7fc1a7db8c516a2366f2/8c9f0a41-c61a-466c-942f-176ff1eebae6/Logo_A.png?format=1500w" alt="Fuuz Logo" width="200"/>
</p>

<h1 align="center">Fuuz Industrial Intelligence Platform</h1>

<p align="center">
  <strong>Build, deploy, and scale custom manufacturing and industrial operations applications — without starting from scratch.</strong>
</p>

<p align="center">
  <a href="https://fuuz.com">Website</a> •
  <a href="https://support.fuuz.com">Documentation</a> •
  <a href="https://academy.fuuz.com">Academy</a> •
  <a href="https://www.fuuz.com/contact-us">Contact Us</a>
</p>

---

## What is Fuuz?

Fuuz is a cloud-based industrial operations platform for building custom manufacturing, telemetry, and operations applications. It provides the foundational infrastructure — data modeling, workflow automation, device connectivity, ERP integration, and visualization — so teams can focus on solving operational problems instead of building plumbing.

Every Fuuz application consists of three building blocks:

- **Data Models** — Define your schema, get a full GraphQL API automatically
- **Data Flows** — Server-side logic for automation, integration, and event processing
- **Screens** — Drag-and-drop UI builder for dashboards, forms, tables, and HMIs

Applications are packaged as portable `.fuuz` files and deployed across environments with zero downtime.

---

## Platform Architecture

```
Enterprise (Organization Root)
└── Tenant (Isolated Environment + Database)
    └── ModuleGroup (Application)
        └── Module (Functional Area)
            ├── Data Models → Auto-generated GraphQL API
            ├── Data Flows → Backend Logic & Integrations
            └── Screens → User Interface
```

Fuuz uses a **dual API architecture**:

| API | Purpose | Schema Owner |
|-----|---------|--------------|
| **Application API** | Your custom data models | Developer (via packages) |
| **System API** | Platform infrastructure (Users, Roles, Settings, Connectors) | Fuuz Platform |

Both APIs expose **Relay-style GraphQL** with full query, mutation, and subscription support.

---

## Key Capabilities

### 🏭 Industrial Operations
- ISA-95 compliant data modeling for manufacturing environments
- OEE (Overall Equipment Effectiveness) calculation and tracking
- Workcenter state management and production history
- Alarm management with deadband support
- Unified Namespace (UNS) publishing patterns

### 🔌 44 Built-In Connectors

| Category | Systems |
|----------|---------|
| **ERP/MES** | Plex, SAP, Epicor, NetSuite, Dynamics 365, Infor, Arena |
| **CRM/Commerce** | Salesforce, WooCommerce, Magento, Square, Amazon SP-API |
| **Cloud/AI** | AWS Lambda, Google API, OpenAI |
| **Database** | Microsoft SQL Server, ODBC |
| **Protocol** | HTTP, FTP, SMTP, MQTT, OPC-UA, Modbus |
| **Shipping** | UPS, FedEx, USPS, C.H. Robinson |
| **EDI** | EDI Nation, TecCom |

### 🌐 Device Gateway
Bridge cloud logic with on-premise equipment through 13 device driver types:

File, HTTP, Modbus, MQTT, MQTT Sparkplug, OPC-UA, PCCC PLC, Ethernet/IP PLC, Printer, Remote System Call, Server, SQL, TCP

All subscriptions support **Store and Forward** for resilient edge-to-cloud data delivery.

### 📊 80+ Visualization Types
Built-in FusionCharts library with column, line, area, pie, gauges, real-time charts, Gantt, treemap, heatmap, and 1,600+ geographic maps.

### 🤖 Machine Learning & Telemetry
- EWMA adaptive baselines for anomaly detection
- Z-score breach detection and alerting
- Linear regression and trend forecasting
- Pearson correlation analysis across sensor streams
- Predictive maintenance patterns

---

## How Applications Are Deployed

Applications are distributed as `.fuuz` packages — portable tar archives containing:

```
MyApp@1.0.0.fuuz
├── manifest.json        → Identity, version, platform compatibility
├── definition.json      → Export selections, dependency ordering
└── package-data.json    → Models, flows, screens, seed data
```

Deployment ordering is enforced automatically:
**ModuleGroup → Module → Sequences → Data Models → Seed Data → Screens/Flows → Schedules**

---

## Expression Language

Fuuz uses **JSONata** as its primary expression language throughout the platform — in data flow transforms, screen element bindings, validation rules, and event handlers. The platform extends standard JSONata with **182+ custom bindings** for GraphQL queries, date/time handling, string manipulation, math operations, and platform integration.

---

## Multi-Tenancy

Fuuz supports full multi-tenant isolation with five tenant types:

| Type | Purpose |
|------|---------|
| **Administration** | Enterprise-level management |
| **Application Development** | Build and test applications |
| **Application** | Production deployment |
| **Custom** | Specialized configurations |
| **Integration** | External system connectivity |

Each tenant has its own database, ensuring complete data isolation between environments.

---

## Getting Started

1. **Sign up** at [fuuz.com](https://fuuz.com) to get access to your development environment
2. **Explore the platform** — start with the Module Designer to create your first data models
3. **Build a flow** — connect to your data sources and automate your first workflow
4. **Design a screen** — use the visual Screen Designer to build your UI
5. **Package and deploy** — export your application and deploy across environments

---

## Repository Structure

| Repository | Description |
|------------|-------------|
| `fuuz-packages` | Shared application packages and templates |
| `fuuz-docs` | Platform documentation and guides |
| `fuuz-examples` | Example applications and integration patterns |
| `fuuz-units` | Unit of measure packages (SI, Imperial, Combined) |

---

## Technology Stack

- **Backend:** Node.js, GraphQL (Relay-style), MongoDB
- **Frontend:** React, FusionCharts
- **Edge:** Fuuz Gateway (Node.js) with device driver framework
- **Expression Engine:** JSONata with 182+ custom platform bindings
- **Deployment:** Cloud-native with `.fuuz` package distribution
- **Authentication:** JWT, SAML SSO, Role-Based Access Control

---

## Industry Applications

Fuuz is used across manufacturing and industrial operations for:

- **Production Tracking** — Real-time work order management, cycle time analysis, and throughput monitoring
- **Quality Management** — Inspection workflows, SPC charting, and non-conformance tracking
- **Asset Management** — Equipment lifecycle tracking, preventive maintenance scheduling, and spare parts inventory
- **Warehouse Operations** — Inventory management, pick/pack/ship workflows, and barcode integration
- **Telemetry & IoT** — Sensor data collection, real-time dashboards, and automated alerting
- **ERP Integration** — Bidirectional sync with Plex, SAP, NetSuite, Epicor, and Dynamics 365
- **Biopharma** — 21 CFR Part 11 compliant batch records, electronic signatures, and audit trails

---

## Contributing

We welcome contributions from the Fuuz community. Please read our [Contributing Guide](CONTRIBUTING.md) before submitting pull requests.

---

## License

Copyright © 2026 Fuuz, Inc. All rights reserved. See [LICENSE](LICENSE) for details.

---

<p align="center">
  <a href="https://fuuz.com">fuuz.com</a> · Built for the people who build things.
</p>
