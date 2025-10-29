# DevOps Simulator - System Architecture & Configuration
# ======================================================
# This file contains both system architecture documentation
# and environment configuration details for Production and Development.

# ------------------------------------------------------
# SYSTEM ARCHITECTURE
# ------------------------------------------------------
architecture:
  overview: >
    DevOps Simulator follows a microservices architecture
    designed for high availability and scalability.

  components:
    - name: Application Server
      technology: Node.js + Express
      port: 8080
      scaling: Horizontal auto-scaling enabled

    - name: Database Layer
      database: PostgreSQL 14
      configuration: Master-slave replication
      backup: Daily automated backups

    - name: Monitoring System
      tool: Prometheus + Grafana
      metrics:
        - CPU
        - Memory
        - Disk
        - Network
      alerts: Email notifications for critical issues

  deployment_strategy:
    method: Rolling updates
    zero_downtime: true
    rollback: Automated on failure

  security:
    - SSL/TLS encryption
    - Database connection encryption
    - Regular security audits

# ------------------------------------------------------
# ENVIRONMENT CONFIGURATION
# ------------------------------------------------------

application:
  name: DevOpsSimulator
  version: "1.0.0"
  environment: production

server:
  host: 0.0.0.0
  port: 8080
  ssl_enabled: true

logging:
  level: INFO
  format: json
  output: /var/log/app.log

database:
  host: prod-db.example.com
  port: 5432
  name: devops_prod

features:
  auto_scaling: true
  load_balancer: true
  backup_enabled: true

# Optional Development Configuration
development:
  server:
    host: localhost
    port: 3000
    ssl_enabled: false

  logging:
    level: DEBUG
    format: text
    output: ./logs/dev.log

  database:
    host: localhost
    port: 5432
    name: devops_dev

  features:
    auto_scaling: false
    load_balancer: false
    backup_enabled: false
