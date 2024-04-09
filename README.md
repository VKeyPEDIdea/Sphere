# Sphere Digital Platform 🔵

[![license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/metarhia/Sphere/blob/master/LICENSE)

## Concept

Sphere Digital Platform is a distributed software infrastructure with highly adaptable and scalable services, capable of handling complex data and process tasks in a wide variety of applied fields. Sphere is a comprehensive solution that works with databases, provides and access APIs, generates reports, and runs domain logic (business processes). It has autogenerated general-purpose and multiple custom UIs (user interfaces with tables, forms, charts, and other visual elements). Sphere supports different clients (web, mobile, desktop) and provides integration with third-party information systems over various protocols (by contract basis and dynamic binding using introspection and scaffolding). Sphere can change data entities dynamically to be adaptive in a quickly changing world (flexible and capable of changing the data model and behavior without the need for deep code rewrites). Sphere is intended to deal with large databases and complex processes; it can provide automated integration with various other information systems using different protocols and provide facilities for custom integrations. Sphere provides collaborative tools for corporate users and online communities. The codebase and knowledge base of the Sphere project are community-driven, free, open-source, and knowledge-oriented. We support a holistic data-centric approach to create transparent and secure global integration hubs, reliable data processing, and data bridges between business entities and individuals in real-time.

Sphere can be applied as a core free technology for constructing the future in multiple fields: retail and supply, government, healthcare, automotive, banking, energy, insurance, education, agriculture, real estate, pharmaceuticals, tourism, e-commerce, media & entertainment, etc. Sphere is not ERP, CRM and so on itself but it can provide services for data analytics, resource planning, integrations for the following software classes (can transparently handle data and processes) as a platform for: ERP (Enterprise Resource Planning), SCM (Supply Chain Management), FM (Financial Management), CRM (Customer Relationship Management), HRM (Human Resources Management), BI (Business Intelligence), MRP (Material Requirements Planning), EAM (Enterprise Asset Management), BPM (Business Process Management), CPM (Corporate Performance Management), CMS (Content Management System), WMS (Warehouse Management System).

It's widely acknowledged that that developing any corporate or government information system starts with creating its overall architecture, selecting technologies, establishing subsystems and modules repositories. This complex and costly process typically requires 1-3 months (depending on the project's scale) of initial team effort to prepare: logging, database drivers, report generation, scheduling, queueing systems and mail delivery, client notifications, automated backups, deployment, testing, monitoring infrastructure, data validation tools, caching, balancing, security, etc. Many subsystems and modules are involved, none of which relate directly to the domain. This groundwork, involving the selection of dependencies (libraries) and technologies, probation, adaptation, and integration of components, often becomes ballast for the project. Developers commonly create their own system-level solutions (not domain-related) to cover these areas, increasing the information system's ownership cost. All in-house general-purpose libraries require maintenance and updates until the end of the information system's life, unnecessarily raising development costs. Conversely, using external dependencies carries risks (their creators often do not guarantee support or have long-term development plans). Furthermore, integrating these dependencies into a cohesive solution demands significant effort.

Consequently, every large-scale information system splits into two products: the platform and the system itself, often so closely linked that the platform cannot be easily reused or adapted for other challenges, acting simply as redundant protection against dependency instability. The best solution to these issues is the creation of platforms as a separate category of systems. This strategy allows for the separation of system tasks from product tasks, making repetitive infrastructure modules reusable. Such an approach not only optimizes development costs and significantly speeds up the process but also removes redundant tasks and ensures a higher standard of implementation. Enhancing the platform's functionalities by 15-25% has the potential to exponentially increase the scope of product deployment, potentially by hundreds of times. Additionally, configuring module settings through declarative code and domain-code (low-code) enhances the reusability of software components. This approach also facilitates their seamless integration via standardized software interfaces, aimed to unify platform modules.

## Services

Services (or subsystems) are components of an information system that can be deployed separately or in groups on servers. This differs from the concept of microservices, which entails complete isolation, including independent processes, servers, databases, and additional infrastructure; instead, it aligns more closely with Service-Oriented Architecture (SOA). The scale of services is determined by their functionality, which requires high cohesion; a service cannot be divided into parts, but can be distributed across multiple servers for clustering.

