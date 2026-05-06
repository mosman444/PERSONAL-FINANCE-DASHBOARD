# PERSONAL-FINANCE-DASHBOARD

A full-stack personal finance dashboard that connects to your bank accounts via Plaid, auto-tags your transactions using ML-based categorization, and visualizes your spending with interactive Recharts charts — all powered by a Django REST backend.

- FEATURES

¬ Bank Integration — Connect checking, savings, and credit accounts via Plaid Link
¬ Auto-Tagging — Transactions are automatically categorized (Food, Transport, Subscriptions, etc.) using Plaid's category data + custom rule overrides
¬ Interactive Charts — Spending breakdowns, trends over time, and budget tracking via Recharts
¬ Real-Time Sync — Webhook support for live transaction updates from Plaid
¬ Secure Auth — JWT-based authentication with token refresh
¬ Date Range Filtering — Slice your data by week, month, quarter, or custom range
¬ Manual Tag Overrides — Reassign categories on any transaction

TECH STACK
Backend - Django 5.x + Django REST Framework
Database - PostgreSQL
Bank Data - Plaid API (Transactions + Auth)
FrontendReact - 18 + Recharts
Auth - JWT (djangorestframework-simplejwt)
Task Queue - Celery + Redis (webhook processing)
Dev Env - Docker + Docker Compose

PROJECT STRUCTURE
finance-dashboard/
├── backend/
│   ├── config/                  # Django settings (base, dev, prod)
│   ├── apps/
│   │   ├── accounts/            # User auth & profile
│   │   ├── plaid_integration/   # Plaid API client, link tokens, webhooks
│   │   ├── transactions/        # Transaction models, auto-tagger, filters
│   │   └── dashboard/           # Aggregation & analytics endpoints
│   ├── manage.py
│   └── requirements.txt
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── charts/          # Recharts wrappers (SpendingPie, TrendLine, etc.)
│   │   │   ├── transactions/    # Transaction list, tag editor
│   │   │   └── plaid/           # PlaidLink button component
│   │   ├── pages/               # Dashboard, Accounts, Settings
│   │   ├── hooks/               # usePlaidLink, useTransactions, useCategories
│   │   └── api/                 # Axios client & API calls
│   └── package.json
├── docker-compose.yml
└── README.md

