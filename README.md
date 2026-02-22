Axis – AI-Powered Smart Ticket Management Platform

Axis is a production-ready, AI-powered ticket management system built with Streamlit and Python.

Originally developed during HackUTD (NMC² prompt) and later expanded into a full operational platform, Axis combines real-time state management, intelligent prioritization, workflow automation, and Jira integration into a modern operations control center.

Axis is designed for technicians, engineers, and administrators managing high-impact infrastructure environments such as data centers.

🚀 Overview

Axis improves operational efficiency by:

Automating ticket validation

Objectively scoring priority

Enforcing lifecycle workflows

Syncing directly with Jira

Supporting bulk imports and exports

Providing dashboard-level analytics

It transforms basic incident tracking into an intelligent decision-support system.

✨ Core Features
🔐 Multi-User Authentication

Role-based access control:

Technician

Engineer

Admin

Per-user persistent ticket storage

User-specific audit logs

Session-based login system

Each user has isolated ticket data stored locally.

🤖 AI-Powered Ticket Intelligence

Axis integrates OpenRouter AI to:

Validate ticket completeness

Suggest missing details

Enhance summaries and descriptions

Objectively calculate priority (0–10 score)

Detect priority mismatches (user vs AI)

Recommend operational next steps

If no API key is configured, Axis automatically runs in intelligent mock mode.

📊 Smart Priority Scoring Engine

Tickets are analyzed across weighted operational dimensions:

Impact Scope (single server → datacenter-wide)

Service Impact (none → full outage)

Urgency (scheduled → immediate)

Safety Risk (none → critical)

Each ticket includes:

AI-calculated priority level (Low / Medium / High / Critical)

Numeric score (0–10)

AI reasoning explanation

Recommended actions

This ensures consistent, objective prioritization.

🧾 Ticket Lifecycle Workflow

Supported statuses:

Draft

AI Review

Approved

In Progress

Completed

Blocked

Workflow features:

AI-triggered review states

Approval gates

Start/complete transitions

Priority override handling

Expandable ticket detail view

🔄 Jira Integration

Create Jira issues directly from tickets

Automatic priority mapping

Server/rack metadata labeling

Store Jira issue key and sync timestamp

Export Jira-compatible CSV format

Email Jira ticket summary with direct link

Jira configuration is managed via environment variables or runtime settings.

📂 Bulk CSV Import & Export
Import

Upload CSV file

AI processes each row

Optional automatic Jira sync

Progress-tracked batch import

Export

Standard ticket summary CSV

Jira-compatible CSV

Email export capability

📧 Email Integration

Send Jira ticket summaries

Send ticket export CSVs

TLS-secured SMTP support

Runtime configuration in Settings

📈 Dashboard & Analytics

Axis includes a modern operations dashboard with:

Total tickets

Active tickets

Completed tickets

Jira-synced tickets

Priority distribution visualization (Plotly)

Quick actions panel

System configuration status indicators

📜 Persistent Audit Logging

Per-user logs track:

Ticket creation

Status changes

Approval actions

Jira synchronization

Deletions

Bulk imports

Stored as JSON files for persistence.

🛠 Tech Stack

Frontend: Streamlit

Backend Logic: Python

AI Integration: OpenRouter API

Data Processing: Pandas

Visualization: Plotly

External Integration: Jira REST API v3

Email: SMTP (TLS)

Persistence: JSON-based local storage

Environment Configuration: python-dotenv

📦 Installation
Clone Repository
git clone <repo-url>
cd axis
Install Dependencies
pip install streamlit pandas plotly python-dotenv requests
🔑 Optional Environment Configuration

Create a .env file:

# OpenRouter
OPENROUTER_API_KEY=
OPENROUTER_MODEL=nvidia/nemotron-nano-12b-v2-vl:free

# Jira
JIRA_BASE_URL=
JIRA_EMAIL=
JIRA_API_TOKEN=
JIRA_PROJECT_KEY=AXIS

# Email
SMTP_SERVER=smtp.gmail.com
SMTP_PORT=587
EMAIL_ADDRESS=
EMAIL_PASSWORD=

If OpenRouter is not configured, Axis runs in mock AI mode.

▶️ Running the Application
streamlit run app.py

The application will open automatically in your browser.

👥 Demo Accounts
Username	Password	Role
tech1	tech123	Technician
tech2	tech123	Technician
engineer1	eng123	Engineer
admin	admin123	Admin
📁 Data Storage Structure
user_data/
  tickets_<username>.json
  audit_log_<username>.json

Each user has isolated ticket and log storage.

🧠 System Architecture

Axis consists of four primary layers:

UI Layer – Streamlit dashboard and interactive components

AI Intelligence Layer – Validation and priority scoring engine

Integration Layer – Jira + Email APIs

Persistence Layer – JSON-based user storage

🏁 Origin

Axis was initially built during HackUTD (NMC² prompt) as a rapid prototype focused on:

Real-time ticket state management

Incident tracking

Reactive UI updates

Automated email notifications

Dynamic filtering and search

It has since evolved into a fully featured AI-driven operations platform.

📌 Roadmap

PostgreSQL database support

SLA tracking & automated escalation

Real-time notifications

Role-based workflow enforcement

Kubernetes deployment

SSO integration

Webhook-based Jira sync