- **Authentication, Authorization, and Accounting (AAA Service)**: manages user identities, access controls, user groups, group and individual right, sessions, data manipulation log.
- **Logging and Monitoring (Audit Service)**: collects, stores, and analyzes logs for system health monitoring and debugging.
- **Global Identifier Service**: issues globally unique identifiers for stored records and resolves queries by ID.
- **Event Bus**: handles event-driven communication between subsystems for decoupling and asynchronous processing.
- **Queue Subsystem**: manages message queues for inter-service communication, ensuring reliable data transfer.
- **Configuration Management**: manages system settings and configurations, allowing for dynamic adjustments.
- **Caching System**: improves performance by temporarily storing frequently accessed data.
- **Notification Service**: handles the distribution of system-wide alerts, emails, and notifications.
- **Reporting Service**: provides tools for creating, scheduling, and distributing custom reports.
- **Batch Processing**: manages execution of batch jobs for data processing and maintenance tasks.
- **Service Orchestration**: coordinates and manages service interactions, ensuring optimal workflow execution.
- **Analytics and BI**: analyzes data to provide insights and support business intelligence initiatives.
- **File Storage Service**: manages a distributed system for storing files with specified access rights and retention periods.
- **Global Storage Service**: central to the system, it manages indexing, reactive cursors, and distributed queries.
- **Cryptography Service**: handles encryption and digital signatures.
- **Static Content Delivery**: organizes static files like JavaScript, HTML, CSS on a content delivery network (CDN).
- **Business Logic Runner**: executes business processes, enforcing data access restrictions and logging user actions.

## Architectural principles

Core architectural principles:

- Isolation with IoC (Inversion of Control) and DI (Dependency Injection);
- Metaprogramming (dynamic metamodel interpretation);
- Platform-agnostic domain codebase;
- Layered architecture (no system code in applications);
- Multiparadigm programming and semantic code;
- Wide use of DSL (Domain-Specific Languages);
- Contract programming (defined with schemas);
- Modularity with auto-binding (no dependency locators in domain code).

Server-side platform operational approach:

- Applied code must be simple and secure; hence, we use sandboxing with V8 isolated contexts, worker threads, and JavaScript closures for varying isolation layers;
- Domain code is kept separate from system code using Domain-Driven Design (DDD), layered (onion) architecture, Dependency Injection (DI), SOLID, and GRASP principles, alongside a contract-based approach;
- We support stateful applications with RPC and client-session sticky to servers;
- No I/O is faster even than async I/O, therefore, we hold state in memory to share it across multiple threads, and use lazy I/O for persistent storage;
- We rely solely on internal trusted dependencies, excluding third-party npm packages. The total size of the Metarhia technology stack is less than 2MB.

## Feature list

Sphere core functionality:

- API provisioning
- Auto-generated browser UI
- Auto-generated browser mobile UI
- Automated and custom form generation
- Grid-style database navigation
- UI and data internationalization
- Data validation
- Report generation
- Third-party system integration
- Domain-logic execution
- Contract-based data validation
- Collaborative and interactive tools
- Data analytics and business intelligence
- Surveys and feedback collection
- Query builder
- Project management tools
- Documents flow and storage
- Registry engine
- Chatbots integration
- Mail delivery
- Event planning
- Asset management and resource planning
- Personnel and customer database
- Payment integration
- AI and ML integration
- Planning tools
- Interactice chat and messaging

Inherited from Metarhia:

- **API auto-routing** calls to `endpoint` for rapid API development (no need to add routes manually);
- **API concurrency**: request execution timeout and execution queue with both timeout and size limitations;
- **Schemas** for API contract, data structures validation, and domain models;
- **Application server** supports different API styles: RPC over AJAX and over Websocket, REST, and web hooks;
- **Multiple protocols** support: HTTP, HTTPS, WS, WSS;
- **Auto loader** with `start` hooks, namespace generation for code and dependencies;
- **Live reload** of code through filesystem watch;
- **Graceful shutdown** with `stop` hooks;
- **Minimal dependencies** and reduced code size;
- **Layered architecture**: api, domain logic, data access layer, and system code layer (hidden);
- **Code sandboxing** for enhanced security and execution context isolation;
- **Code protection**: reference pollution prevention, prototype pollution prevention;
- **Multi-threading** for CPU utilization and execution isolation;
- **Load balancing** for simple scaling with redirection to multiple ports;
- **Caching**: in-memory caching for APIs and static files;
- **Configuration**: environment-specific application settings;
- **Database access** layer compatible with PostgreSQL with SQL-injection protection;
- **Persistent sessions** with authentication, groups, and anonymous sessions;
- **Buffered logging** (lazy write) with log rotation (keep logs N days) and console interface;
- **Testing**: integrated node.js native test runner and table-test support;
- **Inter-process** communication and shared memory used for state management;
- **File utilities**: upload, download, support for partial content and streaming;
- **Task Management**: scheduled task execution at specific intervals or certain times;
- **Server health monitoring** (to be implemented);
- **Database migrations** (to be implemented);
- **State synchronization mechanism with transactions and subscription** (to be implemented);
- **Multi-tenancy support** (to be implemented);

## Requirements and dependencies

- Node.js v18.x or v20.x
- Linux (tested on Fedora v36-38, CentOS v8-9)
- Postgresql v11-16
- OpenSSL v3 or later (optional, for https & wss)
- [certbot](https://github.com/certbot/certbot) (recommended but optional)

## Usage

## License

Copyright (c) 2024 Metarhia contributors. [MIT licensed](./LICENSE).
