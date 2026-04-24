# Authentication Design

## Overview

This document outlines secure authentication patterns for web applications.

## Password-Based Authentication

### Requirements
- Minimum length: 12 characters
- Complexity: mix of uppercase, lowercase, numbers, symbols
- No common passwords check against breach databases
- bcrypt with cost factor 12 for hashing

### Flow
1. Client submits credentials
2. Server validates and issues JWT access + refresh tokens
3. Access token expires in 15 minutes
4. Refresh token expires in 7 days
5. Client uses refresh token to obtain new access token

## Session Management

- Store session ID in httpOnly, secure, SameSite=strict cookie
- Rotate session ID after login
- Invalidate all sessions on password change
- Detect suspicious activity (new location, device)

## OAuth 2.0 / OpenID Connect

Supported providers:
- Google
- GitHub
- Microsoft

### Flow
1. User redirected to provider authorization endpoint
2. User authenticates with provider
3. Provider redirects with authorization code
4. Server exchanges code for access token
5. Server fetches user info from provider
6. Account created or linked if exists

## MFA (Multi-Factor Authentication)

Supported methods:
- TOTP (Time-based One-Time Password)
- WebAuthn / FIDO2
- Backup codes (10 single-use codes)

## Password Reset

1. User requests reset with email
2. Server sends email with signed token (expires in 1 hour)
3. User clicks link, enters new password
4. Token invalidated after use
