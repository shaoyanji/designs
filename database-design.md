# Database Design

## Overview

This document outlines principles for designing scalable and maintainable database schemas.

## Naming Conventions

- Tables: plural, snake_case (e.g., `user_accounts`)
- Columns: singular, snake_case (e.g., `created_at`)
- Primary keys: `id` (auto-incrementing integer or UUID)
- Foreign keys: `<table>_id` (e.g., `user_id`)
- Indexes: `idx_<table>_<column>`

## Normalization Rules

1. **1NF**: Atomic values, no repeating groups
2. **2NF**: No partial dependencies on composite keys
3. **3NF**: No transitive dependencies

## Common Fields

Every table should include:
- `id` - Primary key
- `created_at` - Timestamp
- `updated_at` - Timestamp
- `deleted_at` - Soft delete (optional)

## Relationships

| Type | Implementation |
|------|----------------|
| One-to-One | Foreign key with unique constraint |
| One-to-Many | Foreign key on "many" side |
| Many-to-Many | Junction table with two foreign keys |

## Indexing Strategy

- Index foreign keys
- Index frequently queried columns
- Index columns used in ORDER BY clauses
- Consider partial indexes for filtered queries

## Data Types

- Use appropriate types for data (e.g., `INET` for IP addresses)
- Prefer `TIMESTAMP WITH TIME ZONE` for timestamps
- Use `DECIMAL` for monetary values, never `FLOAT`
- Use `UUID` for external-facing identifiers
